# Changelog

Every commit to `main` reaches users on their next sync, so each entry is dated rather than versioned.

## 2026-10-25

### Changed

- `active-learning`: the curriculum now has a step for scope and depth. The intake first asks for your goal. Together you decide what is in and out of the track, and set a level per topic on a pyramid of four: overview, use, inside, build it yourself. Each topic gets the lowest level your end tasks need; level 4 is always offered. Sessions, teach-backs, cards and chapters stop at that level, so a concept you only need to use no longer takes sessions to explain.
- `active-learning`: the coach starts every part with a black box, also before a worked example. After an error, you explain your own step with a targeted question. The coach asks one fitting question at a time and drops support per step, names the kind of gap and lets you choose a next learning action, matches the check to the kind of reasoning, and labels additions as research, practice or a choice of the track. A question the coach gives counts as help; far transfer is recorded separately and does not undo "learned".
- `active-learning`: parts are never renumbered, a dropped part gets the status `dropped`, and new parts get a short prior knowledge test first. The status file keeps agreements about how the coach works and says when it was rebuilt from a summary. Each source records what was read.
- `active-learning`: DESIGN.md and the README no longer cite the self-explanation meta-analysis as support for the teach-back, and give a more careful account of the AI tutor studies, with a recent counter-finding.

## 2026-10-24

### Added

- `writing-coach`: a writing coach for reports, informative articles and opinion pieces you write yourself. Asks for a budget in words or time first, which sets the size of the outline. The time per paragraph starts from your writing experience, based on research on writing speed, and switches to your measured pace after three paragraphs. Guides you from your point and sub-questions to an outline and every paragraph, with feedback loops you end yourself. Researches in the background with source cards you can check, and ends with a polish by `plain-writing` and a content check of your positions and conclusions.

### Changed

- `plain-writing`: the description now sends coaching on a text you write yourself to `writing-coach`.

## 2026-10-22

### Added

- `business-storytelling`: turn business content into a persuasive story for a pitch, keynote, proposal or case study, with SCQA, Monroe's Motivated Sequence, Duarte's Sparkline, the Hero's Journey and the SUCCESs checklist. Missing facts become visible placeholders instead of invented numbers. Uses `plain-writing` for the sentences when it is installed.
- `design-taste`: design judgement for pages, app screens, slides and documents. Names the default a model would ship, chooses the least typical direction that still fits the subject, and critiques the rendered result. Based on a meta-analysis of Impeccable, Taste Skill and research on aesthetic judgement; Markdown only, no scripts.
- `ia-presenter`: write presentations for iA Presenter as one Markdown file, with the script as speaker notes and only what the audience must see on the slides.
- `mobile-pdf`: turn Markdown or another document into a narrow PDF with large text, for reading on a phone.

## 2026-10-21

### Added

- `active-learning`: a learning coach built on learning research, for a track of a few hours to several months. Help that fits the learning goal, proof of learning with a teach-back, flashcards for Active Retrieval or Anki in your own words, planning with your measured pace, and a booklet with checked sources.
- `plain-writing`: write and edit clear reports, summaries, memos and other informative texts in Dutch or English.
- ZIP downloads for every skill, to upload in the Claude or ChatGPT app. A new release with fresh ZIP files follows every change to a skill.
