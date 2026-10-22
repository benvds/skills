# mobile-pdf

Use it when you want to read a Markdown file, report, article or research document on your phone. It makes a PDF with a narrow page and large text, so your phone shows it at full width and you can read it without zooming, like in a reading app.

It doesn't activate for PDFs meant for printing, for filling, merging or splitting existing PDFs, or for EPUB and other e-book formats.

## What it does

- It uses a page of 102 by 210 mm with 14 pt body text and small margins: about 40 characters per line.
- It converts headings, lists, quotes, links, code blocks, images and bold and italic text from Markdown.
- It turns tables into one block per row, with each cell as "header: value", because a table with columns doesn't fit a narrow page.
- It adds the title and the page number at the bottom of every page, in the language of the document.
- It switches to a font such as DejaVu Sans when the text has characters that the standard font can't show.
- It names the file after the source, ending in `-mobile.pdf`, and tells you what it couldn't convert, such as a missing image.

## What it needs

- **Code execution** with Python. It installs [ReportLab](https://www.reportlab.com/opensource/) to build the PDF. Without code execution, it gives you the script to run yourself.

## Opinions you may not share

This skill takes positions. Change them in [SKILL.md](SKILL.md) if they don't suit you.

- A narrow page instead of wide margins.
- Never less than 14 pt for body text.
- Navy and teal headings on a white page.
- Tables become lists of rows.
