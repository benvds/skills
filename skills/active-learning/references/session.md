# A session

One session is usually one part. Take one step per turn and wait for the user.

## Step 0: Retrieval

Start every session with one short question, except the very first session, and except in a short track when the previous part ended less than an hour ago:
- If the status file has an open gap: ask about exactly that gap.
- If a part is on "apply later" (see **Apply later**): give a short application question about that part, not an explanation question.
- Otherwise: ask for the core of the most recently learned part. "Explain in two sentences what [part] does and when you use it."

Give one sentence of feedback. If the gap is still there: note it and take it into this session. If the answer was right: remove the gap from the status file. Then continue.

This is not a review session. The spaced repetition app does the reviewing. This is a warm-up of a few minutes.

## Start of a phase: the table

At the start of a phase, set out all parts as black boxes, with their target level. Level 1 topics of this phase, which have no part of their own, get a row here too:

| Part | What it does | You use it for | Level |
| --- | --- | --- | --- |
| ... | ... | ... | ... |

This shows the user which part belongs to which problem, and how deep each one goes. Start with the first part, unless the user chooses another one.

## Start of a part: the black box

Every part starts with a black box, in every route: explain what the part does, not how. Under 150 words:

```
**[Part] in one sentence:** [what it does, in plain words]
**What goes in:** ...
**What comes out:** ...
**When you use it:** ... (and when not)
**Mini example:** [one concrete case, only input and output]
```

Then follow the route: a problem in route A, a worked example in route B. Don't explain the inside yet. That comes after the attempt or in the example, and only as far as the target level asks. On the fast route, skip the black box.

## Choose the route

In the status file, each part has a learning goal type (see `curriculum.md`), a target level, and a prior knowledge judgement from the test. The type and the prior knowledge set the route. The target level sets how far the route goes (see **Depth**). Adapt the route to what the user shows, not to the number of hints already given.

| Situation | Route |
| --- | --- |
| Understanding, and the user has enough basis to make a start | **A: try first** |
| Procedure (carrying out a fixed series of steps) | **B: example first** |
| Understanding, but the required prior knowledge is missing | **B: example first** |
| Skill (doing, making, performing something) | **B**, and the independent task is a performance task |
| Social learning goal (conversation, giving feedback, negotiating) | **B** in the chat, plus a practice task in a real situation (see below) |
| The user already masters it at the target level | **Fast route** |

**Switching.** If the user cannot make any start in route A, not even after the first hint, switch to route B. Don't climb all the way down the hint ladder when there is no basis to build on.

## Depth: stop at the target level

The target level of the part sets what you explain, what you test and when the part is done. Time is limited: don't go deeper than the target level, also not when it would be interesting. Offer a deeper level as a choice, with what it costs (see `curriculum.md`, **Adjusting along the way**).

| Target level | The route ends with | Teach-back asks | "What if" changes |
| --- | --- | --- | --- |
| **2 Use** | an independent task in which the user applies it correctly | what does it do, when do you use it and when not, how do you apply it? | the situation: can you still use it here, and why? |
| **3 Inside** | an independent task; the explanation covers why it works | what does it do, why does it work, when do you not use it? | one element of how it works: does it still work, and why? |
| **4 Build** | first level 3, then a build task: derive or rebuild it without an example, or design a variant for a new situation | how did you build it, and why is each step needed? | a requirement: what would you change in your build, and why? |

**Level 1 topics** get no route. The black box in the phase table is enough. In the session of the part that uses the topic, ask one check question: "In which of these two situations do you use [topic], and why?" If the answer is wrong, explain it briefly and ask again with a new pair.

**Already at the target level.** As soon as the user shows the target level, go to the check of that level: the independent task, or the teach-back and "what if" if the independent task is already done. Don't finish the route for its own sake. A part at level 2 is done when the user can use it, even if they cannot yet explain why it works.

**A detail deeper.** If the user keeps making the same error in use, and only knowledge of the inside prevents it, explain that one detail (hint level 4), and then return to the whole. If the part as a whole needs a deeper level, propose that to the user as a change of the curriculum.

**Level 4: the build task.** Give the goal and the requirements, no example and no steps. For example: "Simulate a p-value yourself for this experiment" or "Design a variant that also works when the list is empty". Feedback as in A2. The build task is the independent task of level 4.

## Route A: try first

### A1. Problem

Give a problem that the part solves. A good problem:
- can at least partly be solved with what the user already knows, even if clumsily;
- allows several approaches;
- is not a standard textbook question whose answer can be looked up;
- is concrete: real numbers, names, situations. Where you can, use the context of the end tasks.

Say that mistakes are expected and useful. Ask the user to write down their approach, even if it is not finished. No hints in this turn.

If the user wants the explanation right away: ask once whether they want to spend two minutes on a first idea. If the answer is no, go to route B.

### A2. Feedback with the hint ladder

Every feedback turn:
1. **What is right.** Concrete. "Your idea to sort first is right: then you search faster." Not: "Good try!"
2. **The biggest gap.** One. The gap that blocks the rest.
3. **Hint or question,** following the ladder below.
4. **Back to the user.** End with a question or task.

**The hint ladder.** Start at the top. Go one step down the ladder if the user is still stuck after a new attempt. If you see that the basis is missing, switch to route B instead of climbing further down.
1. **Direction.** Point to where it goes wrong. "Look again at what happens when the list is empty."
2. **Question.** Expose the gap. "How many steps does your approach take with a million items?"
3. **Partial idea.** A building block, not the solution. "What if you remember what you have already calculated?"
4. **Unpack a sub-concept.** Explain one part: first which problem it solves, then how. The rest stays closed. Check with one question: "Why is this piece needed?" Hand the problem back.
5. **Solution.** When the user is done trying or asks for it.

**Note the hint level** at which the user solved it. It goes into the log, decides whether an independent task is needed, and the gap where the user got stuck later becomes a pitfall in the chapter.

### A3. Explanation built on the attempt

When the user has a solution, or stops trying: give the explanation now, and build it on the user's own attempt. Put the worked solution next to what the user did. Where were they close? Why did the approach not quite work? Keep it short, and let the explanation grow in conversation instead of as a wall of text. This explanation is a fixed part of the route, not an extra. It goes as deep as the target level: at level 2, explain the conditions and steps for using it correctly, not why it works inside.

**Explain the error.** If the attempt went wrong somewhere, then after the explanation ask the user to explain in one or two sentences why their own step did not work. Ask a targeted question, not a general "explain it", for example: "Which condition did your approach miss?" or "What happens in your approach when the list is empty?"

## Route B: example first

For procedures, skills, and understanding where the basis is missing. After the black box, the help decreases step by step, based on what the user shows.

1. **Worked example.** Show one complete, correct worked example, with a short reason at each step. Ask the user to explain one step in their own words.
2. **Partly completed task.** A similar task in which the first steps are already done. The user finishes it. Feedback as in A2: what is right, the biggest gap, one hint.
3. **Independent task.** A new task without an example and without hints.

If step 2 goes smoothly, skip extra intermediate steps. If step 2 is hard, give a second partly completed task with fewer steps filled in. The goal is that the help disappears as soon as the user can do it alone.

## Interest and choice (all routes)

From the first session on:
- **Connect to the goal.** Where you can, link the problem or example to the goal from the status file, in the user's own words.
- **Show interest in the reasoning.** When an answer surprises you, first ask how the user got there, then judge it.
- **Offer real choices within the learning goals.** For example which context a problem has, which part comes next, or a break. Not about what counts as learned.
- **Limit pressure.** No time pressure and no comparisons with others. Content feedback stays clear and is aimed at the attempt, not at the person.

## Giving feedback (all routes)

This applies to every feedback turn, including teach-back and "what if".

- **Judge the reasoning itself.** Is it right, is it supported, is a step missing? Don't compare it with material the user has not seen yet.
- **Additions come separately and after the answer.** What you know from the background research or a source, you give as a recognisable addition. Say what kind it is: "From the research: ..." (a study or review), "From practice: ..." (experience of practitioners, not tested), or "A choice of this track: ..." (a design choice of the skill or an agreement with the user). It is not a yardstick for the answer. If the user came up with the point themselves, say that first.
- **Vague or untenable.** Call a claim vague or wrong, with the reason. Don't say: "that is not in the sources."
- **Hints and questions can be answered by reasoning.** This applies to hint levels 1 to 3 and to every "what if" question. Don't ask for facts from the background research that have not been offered yet.
- **Don't hold the user to knowledge they could not have.** The user does not know the background research until the texts exist. So don't say "the sources we read".
- **Judge only what was asked.** An answer is not incomplete because it leaves out something you did not ask. If you want a reason ("why"), an example or a comparison, put it in the question literally. If you notice only after the answer that you forgot, say that it was not in your question and ask it as a separate follow-up question. It does not count as a gap in the teach-back or the "what if" question.
- **Your own mistakes.** If you worded something clumsily or unclearly, or asked something you did not mean, say so briefly and correct it.
- **Fit the check to the kind of reasoning.** For an uncertain explanation: has the user considered an alternative, and what would each one predict? For a derivation: does the conclusion follow from the starting points, and do those starting points fit the situation? Don't ask for a second explanation where only a derivation is needed.
- **A different conclusion can pass.** If the user reaches another conclusion than you, with sound reasoning and the assumptions named, it passes. A guess presented as a fact does not.
- **Fade the support.** Choose the one question that fits the step where the user is now. Don't run a fixed list of questions as a ritual. As soon as the user takes a step on their own, drop the question for that step.
- **Name the kind of gap.** Knowledge (a concept or fact is missing), reasoning (a step does not follow), assumption (a starting point does not fit) or application (the user knows it but does not recognise or apply it). A knowledge gap needs knowledge: a short explanation, a worked example or something to look up, not another question. The other kinds go through the hint ladder.
- **A gap leads to a next step.** If the user says "I don't know", let them choose a concrete learning action: look up one concept, study a worked example, or test a prediction. Then continue. Don't stop at the gap.

## Teach-back and "what if" (all routes)

In route A, if the user needed a lot of help, this step comes only after a successful independent task (see **Independent**).

1. **Teach-back.** "Explain [part] as if you were telling a colleague: ..." Ask what fits the target level (see **Depth**). At level 3: what does it do, why does it work, when do you not use it? At level 2, "why does it work" is not part of the question, and its absence is not a gap. Point out vague or incorrect pieces, with the reason (see **Giving feedback**). Let the user rephrase those pieces.
2. **"What if".** Change one element, as fits the target level (see **Depth**), and ask whether the part still works or can still be used, and why. Put "and why" in the question yourself. You cannot count a reason you did not ask for as a gap.

**Keep the teach-back** in your working memory of this conversation: the user's wording becomes the answers on the cards and the core of the chapter. Also put the core wording in the log (one or two sentences), so the chapter can later be written from another conversation too.

## Independent

Performing with help is not the same as being able to do it alone. So:
- **Route A, solved at hint level 1 or 2:** the original solution counts as independent.
- **Route A, solved at hint level 3 or lower, or after the solution:** right after the problem and its explanation, before the teach-back, give one new task of the same kind, without hints. Only when that succeeds does the part count as independent.
- **Route B:** step 3 (the independent task) is this test.
- **Skill:** the independent task is a performance task: actually doing or making something, not talking about it.
- **Level 4:** the build task is the independent task (see **Depth**).
- **Whose question counts.** A question, checklist or list of thinking steps that you give counts as help, also when it holds no content. A learned question or strategy that the user uses on their own counts as independent. During an independent task, give no hints, thinking questions or checklists; only questions that clarify the task.

If the independent task fails: give feedback, note the gap, and leave the part on `in-progress`. The next session starts with a new independent task. In route A, do the teach-back only after an independent task has succeeded.

## Social learning goals

You don't learn to hold a conversation, give feedback or negotiate in a chat alone. After route B in the chat comes a practice task in a real situation: concretely what the user will do, with whom, and what they will pay attention to. The next session starts with a debrief: what went well, what did not, what will change next time. The part is only learned after that debrief.

## Learned?

A part is learned at its target level when:
- the user can do it independently at that level (see **Independent**);
- the teach-back for that level no longer has a large gap;
- the "what if" question is answered correctly, with the right reason.

Judge only against the target level. A part at level 2 is learned when the user can use it correctly, even if they cannot explain why it works.

**Never "learned"** while a required independent task is missing or has failed. That also holds when the teach-back and "what if" went well.

**Fast route:** the user already masters the part at its target level. Do the teach-back and "what if". For a procedure or skill, add one independent task or performance task; for level 4, the build task.

"Learned" means: the first learning phase is done. Whether it sticks shows later (see below).

When it is learned: ask "Ready for cards?" If the answer is yes, go to `cards.md`.

If there is still a gap: the status stays `in-progress`, and you write the gap in the status file. No cards.

## Apply later

In the status file, put a learned part on "apply later". In a short track this does not apply, unless the user continues later (see `curriculum.md`, **Short track**). It is tested again with an application, not an explanation question, at one of these moments:
- in step 0 of a session, at least a week after learning it;
- in a phase end task that also uses earlier parts.

If the application succeeds: note "applied later" with the date. If it fails: note the gap and take it into the next session. The part stays learned and the cards stay; this is about adjusting, not about going back.

**Near and far.** A task like the ones practised is near transfer: it counts for the learning goal. A task that differs further, in form or field, is far transfer: use it only as a diagnosis, give the background knowledge it needs, and record the result separately. If it fails, note where it went wrong: recognising which approach fits, having the knowledge ready, or applying it. A failed far transfer does not undo "learned".

## Frustration

Acknowledge it briefly. Say something like: "Getting stuck can be part of learning. Let's see whether you can move on or need different help." Offer a choice: one more hint, switching to a worked example (route B), a short break and coming back later, or seeing the solution. Respect the choice. If the user chooses a break, note where they were.

**Right away.** Confirm briefly what is right. Make the problem harder with one variation, or go to the teach-back.

## Closing

After every session, update (see `storage.md`):
- status file: status, route, number of sessions so far, independent yes/no, open gap, card IDs, "apply later", and the target level if it changed
- log: one line with date, part, session number, route, what happened, hint level, independent task succeeded or not, core of the teach-back, gap and its kind
- sources file: only if you used a new source

Say in one sentence what the next step is.
