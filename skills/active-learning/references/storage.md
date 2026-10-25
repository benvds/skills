# Storage: status, log and sources

Everything that must survive a conversation lives in three files per track. The format is the same on every platform, so the user can move a track. Where the files live differs per platform (see `platform.md`).

| File | Contents | Read |
| --- | --- | --- |
| `learning-[slug].md` | track, scope and depth, curriculum, status, pace, texts, next steps | every session |
| `learning-[slug]-log.md` | complete log of all sessions | for chapters, progress, adjusting, retrieval from another conversation |
| `learning-[slug]-sources.md` | research map, search log, source list | for texts, new research, checks |

`[slug]` is the curriculum name in lowercase with hyphens: `statistics`, `product-discovery`.

## Tracks from the Dutch version

Earlier versions of this skill used Dutch file names, keys and statuses. Read those files as they are and keep writing in the same names and words, so the track stays consistent. Don't rename an existing track unless the user asks.

| English | Dutch |
| --- | --- |
| `learning-[slug].md` | `leren-[slug].md` |
| `learning-[slug]-log.md` | `leren-[slug]-logboek.md` |
| `learning-[slug]-sources.md` | `leren-[slug]-bronnen.md` |
| `open`, `in-progress`, `learned` | `open`, `bezig`, `aangeleerd` |
| `apply later` / `applied later` | `later toepassen` / `later toegepast` |
| `level 1 overview`, `level 2 use`, `level 3 inside`, `level 4 build` | `niveau 1 overzicht`, `niveau 2 gebruiken`, `niveau 3 vanbinnen`, `niveau 4 zelf opbouwen` |

## Format, on every platform

- Frontmatter with `name` (equal to the file name without `.md`), `description`, `sources` and `aliases`.
- Every content line starts with `- [stated]`. Headings without a tag are allowed. Memory in the Claude apps requires this; on other platforms you keep it so the files stay portable.
- No sensitive personal data. If a track is about something personal or medical, write only the learning status.

## Rules for memory with files

These rules apply when you have memory tools, as in the Claude apps (see `platform.md`). The tool names below are Claude's. If your memory uses other names, use the tool that does the same thing.

- **Where the files are.** Find existing tracks by file name (`learning-*.md`, or `leren-*.md` from the Dutch version), wherever they are in memory. For a new track, follow the structure the memory already has, for example a folder `/areas/`. If there is no structure, put the files in the root.
- **Read first, then write.** Read the file and use the version from the read as `if_version`. You don't need to reread a file you already wrote in this conversation.
- **Small change: `memory_str_replace`.** To add a line to the log or source list: `memory_append`. Only when creating or restructuring a file: `memory_write`, with all existing lines in it.
- **Conflict.** If the user worked on another device in the meantime, memory reports a version conflict with the current content. Merge your change with what is there and try again. Never overwrite what another device wrote.
- **Full.** Memory reports when a file is almost full. Log or sources: start a second part (`-log-2`, `-sources-2`) and note in the status file where the continuation is. Status file: summarise finished phases into one line per phase.
- **If memory refuses a write:** say so in one sentence and give the content in a code block.

## Rules for a Project, a working folder or no storage

See `platform.md`. In short:
- **Working folder:** read and write the files in `.active-learning/[slug]/`. Reread a file before you overwrite it.
- **Project or no storage:** read the files from the Project, the attachments or the message, and at the end of the session deliver the changed files. Because the user replaces them, always deliver the complete file, never a fragment.

## Status file

```markdown
---
name: learning-statistics
description: Learning track statistics with active learning; end tasks, curriculum, status per part, open gaps
sources: [chat]
aliases: [learning statistics]
---

## Track
- [stated] Goal: judge for myself whether the conclusion of a report holds, without relying on the summary
- [stated] End tasks: read a research report and assess its conclusion; ...
- [stated] Anchor source: none
- [stated] Duration: 8 weeks, 2026-10-17 to 2026-12-12; 2-3 sessions per week of 30 min, Tue and Thu 20:00
- [stated] Weekly budget: 120 min; reviewing reserved 30 min; measured reviewing: not measured yet
- [stated] Cards: Active Retrieval; deck "Statistics" 📊
- [stated] Pace: correction factor not measured yet (after 3 parts)

## Scope
- [stated] Depth: 01 level 3, you must see for yourself why a sample can be skewed; 02 level 2, using it is enough; 03 level 2, reading it correctly is enough; 04 level 2, reading it correctly is enough
- [stated] Level 1, no part of its own: t-test (phase 1 table)
- [stated] Level 4 offered: simulating a p-value; not chosen
- [stated] Out: calculating tests yourself, no end task needs it; regression, outside the end tasks

## Curriculum
### Phase 1: What a number does and does not tell you
- [stated] 01 Sample and population · understanding · level 3 inside · route A: learned 2026-10-17 in 1 session (estimate 1-2); independent yes; apply later open; cards statistics-01-01 to 05
- [stated] 02 Spread · procedure · level 2 use · fast route: learned 2026-10-19 in 0.5 session (estimate 0.5-1); independent yes; applied later 2026-10-28; cards statistics-02-01 to 03
- [stated] 03 p-value · understanding · level 2 use · route A: in-progress, 2 sessions so far (estimate 1-2); independent no; gap: confuses p with the probability that H0 is true
- [stated] 04 Confidence interval · understanding · level 2 use: open; estimate 1-2
- [stated] End task phase 1: assess report X; open; estimate 1
- [stated] Assessment list end task phase 1: conclusion named; p-value interpreted correctly; essential error: p as the probability of H0; help: no hints

## Texts
- [stated] 00-introduction, 01-overview, 05-research delivered 2026-10-17

## Next steps and broadening
- [stated] Follow-up curriculum: regression and calculating tests yourself, out of the track
- [stated] Could add: Bayesian statistics
```

**Short track:** the duration line gives the total time instead of sessions per week, for example `- [stated] Duration: short, 120 min on 2026-10-21; two blocks with a break`. There is no weekly budget line.

**Cards:** the spaced repetition app and the deck name. For Anki, without an emoji: `- [stated] Cards: Anki; deck "Statistics"`.

**Scope:** the reason for each target level, the level 1 topics without a part of their own, which level 4 was offered and whether it was chosen, and what is out of the track, with the reason. Keep each reason to a few words: it is needed when a level is reconsidered later.

**Existing track without levels:** at the next session, propose a target level for the open and in-progress parts, in one question, and add the levels and the Scope section. Learned parts keep their status.

**Per part:** learning goal type, target level, route, status, sessions, estimate, independent yes/no, "apply later" (open, or the date of a successful application), open gap, card IDs.

**Statuses:** `open`, `in-progress`, `learned`. With `in-progress` come the sessions so far and the open gap, if there is one. With `learned` come the date, the actual number of sessions and the card IDs. The estimate stays, so you can measure the difference. "Learned" means the first learning phase is done; "applied later" shows whether it stuck.

## Log

The log is complete: every session, every curriculum change. Nothing is summarised or thrown away.

```markdown
---
name: learning-statistics-log
description: Complete log of the learning track statistics, per session
sources: [chat]
aliases: [statistics log]
---

- [stated] 2026-10-17 · start · intake, test: 01 mastered, 02 partly, rest new; curriculum confirmed
- [stated] 2026-10-17 · 01 · session 1 · fast route, learned · teach-back: "a sample tells you something about the population if ..." · cards made, 5
- [stated] 2026-10-19 · 03 · session 1 · route A · solved at hint level 3 · independent task failed · gap: confuses p with the probability that H0 is true
- [stated] 2026-10-21 · change · 04 split into 04a and 04b; reason: too large for one session
- [stated] 2026-10-24 · change · 03 target level 3 → 2; reason: the end task only needs reading p-values correctly
- [stated] 2026-10-28 · pace · after 3 parts: 4.5 sessions measured against 4 estimated (midpoint); correction factor 1.1
```

One line per session: date, part, session number within that part, route, what happened, whether the independent task succeeded, hint level, core of the teach-back (one or two sentences, in the user's words), gap. The teach-back core is needed to make cards or a chapter later from another conversation. The session number is needed to measure the pace.

## Sources file

This file must be complete enough for a subject expert to check and repeat the background research. The example below only shows the form; its content and source B03 are made up.

```markdown
---
name: learning-statistics-sources
description: Research map, search log and source list of the learning track statistics
sources: [chat]
aliases: [statistics sources]
---

## Research map (2026-10-17)
- [stated] Black box: statistics tells you how sure you can be about a group based on part of it
- [stated] Insight: ... [B03]
- [stated] Misconception: ... [B03]
- [stated] Learning: ... [B05]
- [stated] Contradiction: B04 and B05 differ on ...; B05 is more recent and larger
- [stated] Status: checked with search

## Search log
- [stated] 2026-10-17 · "statistics misconceptions meta-analysis 2025" · 10 results, 2 used (B03, B04)
- [stated] 2026-10-17 · "learning statistics instruction study" · 10 results, 1 used (B05)
- [stated] Selection: recent work first; meta-analyses and reviews, then guidelines from institutions, then experiments, then handbooks; blogs only as practice
- [stated] Retraction check: B03 checked, no correction found

## Sources
- [stated] B03 · Author, A. (2023). Title of the article. Journal, 12(3), 45-67. https://doi.org/... · type: meta-analysis · peer-reviewed: yes · accessed 2026-10-17 · supports: research map, part 03
```

**Source rules:**
- IDs run on: B01, B02, ... An ID never changes.
- Full reference: authors, year, title, journal or publisher, DOI or link to the primary source.
- `type`: meta-analysis, systematic review, guideline, experiment, handbook, documentation, standard, preprint, practice.
- `peer-reviewed`: yes, no, or n/a (for a standard or documentation).
- `accessed`: the date you opened the source.
- `supports`: where the source is used. Extend this when the source is used again later.
- Only sources you actually opened. A source from your own knowledge that you could not open does not go in.
- Every new search in a session or for a chapter also goes into the search log.
