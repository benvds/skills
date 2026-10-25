# Texts and the booklet

Together, the texts form a booklet about the track. They are reference material: you write them after the user has built the material themselves. The evidence comes from sources you opened. The user's material (teach-back, example, pitfalls) makes it concrete and sits in its own paragraphs.

Write the texts in the language of the track. File names, frontmatter keys and `type` values stay as below, so the booklet can be assembled in any language. The headings in this file are examples: write them in the language of the track.

## Which texts, and when

| File | When | Contents |
| --- | --- | --- |
| `[slug]-00-introduction.md` | when confirming; again at the end | why this subject, the end tasks, how the track works, how to read the booklet |
| `[slug]-01-overview.md` | when confirming; again after every curriculum change and at the end | table with phases, parts, end tasks |
| `[slug]-05-research.md` | when confirming; again when the research map changes | research map, search log, source list |
| `[slug]-10-phase-1.md`, `-20-phase-2.md`, ... | end of every phase | the chapter |
| `[slug]-90-next-steps.md` | end of the track | "Next steps and broadening", written out |

The numbers leave room for files the user adds later.

**Short track.** Don't deliver texts at the start. At the end, deliver one chapter with all parts (`[slug]-10-phase-1.md`) and the research file (`[slug]-05-research.md`). Write the introduction and overview only if the user asks for the booklet.

## Shared format

Every file starts with the same frontmatter:

```markdown
---
title: "Phase 1: What a number does and does not tell you"
curriculum: "Statistics"
type: chapter
order: 10
date: 2026-11-02
---
```

`type` is one of: `introduction`, `overview`, `research`, `chapter`, `next-steps`.

Then:
- One `#` heading per file, equal to the title. Below it `##` and `###`.
- Plain Markdown. No Obsidian wikilinks (`[[...]]`), no callouts, no HTML. Then Pandoc can convert it later without problems.
- Source references as `[B07](link)` right next to the claim, with the ID and the link from the sources file. In the research file, `[B07]` without a link is fine, because the source list is right below it.
- **Writing.** Before you write a text, load the skill `plain-writing`, or another skill for clear writing, if one is available, and follow it. Where that skill and this file differ on structure or delivery, follow this file: it says when you deliver a file and when you ask about an EPUB. If there is no such skill, follow these rules: short sentences, active voice, plain words, no dashes between clauses. This applies to all texts in this file, not to the cards.

## The introduction

About 300 to 500 words:
- why the user is learning this subject (the goal from the intake, in the user's own words)
- the end tasks
- the scope: what is in the track and how deep, and what is out
- the structure in phases, in one paragraph
- how the track worked: black box, trying first, teach-back, cards

At the end of the track, rewrite the introduction so it matches how things really went.

## The overview

One table per phase: number, part, target level, what it does, status. Below it the end task of the phase. After the tables: the level 1 topics without a part of their own, and what is out of the track. At the top: duration, weekly effort (or total time for a short track), start and end date.

## The research file

Take the three parts from the sources file: research map, search log, source list. Turn them into readable text, but don't change the content. This file must allow a subject expert to check and repeat the background research.

## The chapter

A chapter is reference material that a reader can check. The evidence comes from sources you opened. The user's experience (teach-back, example, pitfalls) shows how the user understood it and makes it concrete. That experience does not replace the evidence. A reader who reads only the first sentence of each paragraph must know what the part does, what the research says about it and how strong that evidence is.

Write it at the end of a phase, after the phase end task (if there is one). Read the log (core wording, hint levels, gaps) and the sources file first.

**Preparation, before you write**
1. For each part, list the claims the chapter will make: what it does, when it does not work, and, at level 3 or 4, why it works. The chapter goes as deep as the target level. Whatever lies deeper goes under "Further reading".
2. For each claim, search for a source and open it. Start with the primary source that the research map or the design document mentions. A figure or conclusion that you only know from the design document or from a summary does not count as support.
3. Add each new source to the sources file and each search to the search log first. Only then use the source in the text.
4. If you cannot open a source for a claim, choose: leave the claim out, write it as a "design choice of the skill" (with that label, supported by the design document), or put it under "What is still open". A source you could not open may at most appear under "Further reading", with the sentence "mentioned in [Bnn], not opened".
5. If a part has no opened source at all, tell the user before you deliver the chapter.

**Building blocks, one `##` section per part, in this order:**
1. **What it does.** The black box, in one paragraph.
2. **What the research says.** One paragraph per claim. Name what was found, the source with a link, the type of study and the number of studies or participants, the effect (measure, value, comparison and uncertainty, as far as known) and the limit: for whom and under which conditions. Name contradictions between sources. End with one sentence on how strong the evidence is together and what has not been researched, such as the combination of elements in the skill.
3. **How the skill applies it.** The rules of the skill, briefly. Make the difference clear between "the research says" and "the skill chooses". Design choices refer to the design document.
4. **In your own words.** The core wording from the user's teach-back, as a quote or a short block. The user's wording appears only here, not in sections 2 and 3. If it differs from what the sources say, say so in one sentence.
5. **Example.** The problem from the session and how it was solved, as a worked example.
6. **Pitfalls.** The gaps where the user got stuck, plus misconceptions from the sources. A gap from the session is not a fact about the world: say "in the session" and draw no general conclusion from it.
7. **Connections.** How this part relates to the others.

**Then, per phase:**
- **`## End task`:** the task and how the user approached it. Leave it out if the phase has no end task.
- **`## What is still open`:** what the research does not answer or what you could not open.
- **`## Further reading`:** depth and related subjects. Per item one sentence on why it is worth it, and a source.
- **`## Sources`:** all sources the chapter refers to, with ID, full reference and link.

**Check before you deliver**
- Every factual sentence in sections 1 to 3 has a source reference with a link, or is labelled as a design choice.
- You opened every source mentioned, and it is in the sources file.
- Sections 2 and 3 together are at least as long as sections 4, 5 and 6 together. Otherwise the chapter reads as the user's story with sources attached, and that is not the intention.
- A reader who does not know the user can trace every claim to a source.

**Length.** About 400 to 700 words per part; for a part at level 2, the shorter end.

Deliver the chapter as a downloadable file (see `platform.md`) and put it in the status file under "Texts".

## Next steps

At the end of the track: write out the section "Next steps and broadening". Per item: what it is, why it is a logical next step, and where to start (with a source). End with a short look back: what went fast, what took more time than planned.

## The booklet

The user asks "make the booklet" and attaches the `.md` files. The content of the texts is not in storage, so without attachments you cannot make the booklet; ask for them in that case.

1. Read all attached files and sort them by `order`. Files from the Dutch version of this skill use `titel` and `volgorde` instead of `title` and `order`; read those too.
2. Check what is missing compared with the status file (for example a chapter of a finished phase). Name it and ask whether to continue without it.
3. Build one Markdown file:
   - title block with curriculum, author and date (ask for the author's name if it is not known)
   - table of contents
   - the files in order, without their own frontmatter
   - appendix **Methods**: the research map and search log from the sources file
   - appendix **Sources**: the complete source list from the sources file, by ID
4. Check that every `[Bnn]` in the text is in the source list.
5. Deliver it as `[slug]-booklet.md`.
6. Ask: "Do you also want an EPUB?"

**EPUB.** Use Pandoc. If it is not in the environment, try to install it (`pip install pypandoc_binary`). Some environments have no internet; then that fails. Set the title and author as metadata, make a table of contents, and deliver `[slug]-booklet.epub`. If it does not work in this environment, say so and give the Pandoc command, so the user can run it themselves.
