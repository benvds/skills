# Active learning: design and rationale

This document explains why the skill works the way it does. For each choice, it states what was decided, why, what it rests on, and which alternative was rejected. Source references appear as [S1], [S2] and so on. The source list at the bottom states for each source how it was checked.

Written 17 October 2026. Revised the same day after an external review of the content and after first use; see "Changes after review" and "Changes after first use" at the bottom. Prepared for publication on 21 October 2026; see "Changes for publication".

## Goal

You learn a subject in a track that fits what you want to be able to do and the time you have. You build the material yourself, with an AI assistant as coach. What you have learned goes as cards to a spaced repetition app, such as Active Retrieval or Anki, which plans the reviews. At the end you have a booklet about your own track, with sources an expert can check. You can continue on any device, in Claude or in ChatGPT.

## Choice 1: Works in Claude and ChatGPT

**Decision.** The skill follows the open SKILL.md standard [S26]. The learning approach is independent of the platform. Everything that differs per platform (saving, delivering files, multiple-choice questions) is in one file: `references/platform.md`.

**Why.** SKILL.md is an open standard that several assistants read. ChatGPT supports skills, according to OpenAI's help page, for users of Business, Enterprise, Healthcare and Edu, depending on the workspace settings [S27]. By putting the platform differences in one file, the rest of the skill stays the same, and a new platform needs changes in only one place.

**Limitation.** ChatGPT cannot write files to its memory. There, you keep the three status files in a Project and replace them yourself after every session. That is one manual step per session. In Claude it happens automatically. If you have no access to skills in ChatGPT, you can put the content of `SKILL.md` as instructions in a Project and add the reference files as project files.

**Portable.** The files have the same format on every platform. You can start a track in Claude and continue in ChatGPT, or the other way around.

## Choice 2: No scripts, status in the platform's storage

**Decision.** The skill contains only instructions. Status, log and sources live in the platform's storage: memory in the Claude apps, project files in ChatGPT, and a folder in the working folder for a coding agent such as Claude Code.

**Why.** You want to continue on several desktops and your phone. A folder in a working environment exists for only one session. Scripts don't work in every environment or on every platform. Instructions work everywhere.

A working folder is only available on one computer. That is why memory is preferred when it is there, and why the user can always export the status to another platform.

**Rejected.** A web page with a database as central storage. That gives a dashboard, but only works in Claude.

## Choice 3: Help matched to learning goal and prior knowledge

**Decision.** There are two routes. For understanding with enough prior knowledge: try first (route A: black box, problem, hint ladder, explanation built on the attempt). For procedures, skills or missing prior knowledge: a worked example first (route B: example, partly completed task, independent task). If the user cannot make a start in route A, the coach switches to route B. The amount of help follows from what the user shows, not from a fixed number of hints. Each part gets a learning goal type in the curriculum: understanding, procedure, skill or social.

**Why and rationale.**
- **Trying first works, but not always.** A meta-analysis of 53 studies found a medium advantage for problem solving before instruction for understanding and transfer (g = 0.36), but no difference for procedural knowledge (g = -0.03). Instruction first came out better for young learners and for general skills [S1]. "Struggle first" is therefore not a rule for everything. That is why the route depends on the learning goal type.
- **The explanation after the attempt is essential.** In the same meta-analysis, the effects were larger when the instruction built on the learners' own solutions (g = 0.56 against 0.20) and when it took the form of a dialogue instead of a lecture [S1]. That is why the explanation in route A builds on the user's attempt, in conversation.
- **Example first when the basis is missing.** Worked examples gave a medium effect (g = 0.48) in a meta-analysis on mathematics [S28]. Guidance that helps beginners can hold back people with more prior knowledge [S7]. That is why route B reduces the help as soon as the user can do it alone.
- **Black box.** There is no direct research on this form. It is designed to make route A possible: enough overview to try the problem, without giving away the solution.
- **Hints instead of answers.** Students who used an AI that gave answers then did worse without AI than students without AI. An AI tutor that gave hints largely prevented this [S2]. A recent randomised experiment showed that an AI tutor designed according to educational principles gave more learning gain in less time than active learning in class [S3]. The design of the tutor matters, not just the use of AI.
- **Setting it aside helps.** Leaving a problem for a while gave a small to medium advantage (d = 0.29) [S4]. That is why a break is a full option when the user is frustrated.
- **Don't gloss over frustration.** Getting stuck can be part of learning, but it is no proof that learning is working. It can also mean that the task is too hard or the basis is missing. That is why the coach says something like "Getting stuck can be part of learning. Let's see whether you can move on or need different help," and offers to switch to a worked example.
- **Explaining it yourself.** Prompting self-explanation gave a medium learning effect (g = 0.55) [S5]. That is why there is a teach-back.

**Rejected.** An exam mode. It may come back later as a separate variant.

## Choice 4: When a part is "learned"

**Decision.** The assistant tests, you confirm. Learned means: you can do it independently, your teach-back has no large gap, and you answer "what if" correctly with the right reason. If you solved the problem with a lot of help (hint level 3 or lower, or after the solution), one new task without hints follows first. If you already know a part, teach-back and "what if" are enough, plus one performance task for a procedure or skill (the fast route).

"Learned" records the end of the first learning phase, not lasting ability. That is why every learned part comes back later as an application: during retrieval at the start of a session, at least a week later, or in a phase end task that also uses earlier parts.

**Why.** The feeling "I get it" is a poor measure. Students in an active class learned more than students in a passive class, but rated their own learning gain lower [S6]. A test on explaining and applying says more.

Performing during practice is also not a reliable measure of learning: what succeeds with help may not succeed independently later, and learners often mistake performance during practice for lasting learning [S29]. That is why there is an independent task after a lot of help, and a later application. A second review planner is not needed for this: retrieval and the phase end task cover it.

The fast route prevents you from going through parts you already master in full again. A lot of guidance helps beginners, but holds back people who already know the material [S7].

**Rejected.** A stricter bar, where the teach-back must still hold up in the next session before there are cards. See choice 5 for why that adds little.

## Choice 5: Cards only after learning

**Decision.** Cards are made right after a part is learned, not earlier and not later.

**Why and rationale.**
- **Understand before you memorise.** The first two rules of Wozniak, the creator of SuperMemo: don't learn what you don't understand, and understand before you memorise [S8]. This is practical knowledge, not an experiment, but it fits choice 3.
- **Successive relearning.** This method has two parts: first practise until you retrieve something correctly once, then review in spaced sessions. One spaced session already had a large effect (d = 1.82). Three retrievals spread over three sessions gave 68% retention after a week, against 26% for three retrievals in one session. After three spaced sessions, it no longer mattered how strict the initial bar was [S9]. The "learned" check is the first part, the spaced repetition app the second.
- **The timing of the first review is not critical.** Testing immediately or later gave no stable difference, and neither did the shape of the schedule (expanding or equal) [S10]. That is why there is no waiting period.

## Choice 6: Answers in your own words

**Decision.** The assistant writes the questions. The answers come from your teach-back. What you did not explain, you fill in yourself. Before any files are made, the assistant checks each answer for correctness, missing conditions and misleading wording. If there is an error, the assistant explains what is wrong, and you rephrase the answer.

**Why.** In a series of experiments, students with self-made digital cards learned more than with ready-made cards: on average d = 0.45 for definition questions and d = 0.29 for application questions. The advantage appeared with copy and paste, with rephrasing, and (for definitions only) with own examples. Typing word for word gave no advantage [S11]. Rephrasing yourself is therefore not the only effective way, but it is a defensible choice: your teach-back is already a rephrasing, so it costs no extra time.

**What the research does not show.** It did not study the method of this skill, in which an assistant takes answers from an earlier teach-back. That application is a plausible translation of the research, not a proven method. The research was also about students and short texts, tested after two days.

**Why the check.** A teach-back may still have small gaps; only a large gap blocks "learned". Without a check, a small but important error could end up on a card that you review for years. By letting you correct the error yourself, the wording stays your own.

**Rejected.** The assistant writes complete cards and you approve them.

## Choice 7: The content sets the number of cards

**Decision.** No fixed number per part. The assistant lists the pieces of knowledge in the part and makes one card per piece of knowledge that meets two requirements: an end task or a later part needs it, and you must still have it ready in a month. More than about ten cards from one part is a signal to check whether the part is too large.

**Why.** A fixed number is arbitrary: it forces filler cards for a small part and leaves knowledge out for a large part. The principle "one idea per card" [S8] lets the number follow from the content. The filter keeps the reviewing in the spaced repetition app limited to what you really need, because every card costs years of review time.

**Note.** There is no research on the right number of cards per learning part. The limit of about ten is a signal to think, not a rule.

## Choice 8: Reviewing in the spaced repetition app, with a short warm-up

**Decision.** The skill does not plan reviews. Every session does start with one retrieval question about the open gap or the previous part.

**Why.** Testing improves performance with a medium effect (g = 0.50) [S12], and spaced retrieval works better than everything in one session (g = 0.74) [S13]. A spaced repetition app already does this with a scheduling algorithm: Active Retrieval uses FSRS, Anki SM-2 or FSRS. A second planner would mean double work and conflicting schedules.

**Nuance from recent research.** A 2025 meta-analysis on mathematics found a robust small to medium effect of spacing (g = 0.28), but no robust effect of testing compared with rereading (g = 0.18, based on seven studies) [S14]. Effects therefore differ per field. That is why the background research also searches, per subject, for how it is best learned.

## Choice 9: The curriculum

**Decision.** Intake with end tasks and time, background research, prior knowledge test, first draft with a learning goal type per part, a reality check together, a short assessment list per end task, and a next steps section. Phase end tasks also combine parts from earlier phases, without saying which are needed.

**Why and rationale.**
- **Start at the end.** First decide what you want to be able to do, then how you show it, and only then the lessons. This is called backward design [S15]. A level label such as "beginner" says nothing about what you want to achieve.
- **Measure prior knowledge.** Answering questions before you learn the material improves learning that material, even if you answer the questions wrongly [S16]. The review notes that the effect is strongest for concrete facts; less is known for deeper understanding questions. And the test decides where the fast route is possible [S7]. Four to six questions don't map a broad subject completely. The judgement per part is therefore provisional, and when in doubt the coach chooses "partly" over "mastered".
- **The method follows the learning goal.** Understanding, carrying out a procedure, practising a skill and doing something with other people each need a different approach (see choice 3). The learning goal type per part makes that choice explicit. Social learning goals get a practice task in a real situation, with a debrief.
- **Assessment list.** What must go well, which errors are essential and how much help is allowed are set beforehand. This way the coach assesses an end task against agreements and not on gut feeling.
- **Bringing back earlier parts.** A phase end task that also uses earlier parts tests whether you can still apply them later and whether you recognise which approach fits. This connects to choice 4.
- **Next steps and broadening.** What does not fit does not disappear but moves to a follow-up. This keeps the track feasible and you lose nothing.

## Choice 10: Estimating time without a fixed buffer

**Decision.** No fixed buffer percentage. The first estimate is a range per part, split into steps and counted back from the end date. After three parts, your own measured pace replaces the estimate. The skill counts the actual number of sessions per part instead of asking you how long something took.

**Is there research on session estimates and buffers?** On the duration of learning parts or the right buffer for a personal learning track: none found. On how people estimate time: yes, and that research shapes the method:
- **The problem is robust.** Students predicted 34 days on average for their thesis; it took 55, and about 30% met their own prediction [S17]. Review work confirms that this underestimation is widespread [S18].
- **Splitting helps.** Breaking a task into subtasks makes estimates less optimistic [S19].
- **Planning backwards helps.** Planning from the end date back to now gave more realistic predictions than planning forwards [S20].
- **Measure instead of remember.** People underestimate afterwards how long earlier tasks took, and that carries over into new estimates [S21]. That is why the skill counts sessions in the log.
- **Own history as reference.** Predicting based on the actual outcome of comparable earlier cases (the "outside view" or reference class forecasting) is a known remedy [S23]. Your first parts are the best reference for the rest of your track.
- **Concrete planning.** Concrete plans about when and where you start reduced interruptions and with that the underestimation [S22]. That is why the reality check asks for fixed session times.

**Reviewing as real time.** Reviewing in the spaced repetition app gets a fixed place in the weekly budget, not beside it. At the reality check, you first reserve time for reviewing; only the rest goes to learning sessions. At the end of each phase, you measure how much time reviewing really takes. If it overruns, you choose: a stricter card filter, a lower pace, or more time. How much review time a card costs depends on the card and the algorithm; that is why the skill measures it instead of predicting it.

**Why no fixed percentage.** Mark-ups for optimism, as in large projects, differ strongly per country, sector and type of project [S23]. For a personal learning track, no such number exists. Inventing one would give false certainty. Also important: correction methods don't always make estimates more accurate; sometimes they overshoot into overestimation [S18]. That is why the skill also reports when things go faster than planned.

## Choice 11: Three storage files

**Decision.** Per track, a status file, a complete log and a sources file.

**Why.**
- **Keep the status small.** The status file is read every session. The smaller it is, the faster and the less chance of errors.
- **Complete log.** You want to be able to reread the whole track. A memory file in Claude is limited to about 48 KB; a separate file with continuation parts keeps that workable. The log also keeps the core of every teach-back and the number of sessions, so that cards, chapters and pace measurement can be done from any conversation.
- **Verifiable sources.** The research map, the search log and every source used are in one place, with ID, type, year, peer review status, date and what they were used for. A subject expert can thus repeat the background research, not just reread it. The idea of recording the search comes from the way systematic reviews do it [S24].

## Choice 12: Recent sources with authority

**Decision.** The background research searches first for work from the last five years. It uses a fixed ranking: meta-analyses and systematic reviews, then guidelines from authoritative institutions, then experiments, then handbooks, and preprints and blogs only with a label. The assistant goes to the primary source, checks striking results for retraction, and notes contradictions between sources.

**Why.** Research ages, and a summary on a blog sometimes misrepresents a study. With the year, type and peer review status for every source, an expert can quickly see how strong the foundation is. Older classics may remain as a foundation, but the skill actively searches for newer work that confirms or qualifies them. Choice 8 shows why: a recent meta-analysis qualified an older, broader result.

**Effect sizes.** For an effect, the coach notes the measure, the value, the margin of uncertainty, the comparison and the practical meaning. Rules of thumb apply only as a rough direction and only to their own measure: for differences between groups (d, g) around 0.2, 0.5 and 0.8; for correlations (r) traditionally 0.1, 0.3 and 0.5. An analysis of more than 700 correlations from meta-analyses in individual differences psychology found that 0.1, 0.2 and 0.3 are more realistic limits there [S30].

## Choice 13: Texts and the booklet

**Decision.** At the start, an introduction, overview and research file. Per phase, a chapter with "Further reading" and sources. At the end, a next steps chapter. The booklet is one Markdown file by default, with EPUB as an option.

**Why.**
- **Reference after learning.** Reading a chapter before you have tried yourself undermines choice 3. That is why the chapter comes at the end of a phase.
- **Your material, next to the evidence.** Your teach-backs, examples and pitfalls sit in their own paragraphs. This way it reads as your track, while the evidence comes from sources (see "Changes after first use").
- **Only real sources.** Every claim that does not come from the sessions refers to a source in the sources file. Sources the assistant did not open don't go in.
- **Plain Markdown.** No Obsidian-specific syntax, so Pandoc can make an EPUB or PDF from it [S25].
- **Content not in storage.** The texts are too large. You attach the files when you make the booklet.

## Choice 14: A short track of a few hours

**Decision.** A track can also last one day or less. The sessions work the same way: trying first or an example first, teach-back, "what if" and cards. The planning around them shrinks: one phase with two to four parts, a total budget in minutes, less background research, a shorter prior knowledge test, no correction factor, no "apply later", and texts only at the end.

**Why.** Many learning questions are small: someone has an afternoon to get to grips with a tool or a concept. The elements that carry the most weight in the research also work within a session: trying first [S1], worked examples [S28], self-explanation [S5] and self-made cards [S11]. Spacing and later application need time between sessions [S9, S13]; within a few hours that time is missing. That is why the short track leaves the spacing to the spaced repetition app after the track, and drops "apply later" unless the user continues.

**Note.** The sizes of the short track (two to four parts, 20 to 45 minutes per part, about ten minutes for teach-back and cards) are design choices, not derived from research. Background research and a test take a noticeable part of a short budget; that is why both are smaller, and why there are no texts at the start.

**Rejected.** Refusing short tracks. Then the skill would not help with a common learning question, while its core works there too.

## Known limitations

- **The assistant judges your teach-back.** That judgement can be wrong. That is why you confirm every "learned".
- **Storage is not guaranteed.** A write can fail or be refused. The skill then says so and gives the content as a code block.
- **ChatGPT needs a manual step.** After every session, you replace the status files in your Project.
- **Working at the same time.** If you work on the same track on two devices at once in Claude, the assistant merges changes when there is a version conflict. Check the status file if something looks odd.
- **No `cloze` cards.** Only `basic`.
- **Without code execution, no zip or EPUB.** Cards then come as separate code blocks.
- **Rules of thumb.** The shape of the curriculum (two to four phases, three to six parts; one phase with two to four parts in a short track), the signal at ten cards and the limit at hint level 3 for an independent task are design choices, not derived from research.
- **Audience.** The skill assumes an adult learner who masters the language of instruction well. Age, language proficiency and extra support needs are not explicitly weighed. Children or beginning language learners need an adapted version, partly because instruction first came out better for young learners [S1].
- **Social learning goals.** The skill can give a practice task in a real situation and debrief it, but cannot practise with real people itself.

## What this document does not prove

The rationale is about separate elements: trying first, worked examples, self-explanation, spaced reviewing, self-made cards. That each of these elements works does not prove that this combination works best. The skill itself has not been tested. Where this document says "that is why", it describes a design choice that fits the research, not a proven effect of the skill.

## Changes after review

An external review of the content led to these changes:
- **Correction on flashcard research (choice 6).** The advantage of self-made cards also appeared with copy and paste, not only with rephrasing. The skill's method is named as a design translation.
- **Correction on effect sizes (choice 12).** Rules of thumb separated per measure; the coach now also notes uncertainty, comparison and practical meaning.
- **Help matched to learning goal and prior knowledge (choice 3).** Route B with a worked example and decreasing help; learning goal type per part; "struggle first" is no longer a general rule.
- **Independent and later (choice 4).** Independent task after a lot of help; performance task on the fast route for procedures and skills; later application.
- **Checking card answers (choice 6).** A content check before files are made.
- **Frustration sentence changed (choice 3).**
- **Earlier parts in phase end tasks, assessment list per end task, provisional test judgement (choice 9).**
- **Reviewing budgeted within the weekly budget (choice 10).**
- **Wording toned down.** "Comparing this is where most learning happens" was replaced by a supported explanation built on the attempt. The opening sentence of the skill no longer says that explanation teaches less than struggling. New section "What this document does not prove".

## Changes after first use

A first learning track with the skill led to these changes, in `SKILL.md` (fixed rules) and `references/session.md` (new section "Giving feedback" and the "what if" step):
- **Reasoning and sources separate.** The coach gave feedback with sentences like "that is not in the sources we read". This gave the learner the impression of being expected to have knowledge the learner could not have: the background research is deliberately shown only later (see choice 3), and the coach had read it, the learner had not. The rule is now: judge the learner's own reasoning, give what the coach knows from research only afterwards and recognisably as an addition, phrase hints and "what if" questions so they can be answered by reasoning, and briefly name your own clumsy wording.
- **Judge only what was asked.** The coach asked a "what if" question without "why" in it and then counted the missing why as a gap. The rule is now: judge an answer only on what the question asked. If the coach wants a reason, the coach asks for it in the same question. If that was forgotten, the coach says so and asks for the reason separately. The "what if" step now requires "and why" to be literally in the question.
- **Chapter as well-founded reference material.** The first chapter consisted mainly of the user's own wording, with three source references that only ran through this design document and had not been opened. It read as the user's story with sources attached, not as reference material. The rule is now: before writing, search for sources and open them, build each part from what the research says (with study type, effect and limit), how the skill applies it, and only then what the user said about it. The user's wording sits in its own paragraph. A source that was not opened supports nothing. Texts are written with a skill for clear writing, if one is available.
- **Basis.** These are design choices that follow from the skill's own setup (try first, show research later, judge fairly, separate evidence and experience), not outcomes of research. They are based on one user and one track.

## Changes for publication

For publication, the skill was separated from one personal setup:
- **Cards for more than one app.** Active Retrieval is not public. The user chooses a spaced repetition app at the intake. Active Retrieval remains an option; for Anki and other apps, the skill delivers an Anki text file with the card ID as GUID, so an improved card updates the old one [S31].
- **Storage based on tools.** The skill chooses storage based on the tools it has, not on the product name. A coding agent such as Claude Code keeps the status in a folder in the working folder.
- **Writing skill by name.** Texts are written with `plain-writing`, if it is available.
- **English instructions.** The instructions are in English; the skill speaks the user's language. File names, keys and statuses are English. Tracks started with the Dutch version keep their Dutch names, and the skill reads both (see `references/storage.md`).
- **Gender-neutral.** The instructions refer to the user as "the user" or "they".
- **Short track.** A track can last from a few hours to several months (choice 14).

## Sources

For each source, this states how it was checked when this document was written:
- **opened:** the page or article was read
- **location confirmed:** title, authors and location confirmed via a search result or DOI, content not reread
- **via secondary source:** the content comes from an overview or summary by others
- **not rechecked:** taken from earlier background research; check this before you build on it

| ID | Source | Check |
| --- | --- | --- |
| S1 | Sinha, T., & Kapur, M. (2021). When problem solving followed by instruction works: Evidence for productive failure. *Review of Educational Research*, 91(5), 761-798. https://doi.org/10.3102/00346543211019105 | opened |
| S2 | Bastani, H., et al. (2025). Generative AI without guardrails can harm learning. *PNAS*. https://doi.org/10.1073/pnas.2422633122 | location confirmed; page gave an error when opened |
| S3 | Kestin, G., Miller, K., Klales, A., Milbourne, T., & Ponti, G. (2025). AI tutoring outperforms in-class active learning: An RCT introducing a novel research-based design in an authentic educational setting. *Scientific Reports*. https://serl.fas.harvard.edu/publication/ai-tutoring-outperforms-class-active-learning-rct-introducing-novel-research-based | opened (abstract) |
| S4 | Sio, U. N., & Ormerod, T. C. (2009). Does incubation enhance problem solving? A meta-analytic review. *Psychological Bulletin*. https://pubmed.ncbi.nlm.nih.gov/19210055/ | not rechecked |
| S5 | Bisra, K., Liu, Q., Nesbit, J. C., Salimi, F., & Winne, P. H. (2018). Inducing self-explanation: A meta-analysis. *Educational Psychology Review*. https://www.Gwern.net/doc/psychology/spaced-repetition/2018-bisra.pdf | not rechecked |
| S6 | Deslauriers, L., McCarty, L. S., Miller, K., Callaghan, K., & Kestin, G. (2019). Measuring actual learning versus feeling of learning in response to being actively engaged in the classroom. *PNAS*. https://pubmed.ncbi.nlm.nih.gov/31484770/ | not rechecked; page gave an error when opened |
| S7 | Kalyuga, S. (2007). Expertise reversal effect and its implications for learner-tailored instruction. *Educational Psychology Review*, 19, 509-539. https://doi.org/10.1007/s10648-007-9054-3 | location confirmed |
| S8 | Wozniak, P. (1999). Effective learning: Twenty rules of formulating knowledge. https://supermemo.guru/wiki/20_rules | opened |
| S9 | Rawson, K. A., & Dunlosky, J. (2022). Successive relearning: An underexplored but potent technique for obtaining and maintaining knowledge. *Current Directions in Psychological Science*. https://doi.org/10.1177/09637214221100484 | opened |
| S10 | Karpicke, J. D., & Roediger, H. L. (2010). Is expanding retrieval a superior method for learning text materials? *Memory & Cognition*, 38(1), 116-124. https://doi.org/10.3758/MC.38.1.116 | opened; DOI confirmed |
| S11 | Pan, S. C., Zung, I., Imundo, M. N., Zhang, X., & Qiu, Y. (2023, online 2022). User-generated digital flashcards yield better learning than premade flashcards. *Journal of Applied Research in Memory and Cognition*, 12(4), 574-588. https://doi.org/10.1037/mac0000083 · full text: https://sc-pan.github.io/pdf/PZIZQ_2022.pdf | opened (full text) |
| S12 | Yang, C., Luo, L., Vadillo, M. A., Yu, R., & Shanks, D. R. (2021). Testing (quizzing) boosts classroom learning: A systematic and meta-analytic review. *Psychological Bulletin*. https://pubmed.ncbi.nlm.nih.gov/33683913/ | not rechecked; page gave an error when opened |
| S13 | Latimier, A., Peyre, H., & Ramus, F. (2021). A meta-analytic review of the benefit of spacing out retrieval practice episodes on retention. *Educational Psychology Review*. https://doi.org/10.1007/s10648-020-09572-8 | location confirmed |
| S14 | Murray, E., Horner, A. J., & Göbel, S. M. (2025). A meta-analytic review of the effectiveness of spacing and retrieval practice for mathematics learning. *Educational Psychology Review*, 37. https://doi.org/10.1007/s10648-025-10035-1 | opened |
| S15 | Wiggins, G., & McTighe, J. (2005). *Understanding by Design* (2nd ed.). ASCD. Overview: https://cft.vanderbilt.edu/?p=984 | location confirmed |
| S16 | Pan, S. C., & Carpenter, S. K. (2023). Prequestioning and pretesting effects: A review of empirical research, theory, and recommendations. *Educational Psychology Review*. https://doi.org/10.1007/s10648-023-09814-5 | opened |
| S17 | Buehler, R., Griffin, D., & Ross, M. (1994). Exploring the "planning fallacy": Why people underestimate their task completion times. *Journal of Personality and Social Psychology*, 67(3), 366-381. https://bear.warrington.ufl.edu/brenner/mar7588/Papers/buehler-et-al-1994.pdf | location confirmed; figures via secondary source |
| S18 | Buehler, R., Griffin, D., & Peetz, J. (2010). The planning fallacy: Cognitive, motivational, and social origins. *Advances in Experimental Social Psychology*, 43, 1-62. https://doi.org/10.1016/S0065-2601(10)43001-4 | DOI confirmed; content via secondary source |
| S19 | Kruger, J., & Evans, M. (2004). If you don't want to be late, enumerate: Unpacking reduces the planning fallacy. *Journal of Experimental Social Psychology*, 40(5), 586-598. https://doi.org/10.1016/j.jesp.2003.11.001 | DOI confirmed; content via secondary source |
| S20 | Wiese, J., Buehler, R., & Griffin, D. (2016). Backward planning: Effects of planning direction on predictions of task completion time. *Judgment and Decision Making*, 11(2), 147-167. https://doi.org/10.1017/S1930297500007269 | opened |
| S21 | Roy, M. M., Christenfeld, N. J. S., & McKenzie, C. R. M. (2005). Underestimating the duration of future events: Memory incorrectly used or memory bias? *Psychological Bulletin*, 131(5), 738-756. https://pubmed.ncbi.nlm.nih.gov/16187856/ | location confirmed |
| S22 | Koole, S., & Van't Spijker, M. (2000). Overcoming the planning fallacy through willpower: Effects of implementation intentions on actual and predicted task-completion times. *European Journal of Social Psychology*, 30(6), 873-888. | via secondary source |
| S23 | Kahneman, D., & Lovallo, D. (1993). Timid choices and bold forecasts: A cognitive perspective on risk taking. *Management Science*, 39(1), 17-31. Explanation and criticism of fixed mark-ups: https://www.pmi.org/learning/library/planning-fallacy-causes-solutions-project-expectations-6374 | via secondary source |
| S24 | PRISMA: guideline for reporting systematic reviews. https://www.prisma-statement.org | location confirmed |
| S25 | Pandoc, universal document converter. https://pandoc.org | location confirmed |
| S26 | Agent Skills, open standard for SKILL.md. https://agentskills.io | location confirmed |
| S27 | OpenAI (2026). Skills in ChatGPT. https://help.openai.com/en/articles/20001066-skills-in-chatgpt | opened |
| S28 | Barbieri, C. A., Miller-Cotto, D., Clerjuste, S. N., & Chawla, K. (2023). A meta-analysis of the worked examples effect on mathematics performance. *Educational Psychology Review*, 35, 11. https://doi.org/10.1007/s10648-023-09745-1 | via secondary source |
| S29 | Soderstrom, N. C., & Bjork, R. A. (2015). Learning versus performance: An integrative review. *Perspectives on Psychological Science*, 10(2). https://doi.org/10.1177/1745691615569000 | opened (journal abstract) |
| S30 | Gignac, G. E., & Szodorai, E. T. (2016). Effect size guidelines for individual differences researchers. *Personality and Individual Differences*. https://doi.org/10.1016/j.paid.2016.06.069 | via secondary source |
| S31 | Anki Manual: Text Files. https://docs.ankiweb.net/importing/text-files.html | opened |
