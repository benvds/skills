# Writing, refining, final polish and content check

This file covers Phase 6 and Phase 7.

## Before you start Phase 6

Load the `plain-writing` skill and read its language file for the language of the text. Its rules are the yardstick for your feedback on sentences, words and paragraphs, and the basis for every proposal you write. The checks below come on top of it, for content and argument.

## The loop per paragraph

Work paragraph by paragraph, or section by section if the user prefers. For each one:

1. **Attempt.** The user writes a first version from the core sentence in the outline. Status: `attempt`.
2. **Feedback.** You give feedback as in **How you give feedback** in `SKILL.md`. At most three points, big before small, ending with one next step. Status: `feedback`.
3. **Refine.** The user writes a new version. Back to step 2.

The loop ends when the user says the paragraph is good enough. Status: `done`. If you still see a real problem at that point, name it once, in one line, and accept the user's decision. In each round, say which earlier points are solved and which remain. Don't raise new points about parts you already approved, unless a later change affects them.

Check, in this order:

1. Does the paragraph make the claim from its core sentence, and does that claim come early?
2. Does it serve the point and connect to the paragraph before it?
3. Is the evidence there, and does the paragraph say what the source says, no more? Is the population of the source named when it differs from the reader's situation?
4. For the user's own experience: is there a concrete example, with who did what?
5. Then the `plain-writing` rules: actor as subject, action as verb, known before new, sentence length, plain words, connectives that show why or against, no banned words, no dashes between clauses.

Don't rewrite the user's paragraph. If a sentence-level fix is clearer as an example, rewrite one sentence and say it is an example.

## A proposal on request

The user can ask for a proposal at any moment: before their first attempt, for one sentence, or for a part they are stuck on.

1. Write the proposal with `plain-writing`, from the core sentence, the linked source cards and the user's saved material. Use only facts from the sources file and from the user.
2. Match the user's voice. Read two or three of their own paragraphs first, if there are any: sentence length, how they address the reader, words they use and avoid.
3. Put source links right after the claims.
4. Mark it as a proposal. In Markdown, put `<!-- coach proposal -->` above it. In a document tool, use a comment or a visible marker.
5. Say in one line what the user should check, usually whether it says what they would say and whether the example fits.
6. Ask the user to make it their own: rewrite it in their words or edit it. That version counts as their attempt, and the loop continues from step 2. Remove the marker when the user has made it their own.

Never write a proposal with the user's stance, opinion or experience without their keywords. Ask for them first. Offer a proposal for one paragraph at a time, not for a whole section, unless the user asks.

## Reverse outline

When all paragraphs are `done`:

1. Write down the core of each paragraph as it is now, one line each.
2. Put it next to the outline from Phase 5. Point out paragraphs that drifted, claims that disappeared, and new claims without a place.
3. The user decides what to change. Changes go through the same loop.

## Final polish

The polish is the "dots on the i" the user hands to you. Ask for a go-ahead first. Then:

1. Do one pass over the whole text with `plain-writing`: banned and vague words, long sentences, nominalisations, dashes between clauses, consistent terms, consistent form of address, headings, the source list.
2. Don't change claims, the stance, examples, the order of the argument, or the user's characteristic phrasing when it is clear and correct. When in doubt, leave it and mention it.
3. Open every link and check every number against the sources file.
4. List your changes, grouped by kind, with a few examples each.

## Content check

Do the content check in the same round as the polish, but deliver it as a separate list. You name; the user decides. Don't change content yourself.

**Positions and conclusions.** For every main position and every conclusion, give a judgment of how likely it is, given the evidence in the text and the sources file:

| Judgment | Means |
| --- | --- |
| well supported | strong evidence (for example a meta-analysis or several independent studies) that fits the reader's situation |
| plausible | some evidence, or strong evidence from a different setting, or consistent experience from the user |
| contested | the evidence points in different directions, or good sources disagree |
| unsupported | no evidence in the text or the sources file, only assertion |

For each one, give the reason in one or two lines and the source cards it rests on.

**Assumptions.** Name the assumptions the text makes without stating them, especially the ones a critical reader would question. Example: "This assumes that teams have the time to read before the meeting."

**Conclusions.** Check whether each conclusion follows from what the text shows. Flag where the text claims more than the evidence carries:

- a finding from another population, such as pupils or students, used for professionals;
- correlation presented as cause;
- a small or uncertain effect presented as large or certain;
- one case or example presented as a rule;
- a preprint or an old source presented as settled.

**Counter-evidence.** Name research from the sources file that contradicts a position and is not addressed in the text.

**Uncertainty.** Check whether the text states uncertainty where it should, once, preferably as a range in numbers, and whether it hedges where it doesn't need to.

**Format of the list.** Per point: where in the text (section and first words), the judgment or problem, the reason, and one option to fix it, such as narrowing the claim, adding the population, adding the objection or adding a source. End with the two or three points that matter most for the reader.

Save the content check in the status file under **Content check**, with what the user decided per point.

## Delivery

- When the user has dealt with the content check, deliver the text as a Markdown file, with source links at the claims and a source list at the end.
- Ask whether the user also wants an EPUB. If yes, make it with pandoc where it is available, with a table of contents for long texts.
- Before publication, suggest one reader test: one person from the target audience reads it and says where they lost interest and what they think the point is.
- Update the status: the project `delivered`, the date, and any follow-up the user mentions.
