# active-learning

An AI that explains well can make you learn less. In a field experiment with nearly a thousand high school students, those who practised maths with a plain GPT-4 chat later scored 17% lower on an exam without AI than students who never had it [S2]. This skill turns your assistant into a coach that makes you do the thinking, so that afterwards you can do it alone, and keep it.

Use it when you want to learn a subject, in a track of a few hours to several months. It doesn't activate for a single question or explanation, homework answers, flashcards from existing notes, or a course that someone else will teach.

Each claim below links to a source ID. [DESIGN.md](DESIGN.md) lists every source, says how it was checked, and explains each choice in detail.

## What it gives you

### You can do it alone, not only follow along

A clear explanation feels like understanding. That feeling misleads: students in an active class learned more than students in a lecture, but rated their own learning lower [S6]. And what works with help often fails later without it [S29].

So a part counts as learned only when you have done a new task without hints and answered a "what if" question with the right reason. The coach tests, you confirm. A question the coach gives you counts as help; a question you learned to ask yourself counts as your own work.

### Your time goes to your goal

A fixed bar wastes time. In a test track with an earlier version of this skill, every part had to be explained down to why it works. Some concepts took sessions to count as learned, while the learner could already use them.

So you decide together how deep each topic must go: an overview, using it, knowing why it works, or building it yourself. Each topic gets the lowest depth at which your end tasks succeed, and every level deeper needs a reason. If you want to master a topic fully, the coach always offers that, and tells you what it costs.

### Help that fits what you are learning

"Struggle first" sounds like a rule. It isn't one. In a meta-analysis of 53 studies, solving a problem before the explanation helped understanding and transfer (g = 0.36), but not procedures (g = -0.03) [S1].

So for understanding, you try first, get hints instead of answers, and the explanation builds on your attempt. That version gave the larger effect (g = 0.56 against 0.20) [S1]. For procedures, skills or a missing basis, you start with a worked example, and the help disappears as soon as you can do it alone. Help that supports beginners holds back people who already know the material [S7].

### You keep what you learned

Understanding something today doesn't mean you have it in a month. Three retrievals spread over three sessions gave 68% retention after a week, against 26% for three retrievals in one session [S9].

So once a part is learned, it becomes flashcards for your spaced repetition app, such as Anki. The answers come from your own explanation, because self-made cards gave better learning than ready-made ones [S11]. The coach checks every answer for errors, and you correct them yourself, so the wording stays yours.

### A plan that holds

People underestimate how long things take. Students predicted 34 days for their thesis; it took 55 [S17].

So the coach gives a range instead of one number, plans back from your end date, and reserves time for reviewing inside your weekly budget. After three parts, your measured pace replaces the estimate. You hear early when the track no longer fits, and also when it goes faster.

### A record an expert can check

At the end of each phase you get a chapter for a booklet about your own track. It cites only sources the coach opened, with the type of study, the effect and its limits. Your own explanations and mistakes sit in separate paragraphs, so evidence and experience stay apart. The search log lets an expert repeat the background research.

## Example

> **You:** I have two hours this afternoon and want to understand how a p-value works.
>
> **Coach:** What do you want to achieve with it?
>
> **You:** I review papers at work and keep skipping the statistics.
>
> *(after the end tasks, a short test and the scope)*
>
> **Coach:** For your goal, using the p-value is enough: you need to read it correctly, not calculate it. Calculating stays out of the track, unless you want it.
>
> *(after a curriculum of three parts)*
>
> **Coach:** A drug trial finds p = 0.03. A colleague says: "So there is a 3% chance the drug doesn't work." Write down how you would check whether that is right. It doesn't need to be finished.

## What is proven, what is practice, and what is a choice

The skill rests on three kinds of ground. They are not equally firm, and the coach keeps them apart when it talks to you too.

### Supported by research

Each of these findings comes from studies, mostly with pupils and students. None of them tested this skill.

- Solving a problem before the explanation helps understanding and transfer, not procedures. The explanation works better when it builds on your own attempt [S1].
- Worked examples help beginners [S28]. Too much guidance holds back people who already know the material [S7].
- Explaining steps and your own errors to yourself while you learn has a medium effect (g = 0.55) [S5]. After an error, targeted prompts helped more than general ones, but only on similar tasks [S36].
- Spaced retrieval beats retrieving everything at once [S9, S13]. In maths, testing gave no robust advantage over rereading, so the coach also searches how each subject is best learned [S14].
- Self-made flashcards beat ready-made ones [S11].
- The feeling of having learned something is a poor measure [S6], and so is performance with help [S29].
- People underestimate time. Splitting a task and planning back from the end date make estimates more realistic [S17, S19, S20].
- AI tutors can harm learning or help it, depending on their design and setting. Results so far go both ways [S2, S3, S34].

### From practice

These come from experienced practitioners, not from comparative studies.

- Learning a complex topic first as a black box, for what it does, and going deeper only where you need it. This comes from Colin Galen [S32, S33].
- Understand before you memorise, and one idea per card. These are rules from Piotr Wozniak, the creator of SuperMemo [S8].

### Design choices of this skill

These follow from the research and the practice above, but no study prescribes them. Change them in [SKILL.md](SKILL.md) or the files in [references/](references/) if they don't suit you.

- The four depth levels, and the rule that every level deeper needs a reason.
- The teach-back. It is a check of your understanding and the source of your card answers, not a tested learning method. The self-explanation research explicitly excludes explaining to someone else [S5].
- The bar for "learned": a task without hints, a teach-back and a "what if" question, with an extra task after a lot of help.
- One question per turn, so you do the work.
- Interest in your reasoning, real choices and little pressure. Support for autonomy goes together with motivation, but those studies measured correlations, not effects [S37].
- Cards right after a part is learned, and a signal to check the part when it gives more than about ten.
- The shape of a curriculum: two to four phases of three to six parts.
- Chapters that cite only opened sources, ranked from meta-analyses down to blogs.

The combination has not been tested as a whole. It has only been tried in two tracks, and the changes after each track are in DESIGN.md.

## What it needs

- **Web search** for the background research and the sources in the chapters. Without it, the research is marked as unchecked.
- **Code execution** for the card files and the EPUB. Without it, cards come as code blocks.
- **Storage** to continue across conversations: memory in the Claude apps, a Project in ChatGPT, or a working folder in Claude Code. Without it, you get the status files as code blocks after every session.

Cards come in the format of Active Retrieval (my own app, not public) or as a text file that Anki and many other apps import.

## Sources

The source IDs [S1] to [S37] refer to the source list in [DESIGN.md](DESIGN.md#sources). For each source, it says whether it was opened in full, read as an abstract, or known only from a summary.
