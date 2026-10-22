---
name: mobile-pdf
description: Turn Markdown or another written document into a narrow PDF with large text, for comfortable reading on a phone or small tablet. Use when the user wants to read a Markdown file, report, research document, article or notes on their phone, or asks for a PDF for mobile, for example "make a PDF I can read on my phone", "mobile PDF of this report", "PDF for reading on the go" and "maak hier een pdf van voor op mijn telefoon". Use it instead of a generic PDF approach whenever reading on a phone is the goal. Not for PDFs meant for printing or A4 and Letter layouts, for filling, merging, splitting or editing existing PDFs, or for EPUB and other e-book formats.
---

# Mobile PDF

Make a narrow PDF with large text that reads like a reading app on a phone. You build it with ReportLab in Python, so you need code execution. Without code execution, say so and give the user the script to run.

## Key idea

The trick is a **narrow page**, not wide margins. A page of 102 mm wide keeps lines short at a large font size, with the text almost edge to edge. A phone shows the page at full width, so the text is large without zooming.

## Page layout

```python
from reportlab.lib.units import mm
from reportlab.lib.pagesizes import A5

PAGE_W = 102 * mm   # narrow: about 40 characters per line at 14 pt
PAGE_H = A5[1]      # A5 height, 210 mm
MARGIN = 5 * mm     # minimal padding left and right
TOP_MARGIN = 14 * mm
BOTTOM_MARGIN = 14 * mm
```

Use `SimpleDocTemplate` with `pagesize=(PAGE_W, PAGE_H)` and these margins.

## Typography

```text
TITLE   fontSize=26  leading=31  color=NAVY
H1      fontSize=20  leading=25  color=TEAL  spaceBefore=18
H2      fontSize=17  leading=22  color=NAVY  spaceBefore=14
H3      fontSize=15  leading=19  color=NAVY  spaceBefore=10
BODY    fontSize=14  leading=21  color=#1f2937  spaceAfter=6
BULLET  fontSize=14  leading=21  bulletFontSize=14  leftIndent=14  (plus 14 per nesting level)
QUOTE   fontSize=14  leading=21  leftIndent=10  color=MGRAY  italic
CODE    fontSize=11  leading=15  font=Courier  color=#374151  background=LGRAY
SMALL   fontSize=11  leading=15  color=MGRAY
```

## Colours

```python
NAVY  = "#1a2744"
TEAL  = "#0d7c66"
MGRAY = "#6b7280"
LGRAY = "#f4f5f7"
```

## Fonts

The built-in Helvetica only covers Western European characters. Other characters, such as Greek, Cyrillic, arrows, maths symbols, or subscript and superscript digits, render as black boxes. If the text contains them, register a TrueType font that has them, such as DejaVu Sans, and use it for every style. Emoji don't render in ReportLab. Leave them out, or replace them with a word.

## Converting Markdown

Read the source line by line. Join consecutive text lines into one paragraph, because Markdown wraps long paragraphs over several lines.

| Markdown | Becomes |
|---|---|
| first `# ` heading | TITLE |
| `## ` | H1, with a thin teal line under it |
| `### ` | H2 |
| `#### ` and deeper | H3 |
| `- `, `* ` or `+ ` | BULLET with `•` as `bulletText`, indented per nesting level. Don't write `&#8226;`: `bulletText` is not parsed, so it shows literally. |
| `1. ` | BULLET with the number instead of the bullet |
| `> ` | QUOTE |
| fenced code block | CODE, one paragraph, lines joined with `<br/>` and leading spaces as `&nbsp;` |
| table | one block per row: each cell as "header: value" on its own line, with a light grey line between rows. Tables with columns don't fit a narrow page. |
| `![alt](path)` | the image scaled to the text width if the file exists, otherwise the alt text in SMALL |
| `---` | a light grey horizontal line |
| blank line | end of the paragraph |
| anything else | BODY |

Before you add inline markup, escape the text, because ReportLab's `Paragraph` reads it as XML:

1. `&` becomes `&amp;`, `<` becomes `&lt;` and `>` becomes `&gt;`.
2. Then convert the inline markup:
   - `**text**` becomes `<b>text</b>`. Do this before italics.
   - `*text*` and `_text_` become `<i>text</i>`.
   - `` `text` `` becomes `<font face="Courier" size="12" color="#374151">text</font>`.
   - `[text](url)` becomes `<a href="url" color="#0d7c66">text</a>`.

If the source is not Markdown, such as a Word file or a web page, first turn it into Markdown with headings, lists and paragraphs, then follow the same steps.

## Footer

Put the document title and the page number 8 mm from the bottom, with the `onFirstPage` and `onLaterPages` hooks. The title is the first `# ` heading, or the file name if there is none. Write the page label in the language of the document, such as "Page" or "Pagina".

```python
def footer(canvas, doc):
    canvas.saveState()
    canvas.setFont("Helvetica", 8)
    canvas.setFillColor(MGRAY)
    canvas.drawString(MARGIN, 8 * mm, title)
    canvas.drawRightString(PAGE_W - MARGIN, 8 * mm, f"{page_label} {doc.page}")
    canvas.restoreState()
```

Shorten a long title so it doesn't run into the page number.

## Install

```bash
pip install reportlab
```

If pip refuses because the environment is managed by the system, use a virtual environment. Only in a temporary sandbox may you add `--break-system-packages`.

## Output

Name the file after the source, with `-mobile.pdf` at the end. Deliver it in the way the environment allows: as a file in the working folder, as a download, or with the tool that sends files to the user. Then say in one line how many pages it has, and name anything you couldn't convert, such as a missing image.

## What not to do

- Don't use a full A5, A4 or Letter page. The lines get too long and the text too small on a phone.
- Don't fake a narrow column with wide margins. That wastes screen space.
- Don't go below 14 pt for body text.
- Don't put a wide table on the page as a table.
