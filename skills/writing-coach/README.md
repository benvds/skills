# writing-coach

A writing coach for reports, informative articles and opinion pieces that you publish or hand in under your own name. You write the text; the coach asks, checks, researches and gives feedback. It hands you the work that doesn't need your judgment: background research, a proposal when you are stuck, and the final polish. [DESIGN.md](DESIGN.md) gives the reasons and the sources for each choice.

It doesn't activate for texts you want written entirely for you (use [plain-writing](../plain-writing/README.md)), pitches and persuasive stories (use [business-storytelling](../business-storytelling/README.md)), fiction, marketing copy or social media posts.

## The method

**1. Budget first.** The coach asks for a budget in words, time, both or none, before anything else. A word budget sets how many sections and paragraphs fit, and gives every paragraph a word target. A time budget gets a reality check: the work split into steps, a range per paragraph, planned back from your deadline, and three lists of what fits, almost fits and is out of reach. After three paragraphs, your measured pace replaces the starting guess.

**2. Your point before any source.** You write the point in one sentence, or the main question of your report, and list in keywords what you already know and think. That goes on paper before research can steer it.

**3. Sub-questions that carry the point.** You split the main question into sub-questions that are each needed and together sufficient. In an opinion piece, the strongest objection is always one of them, because answering it persuades more than ignoring it.

**4. Research in the background.** While you work on the outline, research runs per sub-question. Every finding becomes a card with the source, the type of study, who was studied, the size of the effect and what was actually opened. The coach cites nothing it hasn't opened, and tells you first when a finding contradicts your point.

**5. Outline and paragraphs as loops.** You write the outline: headings, one core sentence per paragraph that states a claim, and a word target. Then every paragraph. After each attempt you get at most three points of feedback, big before small, ending with one next step. You decide when it is good enough. A proposal comes only when you ask, marked as one, for you to make your own.

**6. Polish and content check.** The coach polishes the sentences with [plain-writing](../plain-writing/README.md), without touching your claims. It also labels every main position as well supported, plausible, contested or unsupported, names the assumptions you don't state, and flags conclusions that claim more than the evidence carries. You decide what to do with each point.

## What this is not

The research supports the elements one by one, and most of it was done with pupils and students. No study tested this combination. Several choices are practice rules, and DESIGN.md marks them as such, including the sizes in the budget.

## In practice

- **Sessions.** One question per turn. When you come back, the coach says in two or three lines where the project stands and what the next step is.
- **Status.** The brief, budget, outline with the status per paragraph, content check and log live in a status file, and the research cards in a sources file. Where they live depends on the platform: memory in the Claude apps, a Project in ChatGPT, or `.writing-coach/` in your working folder in Claude Code.
- **The draft** lives where you can edit it: a document, a project file or a Markdown file in your working folder.
- **Delivery.** A Markdown file with a source list at the end, and an EPUB if you want one. Before you publish, the coach suggests one reader from your audience who says where they lost interest and what they think the point is.

## Example

> **You:** Help me write a LinkedIn article on why teams should write before they meet.
>
> **Coach:** *(after the questions about kind, reader and channel)* What is your budget: a number of words, the time you have, both, or none?
>
> **You:** About 1,200 words.
>
> **Coach:** That is room for 6 to 9 paragraphs, so three or four sections. Now your point: what should a team lead believe after reading? Say it in one sentence you could say out loud.

## What it needs

- **[plain-writing](../plain-writing/README.md)** for the feedback on sentences, the proposals and the polish. Install it too. Without it, the coach uses its own shorter list of sentence rules.
- **Web search** for the background research. Without it, the sub-questions are marked as not researched and you add the sources you know.
- **Storage:** memory files, a ChatGPT Project or a working folder. Without storage, it gives the status files as code blocks after every session.

## Opinions you may not share

This skill takes positions. Change them in [SKILL.md](SKILL.md) or the files in [references/](references/) if they don't suit you.

- You make the first attempt at the point, the questions, the outline and every paragraph. The coach doesn't write the whole outline, even when you are stuck; it offers options for the part you are stuck on.
- You end every feedback loop, not the coach. It names a remaining problem once and accepts your decision.
- At most three points of feedback per round.
- The strongest objection is always part of an opinion piece.
- The budget is asked before anything else, and a paragraph is about 100 to 150 words.
- A source is cited only when it was opened, and the card says what was opened.
- In Dutch, the coach says *je*, not *u*.

## Works well with

- [plain-writing](../plain-writing/README.md), which it uses for the sentences and the polish.
- [business-storytelling](../business-storytelling/README.md) when the text has to persuade a specific audience, such as a pitch or a proposal.
- [mobile-pdf](../mobile-pdf/README.md) to read your draft on your phone.
