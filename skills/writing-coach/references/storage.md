# Storage: status, sources and draft

Everything that must survive a conversation lives in two files per writing project, plus the draft. The format is the same on every platform, so the user can move a project. Where the files live differs per platform (see `platform.md`).

| File | Contents | Read |
| --- | --- | --- |
| `writing-[slug].md` | brief, budget, point, own material, sub-questions, outline with status per paragraph, content check, decisions, next step, log | every session |
| `writing-[slug]-sources.md` | research cards, search log, research summary per sub-question | for research, outline, drafting, fact check |
| the draft | the text itself | when the user shares text, for revision and polish |

`[slug]` is a short project name in lowercase with hyphens: `async-decisions`, `annual-report-2026`.

## Format of the two files, on every platform

- Frontmatter with `name` (equal to the file name without `.md`), `description`, `sources` and `aliases`.
- Every content line starts with `- [stated]`. Headings without a tag are allowed. Memory in the Claude apps requires this; on other platforms you keep it so the files stay portable.
- No sensitive personal data. If a text is about something personal or medical, keep only the writing status in these files.
- Keep the draft out of these files. It is too long, and it lives where the user can edit it (see `platform.md`).

## Rules for memory with files

These apply when you have memory tools, as in the Claude apps. The tool names are Claude's; if your memory uses other names, use the tool that does the same thing.

- **Where.** Find existing projects by file name (`writing-*.md`), wherever they are in memory. For a new project, follow the structure the memory already has, for example a folder `/areas/`. If there is no structure, use the root.
- **Read first, then write.** Use the version from the read as `if_version`. You don't need to reread a file you wrote in this conversation.
- **Small change:** `memory_str_replace`. New source card or log line: `memory_append`. Only when creating or restructuring: `memory_write`, with all existing lines.
- **Conflict.** If another device changed the file, merge and try again. Never overwrite what another device wrote.
- **Full.** Sources: start `writing-[slug]-sources-2.md` and note it in the status file. Status: shorten the log to one line per week.
- **Refused write:** say so in one sentence and give the content in a code block.

## Status file

```markdown
---
name: writing-async-decisions
description: Writing project opinion piece on writing before meetings; brief, point, outline, status per paragraph
sources: [chat]
aliases: [async decisions article]
---

## Brief
- [stated] Kind: opinion piece; reader: team leads at mid-sized companies who meet weekly and think that is normal
- [stated] Length: about 1,200 words; channel: LinkedIn article; deadline: 2026-11-10
- [stated] Way of working: user writes outline and every paragraph first; proposals on request; coach does research, feedback, polish and content check

## Budget
- [stated] Words: 1,200, target (not a hard limit); opening ~120, close ~120, body 6 to 9 paragraphs
- [stated] Time: 6 hours until 2026-11-10, in 4 sessions of 90 min; fixed steps 2 hours
- [stated] Pace: starting guess 20 to 45 min per paragraph; measured: not yet (after 3 paragraphs)

## Point
- [stated] Point: Teams make better decisions when everyone writes a page first and meets after
- [stated] Own material: two teams at clients; one reversed decision; quiet team members rarely speak up; cost in hours

## Sub-questions
- [stated] DV1 Why do decisions in meetings go wrong? · both · research done (R1-R3)
- [stated] DV2 What does writing first change? · both · research done (R4-R6)
- [stated] DV3 Strongest objection: it costs time · own experience
- [stated] DV4 How do you start without extra work? · own experience

## Outline
- [stated] Outline approved by user: 2026-10-25, after 3 rounds
- [stated] 1 Opening · core: Your team meets weekly and reverses decisions a month later · ~120 w · status: done
- [stated] 2.1 · core: Meetings reward whoever speaks first · ~140 w · status: feedback, round 2; proposal asked · sources: R2
- [stated] 3.1 · core: Writing costs time, so limit it to one page and decisions that are hard to reverse · ~130 w · status: open

## Decisions
- [stated] 2026-10-25: point narrowed to decisions that are hard to reverse, after R5

## Content check
- [stated] 2026-11-05: 2.1 "meetings reward whoever speaks first" plausible, R2 is about students; user added the population
- [stated] 2026-11-05: assumption that teams have time to read before the meeting; user added a line on 15 minutes reading time

## Next step
- [stated] User refines 2.1 after round-2 feedback, then writes 3.1

## Log
- [stated] 2026-10-24: intake, budget, point, sub-questions; research started · 70 min
- [stated] 2026-10-25: outline approved after 3 rounds; paragraph 1 done, 2.1 in progress · 85 min
```

## Sources file

```markdown
---
name: writing-async-decisions-sources
description: Research cards and search log for the writing project on writing before meetings
sources: [chat]
aliases: [async decisions sources]
---

## Summary per sub-question
- [stated] DV1: [two or three lines: what the evidence says, how strong, what is missing]

## Research cards
### R1 · DV1
- [stated] Finding: ...
- [stated] Source: ...
- [stated] Type: ...
- [stated] Who: ...
- [stated] Size: ...
- [stated] Limits: ...
- [stated] Checked: ...
- [stated] Relation: ...

## Search log
- [stated] 2026-10-24 "meeting decision quality speaking order" · two relevant studies, one meta-analysis
```

The research card format and its rules are in `research.md`.
