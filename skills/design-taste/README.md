# design-taste

Design judgement for anything people look at: web pages, app screens, dashboards, slide decks, documents and posters. A model's first design idea is the category's most typical idea, because it was trained to prefer the familiar. This skill makes the assistant notice that default, choose a direction that fits this subject and its use, carry it through every part, and judge the result the way a stranger would.

It doesn't activate for backend work, text-only editing, data analysis, brand strategy without a visual artefact, or exact reproduction of a given design.

## What taste means here

[DESIGN.md](DESIGN.md) is a meta-analysis of two published design skills, [Impeccable](https://github.com/pbakaus/impeccable) and [Taste Skill](https://github.com/Leonxlnx/taste-skill), and of the research on aesthetic judgement. In short:

- **Taste is judgement, not preference.** Designers get better, and see their old taste as worse, not just different.
- **Taste is fit.** The right form for this subject and this use, so that it could not belong to a competitor.
- **Taste balances the typical and the new.** People prefer what is easy to process, and also what is new. The best design is the most advanced that is still acceptable.
- **Taste needs feedback.** Feeling sure proves nothing. You look at the result.
- **Taste is decision.** Removing every cliché leaves an empty page with good manners. In Taste Skill's own tests, removal alone lost to no skill at all.
- **Taste is coherence.** One idea in every part, not a bold first screen followed by stock blocks.
- **Rules about taste date.** Yesterday's remedy is today's cliché, so the skill names procedures, never replacement fonts or colours.

## The method

1. **Read what is true:** the subject, the audience and where they use it, the one goal, and the real material that exists.
2. **Inventory the subject:** eight to twelve things only this client has.
3. **Name the rut:** what the category always ships, its predictable opposite, and the assistant's own known defaults.
4. **Write candidates with their typicality:** five to seven directions from the subject's world, each with an honest guess of how often a model would land there.
5. **Choose by fit:** the least typical candidate that passes the competitor test, suits the mode and is still recognisable. The familiar option stays available if you want it.
6. **Commit and build:** a direction in six lines, then a build that meets the craft floor and carries the idea into every part.
7. **Look and correct:** screenshots at real sizes, thirteen critique passes, fix the top three, at most three rounds.

It also refines an existing design inside its own identity, and reviews a design without changing it.

## Example

> **You:** Make a landing page for our bakery, De Zeven Deuren.
>
> **Assistant:** *(in its notes)* Rut: a cream page with a serif logo, a loaf photo and "Freshly baked since 1987"; the opposite is a black page with neon type. Inventory: the seven doors of the old almshouse across the street that gave the bakery its name, the oven lit at 4:30, one rye batch on Saturdays… Chosen: "On this page, the seven doors become the seven sections, each opening on one bread." Competitor test: the bakery two streets away has no seven doors.

## What it needs

- **Rendering** to look at the result: code execution with a browser, or a preview tool. Without it, the critique runs on the code and the report says so.
- **Web search** for real pictures from open collections. Without it, the assistant draws or uses type and colour.

## Opinions you may not share

This skill takes positions. Change them in [SKILL.md](SKILL.md) or the files in [references/](references/) if they don't suit you.

- No monospace labels, 01/02/03 numbering or hairline grids. These are more common on award sites than on weak ones; the skill avoids them as house style, and says so.
- Commit rather than refine when in doubt, except on screens people work in, where precision and restraint win.
- The least typical option that still fits, not the safest.
- No invented customers, quotes, logos or numbers, ever.

## Works well with

- [business-storytelling](../business-storytelling/README.md) for the story behind a pitch or a landing page, before the design.
- [ia-presenter](../ia-presenter/README.md) for slides in iA Presenter. The app does the layout; this skill judges what the audience sees.
- [mobile-pdf](../mobile-pdf/README.md) for a document to read on a phone. Its page and type scale stay fixed.
- [plain-writing](../plain-writing/README.md) for the words in a document or on a page.

## Credits

The modes (persuade, operate, read, experience), the idea of a craft floor and the warning about Claude's own cream-and-serif default come from [Impeccable](https://github.com/pbakaus/impeccable) by Paul Bakaus (Apache 2.0). The subject inventory, the competitor test, the dated registry of tells, the critique passes and the gallery study figures come from [Taste Skill](https://github.com/Leonxlnx/taste-skill) by Leonxlnx (MIT). Both are rewritten here in my own words, without their scripts.
