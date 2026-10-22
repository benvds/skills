---
name: ia-presenter
description: Write presentations for iA Presenter as one Markdown file, with the spoken script as speaker notes and only what the audience must see on the slides. Use when the user wants a talk, presentation or slide deck for iA Presenter, wants to turn notes, an outline or a document into iA Presenter slides, or wants help structuring a talk with speaker notes in that format. Examples are "make an iA Presenter deck about X", "turn this outline into slides for iA Presenter", "write the script and slides for my talk" when iA Presenter is in use, and "maak een presentatie in iA Presenter". Not for PowerPoint, Keynote, Google Slides, reveal.js, Marp or other slide tools, for designing a theme, or for a persuasive story without slides.
---

# iA Presenter presentations

Write text-first presentations in iA Presenter's Markdown format. The result is one `.md` file that the user opens or imports in iA Presenter.

## Core idea

iA Presenter turns the usual slide design around. By default, text is not visible on a slide. You choose what becomes visible.

- **Plain text** is the speaker's script. Only the speaker sees it.
- **Tab-indented text** is visible on the slide.
- **Headings** are visible on the slide.

This enforces the principle that what you say is not what you show.

## Workflow

1. **Outline.** Write the structure: the slides with one idea each, in order. Show it to the user and adjust it until it is solid. If nobody can answer, for example when you run as a subagent or the user says "just make it", don't wait. Use the outline as it is and say after the result which choices you made.
2. **Script.** Write the speaker notes as plain text: what the speaker will actually say.
3. **Titles.** Add a heading for each slide.
4. **Visible text.** Tab-indent only what the audience must see.
5. **Images.** Add images sparingly, to create tension, not as decoration.

For a persuasive talk, such as a pitch, a proposal or a vision, build the story first. If the `business-storytelling` skill is available, use it for the structure before you write the slides.

## Syntax

### Slides

Separate slides with three dashes on their own line:

```markdown
---
```

Headings on consecutive lines, with nothing between them, stay together on one slide.

### Headings

Standard Markdown headings, from `#` to `######`. Use levels 1 to 3 for slide titles. Level 4 is the usual way to write a caption for an image.

```markdown
# Big title

---

### Smaller title
```

### Speaker notes

Plain text without a tab. The audience doesn't see it:

```markdown
# Revenue growth

This is what I'll say out loud. The audience only sees the heading above.
I can write my full script here. Several paragraphs work fine.
```

### Visible text

Start the line with a tab character:

```markdown
# The problem

	60% of users leave within 48 hours.

This explains why that number matters and what we learned from exit surveys.
The tabbed line above is all the audience sees.
```

Lists and block quotes work the same way. Put the tab before the marker:

```markdown
	- First point
	- Second point

	> A quote the audience should see
```

Bullet points often belong in the speaker notes, not on the screen.

Always use a real tab character, not spaces.

### Comments

A line that starts with `//` is a comment. It stays in the editor and is not shown on the slides. Use comments for reminders, such as an image that still has to be found:

```markdown
// Image: a stopwatch showing 3 minutes
```

### Images

In a Markdown file, use Markdown image syntax:

```markdown
![Stopwatch showing 3 minutes](stopwatch.png)

#### First win in under 5 minutes
```

- Images are visible on the slide by default. Don't indent them.
- Write a caption as a level 4 heading, before or after the image.
- Use the file name without a leading slash, and write spaces in the name as `%20`.
- Give every image a description in the brackets, for accessibility.

When the user has no image yet, don't invent a file name. Write a `//` comment that describes the image you would use, so the user can add it later. iA Presenter asks for access to local images when it imports the file. Size, position and filters are set in the app.

### Other formatting

iA Presenter supports `**bold**`, `*italic*`, `==highlight==`, `~~strikethrough~~`, links, footnotes, tables and fenced code blocks. Indent a line with a tab to show it on the slide. Tables and code blocks can behave differently from text, so tell the user to check them in the app.

## Content principles

**One idea per slide.** If a slide is hard to write, it probably holds two ideas. Split it.

**Create tension.** Show images that raise a question, so the audience listens for the answer. Don't show images that repeat what you say.

**Billboard test.** A slide should be readable at a glance, like a billboard you drive past.

**No stuffed slides.** People read faster than you speak. If you show your script, they read ahead and stop listening.

For more on structure, arguments, openings and conclusions, read [references/rhetoric.md](references/rhetoric.md).

## Example

```markdown
# Why onboarding is broken

Today I want to challenge how we think about new users. This isn't about features. It's about time to value.

---

# The problem

	60% leave before they get it.

New users leave within 48 hours. They never see what makes us great. We lose people before they understand why they signed up.

---

// Image: a stopwatch showing 3 minutes

#### First win in under 5 minutes

Slack gets users to send their first message in 3 minutes. That's the benchmark. When did your users last feel successful? How long did it take?

---

# What we're going to do

	Remove the tutorial.
	Start with action.
	Celebrate success.

Prototype ready Friday. Testing next week. I need volunteers.
```

## Output

Write the presentation in the language of the audience. Deliver one `.md` file in the way the environment allows: as a file in the working folder, as a download, or as a code block if you can't make files. In a code block, keep the tab characters. Tell the user to open or import the file in iA Presenter, which handles the layout.

After the file, list in a few lines the images that still need to be found and any choices you made without the user.
