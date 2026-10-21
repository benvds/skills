# active-learning

Use it when you want to learn a subject, not just get an answer. It coaches you through a learning track that lasts from a few hours to several months: you build the material yourself, and the assistant asks, hints and checks.

It doesn't activate for a single question or explanation, homework answers, flashcards from existing notes, or a course that someone else will teach.

## What it does

- **Curriculum.** It starts from what you want to be able to do afterwards and the time you have. It does background research, tests what you already know, and drafts phases and parts. Together you check what fits in your time.
- **Sessions.** For understanding, you try a problem first and get hints; the explanation builds on your attempt. For procedures and skills, or when the basis is missing, you start with a worked example and the help decreases. Every part ends with an independent task, a teach-back in your own words and a "what if" question.
- **Cards.** Only after a part is learned, it makes flashcards whose answers come from your teach-back. It checks them for errors and lets you fix them yourself. Cards come in the format of Active Retrieval (my own app, not public) or as a text file that Anki and many other apps import.
- **Booklet.** At the end of each phase, it writes a chapter with sources it has actually opened. At the end you can combine the chapters into one Markdown file and an EPUB.
- **Status.** It keeps the curriculum, a log and the sources in three files, so you can continue in another conversation. Where they live depends on the platform: memory in the Claude apps, a Project in ChatGPT, or `.active-learning/` in your working folder in Claude Code.
- **Short tracks.** With a budget of a few hours, it uses one phase with two to four parts, a budget in minutes and texts only at the end.

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

## Research

[DESIGN.md](DESIGN.md) explains every choice, what research it rests on, and how each source was checked. It also says what the research does not prove: the elements are supported separately, but the skill as a whole has not been tested.
