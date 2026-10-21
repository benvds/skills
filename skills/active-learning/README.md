# active-learning

A learning coach built on learning research. You don't read explanations and hope they stick: you work on the material yourself, show that you can do it, and keep it with spaced repetition. Each step in the method follows a known finding, and [DESIGN.md](DESIGN.md) gives the source for each one.

Use it when you want to learn a subject, not just get an answer. A track lasts from a few hours to several months.

It doesn't activate for a single question or explanation, homework answers, flashcards from existing notes, or a course that someone else will teach.

## The method

**1. Start from what you want to be able to do.** The curriculum starts with concrete end tasks in the form "I can ...", not with a level such as "beginner". Planning back from the result is called backward design. A short test of your prior knowledge decides where you start. Questions asked before you learn something help you learn it, even when you answer them wrongly.

**2. Get help that fits the goal.** In a meta-analysis of 53 studies, trying a problem before the explanation helped understanding and transfer (g = 0.36), but not procedural knowledge. So the coach chooses per part:
- **Understanding, with enough basis:** you try first and get hints, not answers. The explanation then builds on your own attempt. In the same meta-analysis, the effect was larger when the explanation built on the learners' own solutions (g = 0.56 against 0.20).
- **Procedures, skills or a missing basis:** you start with a worked example, then finish a partly worked task, then do one alone. The help disappears as soon as you can do it alone, because help that supports beginners holds back people who already know the material.

**3. Prove that you can do it.** Feeling that you understand something is a poor measure, and performing with help is not the same as learning. A part counts as learned only when you have solved a task without hints, explained it in your own words, and answered a "what if" question with the right reason. Explaining it yourself had a medium effect in a meta-analysis (g = 0.55). Later, the part comes back as an application, to check that it stuck.

**4. Make cards only after that, in your own words.** First understand, then memorise. The answers on your cards come from your own explanation; in experiments, self-made cards gave better learning than ready-made cards. The coach checks each answer for errors and missing conditions, and lets you correct it yourself. Your spaced repetition app (Active Retrieval or Anki) then plans the reviews. Three retrievals spread over three sessions gave 68% retention after a week, against 26% for three retrievals in one session.

**5. Plan with your real pace.** People underestimate how long learning takes. The coach splits parts into steps, gives a range instead of a single number, and plans back from your end date. Reviewing gets its own place in your weekly budget. After three parts, your measured pace replaces the estimate, and the coach tells you early if the track no longer fits.

**6. Get a booklet you can check.** At the end of each phase, the coach writes a chapter. Each claim in it rests on a source the coach actually opened, with the type of study, the effect and its limits. Your own explanations and mistakes sit in separate paragraphs, so the evidence and your experience stay apart. The background research is kept with the search log, so an expert can repeat it.

## What this is not

The research supports the elements one by one. That does not prove that this combination works best, and the skill as a whole has not been tested. DESIGN.md names this, and for each source it says whether the source was opened, confirmed or only known from a summary.

## In practice

- **Curriculum.** Intake, background research, a prior knowledge test, a first draft in phases and parts, and a reality check together: what fits, what almost fits, what is out of reach.
- **Sessions.** One step per turn. Each session starts with one retrieval question about an earlier part or an open gap.
- **Cards.** In the format of Active Retrieval (my own app, not public) or as a text file that Anki and many other apps import. Improved cards update the old ones without losing their review schedule.
- **Booklet.** All chapters in one Markdown file, with an EPUB if you want one.
- **Status.** The curriculum, a log and the sources live in three files, so you can continue in another conversation or on another platform. Where they live depends on the platform: memory in the Claude apps, a Project in ChatGPT, or `.active-learning/` in your working folder in Claude Code.
- **Short tracks.** With a budget of a few hours, the coach uses one phase with two to four parts, a budget in minutes and texts only at the end.

## Example

> **You:** I have two hours this afternoon and want to understand how a p-value works.
>
> **Coach:** What do you want to be able to do afterwards? For example: "I can read a test result in a paper and say what the p-value does and does not tell me."
>
> *(after the intake, a short test and a curriculum of three parts)*
>
> **Coach:** A drug trial finds p = 0.03. A colleague says: "So there is a 3% chance the drug doesn't work." Write down how you would check whether that is right. It doesn't need to be finished.

## What it needs

- **Web search** for the background research and the sources in the chapters. Without it, the research is marked as unchecked.
- **Code execution** for the card files, the zip and the EPUB. Without it, cards come as code blocks.
- **Storage:** memory files, a ChatGPT Project or a working folder. Without storage, it gives the status files as code blocks after every session.

## Opinions you may not share

This skill takes positions. Change them in [SKILL.md](SKILL.md) or the files in [references/](references/) if they don't suit you.

- You try first, before any explanation, when the goal is understanding.
- One question per turn. The coach waits for you.
- No cards before a part is learned, and the coach does not write your answers for you.
- The skill plans no reviews. Your spaced repetition app does that.
- A chapter cites only sources the assistant actually opened. Without a source, a claim is left out or labelled as a design choice.
- The skill saves its status without announcing it every time.
- Cards for Active Retrieval keep the Dutch headings `# Vraag` and `# Antwoord`, because the app expects them.
