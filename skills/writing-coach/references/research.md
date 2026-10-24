# Background research

This file covers Phase 4. Research runs in the background while the user works on the outline. The result is a set of research cards in the sources file: one card per finding, each with a source that was opened.

## When to start

Start as soon as the sub-questions pass (Phase 3). Research every sub-question marked "outside sources" or "both". If the user adds a sub-question later, start research for that one only.

Don't research before the user's own material is saved (Phase 2, step 4). The user's view goes on paper first.

## How to run it in the background

See `platform.md` for what your platform allows. In order of preference:

1. **A background agent** (for example the `Agent` tool with `run_in_background` in Claude). Start one agent per two or three sub-questions, with the brief below. Continue with the user while they run. When an agent reports back, check its cards and add them to the sources file.
2. **Research between turns.** Without agents, do the research yourself in one turn. Tell the user first what you are researching and give them a task for the outline that they can do in the meantime.
3. **No web access.** Say so. Mark the sub-questions as "not researched" and ask the user to add sources they know.

## Brief for a research agent

Give the agent everything it needs, because it starts without the conversation:

```
You research sources for a writing project. Do not write any text for the article.

Project: [title]. Kind: [report / informative article / opinion piece].
Reader: [reader from the brief].
Point or main question: [sentence].

Sub-questions to research:
- [DV1] [question]
- [DV2] [question]

For each sub-question, find the best available evidence, both for and against
the point. Rules:
- Open every source you cite. Never cite from memory or from a search snippet
  alone. If you could only read a summary, say so.
- Prefer, in this order: systematic reviews and meta-analyses; randomised or
  controlled studies; large surveys and official statistics; reports from
  recognised institutions; practice guides by named experts. News and blogs
  only to find the original source, which you then open.
- Prefer sources from the last ten years. Older work is fine if it is still the
  standard reference; then look for newer work that confirms or contradicts it.
- For a Dutch reader and a Dutch context, also look for Dutch sources and data.
- Record who was studied, how large the effect or number is, and the limits.
- Mark preprints as preprints.
- Report findings that contradict the point as clearly as findings that support it.

Return:
1. Research cards in the format below, one per finding.
2. A search log: each query, and in one line what it gave.
3. Per sub-question, two or three lines: what the evidence says, how strong it
   is, and what is missing.
```

## Research card

Every finding becomes one card in the sources file:

```markdown
### R3 · DV2
- [stated] Finding: writing about subject matter improved learning; small effect
- [stated] Source: Graham, Kiuhara & MacKay (2020). The effects of writing on learning in science, social studies, and mathematics: A meta-analysis. Review of Educational Research, 90(2). https://doi.org/10.3102/0034654320914744
- [stated] Type: meta-analysis, 56 experiments
- [stated] Who: pupils aged 6 to 18, school subjects
- [stated] Size: effect size 0.30 (small)
- [stated] Limits: school pupils, not professionals; learning of content, not writing quality
- [stated] Checked: abstract opened 2026-10-24; full text not read
- [stated] Relation: supports DV2
```

Field rules:
- **Finding** in your own words, one sentence. No quotes longer than a few words.
- **Source** with a DOI or a direct link to the original wherever there is one.
- **Checked** says what was actually opened: full text, abstract, or only a summary by someone else. A card without "Checked" is not usable in the text.
- **Relation:** supports, nuances or challenges, plus the sub-question or the point it concerns.

## After the research

1. Check each card yourself: does the link work, does the source say what the card says? Remove or mark cards you cannot confirm.
2. Add the cards and the search log to the sources file.
3. Tell the user per sub-question in two or three lines what was found and how strong it is. Give the full cards only when they ask or when they write that paragraph.
4. If a card challenges the point, a sub-question or the user's own material, say so first, and ask what the user wants to do: adjust the point, add the objection to the outline, or narrow the claim.
5. If nothing good was found for a sub-question, say so. Options: rely on the user's own experience and say that in the text, narrow the sub-question, or drop it.

## Rules for using sources in the text

- Use a source only for what it says, and say who was studied when that differs from the reader's situation.
- Give the size of an effect in words the reader understands (small, medium, large), with the number.
- Put the link right after the claim, and add the source to the list at the end.
- A preprint is named as a preprint. An old source gets a line on whether newer work confirms it.
