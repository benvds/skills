# ia-presenter

Use it when you present with [iA Presenter](https://ia.net/presenter). It writes your talk as one Markdown file: the full script as speaker notes, and on the slides only what the audience must see. You open or import the file in iA Presenter, and the app does the layout.

It doesn't activate for PowerPoint, Keynote, Google Slides, reveal.js, Marp or other slide tools, or for designing a theme.

## What it does

- It starts with an outline of one idea per slide and adjusts it with you before it writes the slides. If nobody can answer, it uses its own outline and says which choices it made.
- It writes what you will say as plain text, which iA Presenter shows only to you.
- It tab-indents only what belongs on the slide, and keeps bullet points in your notes where it can.
- It suggests images that raise a question instead of repeating what you say. It doesn't invent file names: an image you still need becomes a `//` comment with a description, listed after the result.
- It uses the iA Presenter syntax from the [official Markdown guide](https://ia.net/presenter/support/basics/markdown) and [image guide](https://ia.net/presenter/support/visuals/images).
- For structure, openings and conclusions, it draws on the five canons of rhetoric in [references/rhetoric.md](references/rhetoric.md).

## Example

```markdown
# The problem

	60% leave before they get it.

New users leave within 48 hours. They never see what makes us great.

---

// Image: a stopwatch showing 3 minutes

#### First win in under 5 minutes

Slack gets users to send their first message in 3 minutes. That's the benchmark.
```

The audience sees the heading, the tabbed line and the caption. The rest is your script.

## Opinions you may not share

This skill takes positions. Change them in [SKILL.md](SKILL.md) or [references/rhetoric.md](references/rhetoric.md) if they don't suit you.

- One idea per slide, and a slide must pass the billboard test.
- Bullet points belong in your notes, not on the screen.
- No agenda slide. Start with why anyone should care.
- Images create tension. Stock images that repeat your words are left out.
- Shorter is better. Finish on time.

## Works well with

- [business-storytelling](../business-storytelling/README.md) to build a persuasive story before it becomes slides.
