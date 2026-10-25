# Building a curriculum

A curriculum starts with what the user wants to be able to do, not with a level label. You work back from the end: first the goal and the end tasks, then what they require and how deep, then what fits in the available time.

A track can last from a few hours to several months. For a track of one day or less, follow this file with the changes in **Short track** at the end.

## Step 1: Intake

**Open questions, one per turn:**
- **Goal.** "Why do you want to learn this, and what do you want to achieve with it?" Write the answer down as one sentence, in the user's words. It decides what is in and out of the track (step 4) and opens the introduction.
- **End tasks.** "What do you want to be able to do afterwards? Think of three to six concrete things, in the form 'I can ...'." Help make vague goals concrete: "understand statistics" becomes "read a research report and say whether the conclusion holds".
- **Anchor source.** "Are you following a book, course or exam syllabus? Then I'll follow its order and terms."

**Multiple choice, together in one message** (with a question tool if there is one, otherwise as numbered options in text; see `platform.md`):
- **Duration:** a few hours or one day / 4 weeks / 8 weeks / 3 months or a fixed end date
- **Sessions per week:** 1 / 2-3 / 4-5 / daily
- **Session length:** 15 min / 30 min / 45 min / 60 min or more
- **Spaced repetition app for the cards:** Active Retrieval / Anki / another app / none yet

If the user already named a short budget, such as "I have two hours", you know the duration: ask only the questions that are still open. If the user chooses "a few hours or one day", ask one follow-up question about the total time and whether it is one block or several blocks with breaks. Sessions per week then don't apply.

The spaced repetition app sets the card format (see `cards.md`). For another app or none yet: say that the cards come as an Anki text file, because many apps can import it.

The deck name is the curriculum name. If the user chooses Active Retrieval, also choose a deck emoji that fits the subject. Name it and say that the user can change it.

## Step 2: Background research

Goal: know how the subject is structured, which misconceptions are known, and how it is best learned. You use this to choose the order, make good problems and give honest feedback.

### What counts as a source

Use recent, scientifically grounded material with authority wherever you can.

**Recent.** Search first for work from the last five years. An older source may serve as a foundation (a classic experiment, a standard work), but then search for newer work that confirms, qualifies or refutes it. Note the year of every source.

**Ranking,** from strong to weak:
1. Meta-analyses and systematic reviews in peer-reviewed journals, preferably from the last five years
2. Guidelines and overviews from authoritative institutions: scientific academies, government institutes, Cochrane and Campbell, education institutes with evidence summaries (such as the Education Endowment Foundation or the What Works Clearinghouse), and for technical subjects the official standard or specification
3. Large randomised experiments in peer-reviewed journals
4. Smaller experiments and review articles
5. Handbooks from recognised publishers and official documentation
6. Preprints: only with the label "not peer-reviewed"
7. Blogs, news articles and practice stories: only as practical experience, never as evidence. Use a news item at most to find the underlying study, and then cite that study.

**Check.**
- Go to the primary source. A summary or blog about a study is not a source for the study.
- Prefer a DOI or the journal's page.
- For a striking result, search whether the study was retracted or corrected (search for the title plus "retraction" or "correction").
- If sources contradict each other, note it. Don't silently choose the source that suits you best.
- **Effect sizes.** For every effect, note: the measure (g, d, r or something else), the value, the margin of uncertainty (confidence interval) if there is one, what it was compared with, and what it means in practice. Use rules of thumb only as a rough direction, and only with the measure they belong to:
  - **d and g** (difference between groups): around 0.2 small, around 0.5 medium, around 0.8 large.
  - **r** (correlation): traditionally 0.1 small, 0.3 medium, 0.5 large. In many fields correlations are lower; there, 0.1, 0.2 and 0.3 are closer to small, typical and large.
  - A small effect can mean a lot in practice, and a large effect in an artificial setup can mean little. Say so.

### Searching

Four to eight short searches (two to six words). Vary them:
1. `[subject] meta-analysis [current or previous year]`
2. `[subject] systematic review`
3. `[subject] misconceptions` or `[subject] common errors`
4. `learning [subject] instruction study`
5. `[subject] curriculum` or `[subject] prerequisites` for the structure
6. A search on the site of an authoritative institution in the field
7. If the user's language is not English: one search in that language for local guidelines or sources
8. If there is an anchor source: look it up and read the table of contents

Open the best sources in full if the summary is too thin.

**Non-empirical subjects** (an algorithm, a mathematical concept, a standard): find the authoritative source for what it is and does (the specification, the standard work), plus known pitfalls. Write honestly: "No empirical research on the subject itself."

**No search function:** say so. Work from your own knowledge and mark the research map as "unchecked". Don't add sources to the source list.

### Recording

Write the research map, the search log and the sources to the sources file (format in `storage.md`). Don't show the map to the user before they start: too much explanation up front takes away the thinking for themselves. Say in one sentence that the research is saved and that the user receives it as `05-research.md` when the curriculum is confirmed.

## Step 3: Prior knowledge test

Four to six short questions that together cover the whole subject, from the basics to the hardest end task. This is one of the exceptions to the rule of one question per turn (see `SKILL.md`).

- Mostly open questions: "What would you do if ...", "Why ...". No yes/no.
- Say that wrong answers or "I don't know" are fine: the test decides where the track starts, and questions asked beforehand help learning even when you answer them wrongly.
- After the answers, give no long correction. One sentence per question: mastered, partly, or new. The explanation comes in the sessions.
- **Level per answer.** For yourself, note which level of the depth pyramid each answer shows (see step 4): can the user say what it is for, use it, explain why it works, or build it? Step 4 compares this with the level the end tasks need.
- **The test gives direction, not a complete picture.** Four to six questions don't cover a broad subject. Treat the judgement per part as provisional, and adjust it as soon as a session shows something else. When in doubt between "mastered" and "partly", choose "partly".

## Step 4: Scope and depth

Before you make parts, decide together with the user what is in the track, what is out, and how deep each topic must go. This is where most time is won or lost: a topic learned deeper than the end tasks need costs sessions without bringing the goal closer.

### The depth pyramid

Show the user the pyramid, short and in their language. You start at the top. Each level includes the levels above it, and each level down costs more time.

```
1. Overview   what it does, what you use it for, when not
2. Use        apply it correctly in a real task
3. Inside     why it works: predict, find errors, adapt
4. Build      derive or rebuild it yourself, design a variant
```

| Level | The user can | You test it with |
| --- | --- | --- |
| **1 Overview** | say what it does, what goes in and what comes out, when to use it and when not | one question: in which of two situations do you use it, and why? |
| **2 Use** | apply it correctly in a new, concrete task, including its conditions | an independent task |
| **3 Inside** | explain why it works, predict what happens when something changes, find an error in it | a teach-back with "why", and a "what if" |
| **4 Build** | derive or rebuild it without an example, or design a variant for a new situation and justify it | a build task without an example |

### Choose the lowest level that is enough

Go through the topics from the end tasks and the research map. For each topic:

1. **Propose the lowest level** at which every end task that needs the topic succeeds.
2. **Every level deeper needs a reason.** Ask yourself, and the user when in doubt: "What goes wrong in your end task if you can only [the previous level]?" If there is no concrete answer, don't go deeper.
3. **Good reasons for level 3:** the end task asks to predict what happens in a new situation, to find errors, to adapt it, to choose between alternatives because of how they work, or to explain it to others.
4. **Good reasons for level 4:** the user wants to build, teach or research it, or an end task asks for a new variant.
5. **Interest is a reason too,** but it costs time. The user chooses it knowingly, and the reality check counts it.
6. **A prerequisite needs less depth than you think.** That another part depends on a topic does not mean the topic needs level 3. Often level 1 or 2 is enough.
7. **Compare with the test.** If the test shows the user is already at the target level, the topic needs no part of its own, or only the fast route.

Be critical, also of your own proposal. Say which levels you doubt, and why.

### Offer level 4

Level 4 is never the default, but you always offer it. Name one or two topics where building it yourself could be worth it, say roughly what it costs, and ask whether the user wants that. For example: "Do you want to be able to simulate a p-value yourself? That costs about two extra sessions."

### Show the scope

```
Goal:       [one sentence from the intake]
End tasks:  I can ...

In the track
| Topic                  | Level      | Why this depth                                     |
| t-test                 | 1 Overview | recognise when it fits; calculating is not needed  |
| p-value                | 2 Use      | reading it correctly is enough                     |
| sample and population  | 3 Inside   | you must see for yourself why a sample can be skewed |

Out of the track
- calculating tests yourself: no end task asks for it → follow-up
- regression: outside the end tasks → follow-up
```

Ask the user, in one question, to confirm or adjust the scope. Put it in the status file. What is out of the track goes to **Next steps and broadening** in step 7.

**Level 1 topics** usually don't become a part of their own. They get a row in the black box table at the start of the phase, and a check question in the session of the part that uses them (see `session.md`).

## Step 5: First draft

Derive the parts from the scope, the end tasks and the test.

- **Shape:** two to four phases, three to six parts per phase.
- **Part:** one concept or skill at its target level, learnable in one or two sessions of the chosen length. Larger? Split it, or check whether the target level is too high.
- **Target level per part:** from step 4. It sets how far a session goes, what the teach-back asks and when the part is done (see `session.md`).
- **Order:** by dependency. What another part needs comes first.
- **Numbering:** parts are numbered across all phases: 01, 02, 03, ...
- **Learning goal type per part.** Give each part one type. The type sets the route in a session (see `session.md`):
  - **understanding:** grasping how something works and why ("why is a p-value not the probability of H0?")
  - **procedure:** carrying out a fixed series of steps correctly ("calculate a t-test")
  - **skill:** doing or making something, with practice ("assess a research report")
  - **social:** doing something with other people ("give feedback on a colleague's analysis")
- **Phase end task:** every phase ends with a task that combines the parts of that phase, and also parts from earlier phases. Don't say which parts are needed: the user decides which approach fits. This also tests whether earlier parts can still be applied later.

### Assessment list per end task

For every end task and every phase end task, set out beforehand, in three to five lines:
- **what must go well** for the task to count as passed;
- **which errors are essential**, and which are not;
- **how much help is allowed** (usually: no hints, but questions to clarify the task are fine).

Show the list to the user and ask them to confirm it. Later, assess the task against this list, not on gut feeling. Put the list in the status file.

### Estimating

No research says how many sessions a learning part takes or how much buffer a personal learning track needs. What is well researched is how people underestimate and what helps against it. This method is built on that:

1. **Split.** Split each part into the steps of its route up to its target level (for example black box, problem, feedback rounds, explanation, independent task, teach-back, and for level 4 a build task) and estimate those. Splitting makes estimates less optimistic.
2. **A range, not a point.** Give a lowest and highest estimate in sessions per part, based on the test (new, partly or mastered) and the distance between the level the test showed and the target level. Add up the low ends and the high ends separately.
3. **Count back from the end date.** Plan from the end date back to today: what must be done in the last week, and in the week before? Planning backwards gives more realistic estimates than planning forwards.
4. **No fixed buffer percentage.** A fixed percentage has no basis for this kind of track. Use the high end of the range as the planning basis, and replace it with measured pace as soon as possible (see "Adjusting along the way").

Also estimate roughly how many cards the track will produce, based on the number of pieces of knowledge per part (see `cards.md`). This is a rough estimate; say so.

## Step 6: Reality check

Work it out together and show it:

**Budget the reviewing first.** Reviewing in the spaced repetition app is real time and belongs inside the weekly budget, not beside it. Ask in one question how many minutes per week the user already spends on reviewing, and how many at most. Subtract that from the weekly time. What remains is the time for learning sessions.

```
Weekly budget:     [total] min per week
Reviewing:         [r] min per week reserved
Learning sessions: [weeks] × [sessions that fit in the rest] = [B] sessions
Needed:            [low] to [high] sessions
Cards:             about [K] for the spaced repetition app
```

Then three lists:
- **Fits:** what falls within the time, even at the high estimate
- **Almost fits:** what can be added if the pace turns out better
- **Out of reach:** what is not feasible in this setup

Say that the review load grows with every learned part. How much exactly depends on the cards and the app's algorithm; you measure that along the way instead of guessing now.

If it does not fit, lay out the options and let the user choose:
- a lower target level for some topics: this often saves the most time without dropping an end task
- a smaller goal (fewer or simpler end tasks)
- a longer duration or more sessions per week
- moving parts to a follow-up curriculum

Give your own advice, with a reason. Then ask what the user chooses.

**Concrete session times.** Finally, ask on which days and at what times the sessions fit. A concrete "when and where" plan helps to start on time and limit interruptions. Put it in the status file.

## Step 7: Confirm

1. Show the final curriculum compactly: goal, phases, parts with target level, status and range, level 1 topics without a part of their own, end tasks.
2. Add the section **Next steps and broadening**:
   - **Follow-up curriculum:** what is out of the track (step 4) or was moved out at the reality check, plus the logical next step after the end tasks
   - **Could add:** related subjects, and deeper levels that the goal does not need but that strengthen it, such as level 4 for a topic the user did not choose it for
3. Ask for agreement.
4. Save the three files (`storage.md`).
5. Deliver `00-introduction`, `01-overview` and `05-research` (`texts.md`).
6. Start phase 1 with the black box table.

## Adjusting along the way

- **Measure, don't remember.** People underestimate afterwards how long something took. So count the actual number of sessions per part and put it in the log. Don't ask the user to say it from memory.
- **Own pace as reference.** After three learned parts, and then after every phase: divide the measured sessions by the estimated ones (midpoint). That is this user's correction factor. Apply it to the rest of the track and put it in the status file. Your own history is a better predictor than a plan.
- **Project the end date** with the measured pace. If it falls after the duration, redo step 6.
- **Stop at the target level.** When a part reaches its target level, it is done, even if more is possible. Offer the deeper level as a choice, with what it costs.
- **Change a level only with a reason.** Deeper: if the user keeps making the same error in use that only knowledge of the inside prevents, propose to take that one detail a level deeper, and then return to the whole. Shallower: if a part takes much longer than estimated while the end task needs less, propose a lower target level. Either way, it is a change (see below).
- **Measure the review load.** At the end of every phase, ask how many minutes per week reviewing in the spaced repetition app now takes (from the app or the user's own measurement). If it exceeds the reservation, lay out the options: apply the card filter more strictly, slow down new parts, or free up more time. Put the measured review time in the status file.
- **The other way too.** If it goes faster than estimated, say so as well, and offer parts from "Almost fits" or "Could add".
- **Out of scope:** if something interesting comes up in a session that the end tasks don't need, put it under "Could add". The track does not quietly grow.
- **Changes:** always in consultation, always in the log with the reason, and then a new version of `01-overview`.

## Short track

A short track lasts one day or less, for example two hours or an afternoon. The approach in the sessions stays the same: trying first or an example first, teach-back, "what if" and cards. What changes is the size and the planning around it.

- **Intake.** One to three end tasks instead of three to six. Ask for the total time and whether it is one block or several blocks with breaks. An anchor source is optional.
- **Background research.** Two to four searches instead of four to eight. Record them in the sources file as usual.
- **Prior knowledge test.** Two to four questions instead of four to six.
- **Scope and depth.** As in step 4, but strict: most topics at level 1 or 2, level 3 for at most one core topic. Still offer level 4, usually as a follow-up after the track.
- **Shape.** One phase with two to four parts. Each part fits in one session of 20 to 45 minutes. If the end tasks need more, make the goal smaller or suggest a longer track.
- **End task.** One end task at the end, if time allows, with a short assessment list. If there is no time, the teach-backs and independent tasks are the test.
- **Estimating.** Give the range per part in minutes instead of sessions. Count back from the end time.
- **Reality check.** Calculate with the total time in minutes. Reserve about ten minutes per part for the teach-back, "what if" and the cards. Don't reserve review time within the budget: reviewing in the spaced repetition app starts after the track. Do say how many cards the track will roughly produce, and that reviewing them takes a few minutes a day in the weeks after.

```
Total time:        [total] min
Per part:          [low] to [high] min, plus about 10 min for teach-back and cards
Needed:            [low] to [high] min
Cards:             about [K] for the spaced repetition app
```

- **Confirm.** Show the curriculum in the chat and save the three files. Don't deliver texts at the start: they would cost time the user wants to spend learning.
- **Adjusting.** Don't calculate a correction factor; there are too few parts for that. After every part, compare the time used with the time left, and say early if a part no longer fits.
- **Apply later.** Doesn't apply within a short track. If the user continues later, apply it then.
- **At the end.** Deliver one chapter with all parts (`[slug]-10-phase-1.md`) and the research file (`[slug]-05-research.md`), see `texts.md`. If the user wants to continue, offer to turn it into a longer track: redo the intake questions about duration and sessions, and the reality check with a weekly budget.
