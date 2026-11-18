# Week reflection: design and rationale

This document explains why the skill works the way it does. For each choice it states what was decided, why, what it rests on, and which alternative was rejected. Source references appear as [S1], [S2] and so on. The source list at the bottom says for each source what was opened.

Written 18 November 2026.

## Goal

You make many project decisions in a week. A weekly reflection is useful when it looks closely at one of them: what you chose, what else was on the table, what you expected and what you actually saw. This skill keeps that conversation short and hands the next step back to you.

## Choice 1: One decision, not the whole week

**Decision.** A conversation looks at one project decision. If you bring several, the skill asks which one to take first.

**Why.**

- Debriefs and after-action reviews work by focusing on a specific event: what was supposed to happen, what happened, why, and what to do next. A meta-analysis of 46 samples (N = 2,136) found that debriefs improved effectiveness by about 25% (d = .67) over a control group, with similar effects for teams and individuals, in simulated and real settings [S1].
- A review that covers every project turns into a status meeting. It spreads attention and makes it easy to stay on the surface.
- One decision fits in a short session, so the reflection can become a weekly habit.

**Rejected.** A full week review with a template for every project. It looks thorough, but it invites a report rather than a reflection.

**Limitation.** The meta-analysis is about debriefs in training and work settings, mostly with teams. It does not test a solo weekly reflection.

## Choice 2: One question per turn

**Decision.** Every message from the coach has exactly one question mark. The coach waits for the answer before asking the next question.

**Why.**

- The user does the interpreting. A question leaves the thinking with them; a list of questions or a form lets them answer quickly and move on.
- One question also makes it harder for the coach to smuggle in a conclusion. If the coach has a second question, it waits.
- A short turn is easy to answer. A wall of prompts is easy to skim.

**Rejected.** A fixed questionnaire such as "what went well, what went badly, what next". It is efficient, but it becomes a form that can be filled in without looking closely.

**Limitation.** This is a practice choice, not a research finding. Some users prefer a form; they can change the skill.

## Choice 3: Alternatives and expectations before the outcome

**Decision.** The conversation reconstructs the alternatives and what the user expected before it asks what actually happened.

**Why.**

- Once people know the outcome, they overestimate how predictable it was. Fischhoff (1975) is the classic demonstration that outcome knowledge changes judgments of what was foreseeable [S2].
- Asking "what else was on the table?" before "what happened?" gives a record of the actual choice set, not a set reconstructed after the result.
- Asking what the user expected before the outcome gives a comparison point. Without it, the conversation becomes a story about the result.

**Rejected.** Starting with "How did it go?" It is the natural opening, but it anchors the whole conversation on the outcome.

**Limitation.** The ordering is a derivation from hindsight-bias research, not a tested protocol for weekly reflection.

## Choice 4: Observed effect, not just a feeling

**Decision.** The coach asks what the user actually saw: an event, a number, a comment, a change in the work or a missed deadline. It asks what they saw that tells them an interpretation is true.

**Why.**

- After-action reviews compare the intended effect with the actual effect. A feeling is part of the picture, but it is not the same as the effect.
- Reflection is worth doing. In ten experiments (N = 4,340), reflecting on accumulated experience was sometimes more valuable than accumulating more practice, especially early in a learning curve when there was enough experience to reflect on [S3].
- A concrete observation gives the user something to compare across weeks. "It felt slow" is harder to learn from than "the review took two days longer than planned".

**Rejected.** "How do you feel about it?" as the main question. Feelings matter, but they are not the observed effect.

**Limitation.** Not every effect is measurable. The skill accepts a concrete observation, not only a number.

## Choice 5: The user chooses the next step

**Decision.** The coach asks for the next step and waits. It never proposes one unasked. If the user asks the coach to choose, the coach offers at most three options and hands the choice back.

**Why.**

- A step chosen by someone else is easier to drop. The reflection belongs to the user, so the step does too. This is a practice choice, not a tested effect of this skill.
- Specific plans help goal pursuit. Implementation intentions, plans in the form "when situation X arises, I will do Y", have strong effects on goal attainment [S4]. That is why the skill asks for one concrete next step rather than a list of intentions, and why the user names it.

**Rejected.** The coach recommends the best next step. It is faster, but it turns reflection into advice and takes the choice away.

**Limitation.** The implementation-intention research is about goal pursuit, not about reflection conversations. The skill borrows the value of a specific, self-chosen plan.

## Choice 6: No score and no verdict

**Decision.** The coach does not label the decision good or bad, and does not score the week. It asks what the user would do differently and lets them name the lesson.

**Why.**

- A performance review invites defensiveness. The user starts arguing for the decision instead of looking at it.
- The point is to see the decision more clearly, not to grade the person who made it.

**Rejected.** "What went well and what went badly" scoring. It is familiar, but it evaluates before the evidence is on the table.

**Limitation.** This is a practice choice. Some users want a verdict; the coach can give one only when asked, and then as an option, not a judgment.

## Choice 7: Fictional examples in public files

**Decision.** The examples in `SKILL.md` and the README are invented and labelled as fictional.

**Why.**

- A reflection contains a real project, real client names, real numbers and sometimes real mistakes. The public files must not carry someone's real week.
- An invented example shows the shape of the conversation without exposing a project or the people in it.

**Rejected.** Using the author's own week as the example. It would be more authentic, but it would publish details that belong to a project and the people in it.

**Limitation.** A fictional example cannot show every kind of decision. It shows the rhythm, not the content.

## Choice 8: No storage and no scripts

**Decision.** The skill runs in any chat. It does not need to save a file, search the web or run code. The conversation is the deliverable.

**Why.**

- It keeps the skill usable in Claude, ChatGPT and other assistants without setup.
- A weekly reflection should be easy to start. A log with scores and trends adds work before the first question.

**Rejected.** A weekly log with scores and trends. It could be useful, but it makes the skill about the log instead of the conversation.

## Limits

- The research is about debriefs, reflection and goal pursuit, not about this exact weekly conversation. No study tested this format.
- Most debrief research is with teams in training or simulation. The solo, project-decision version is a derivation.
- The one-question rule, the no-verdict rule and the closing after the choice are practice choices.
- The skill is not therapy or a performance review.

## Sources

- [S1] Tannenbaum, S. I., & Cerasoli, C. P. (2013). Do team and individual debriefs enhance performance? A meta-analysis. *Human Factors, 55*(1), 231-245. https://doi.org/10.1177/0018720812448394. Abstract opened.
- [S2] Fischhoff, B. (1975). Hindsight is not equal to foresight: The effect of outcome knowledge on judgment under uncertainty. *Journal of Experimental Psychology: Human Perception and Performance, 1*(3), 288-299. https://doi.org/10.1037/0096-1523.1.3.288. Metadata and topic tags opened; the full article was not.
- [S3] Di Stefano, G., Gino, F., Pisano, G., & Staats, B. R. (2014). Learning by thinking: How reflection can spur progress along the learning curve. Working paper. https://doi.org/10.2139/ssrn.2414478. Abstract opened.
- [S4] Gollwitzer, P. M. (1999). Implementation intentions: Strong effects of simple plans. *American Psychologist, 54*(7), 493-503. https://doi.org/10.1037/0003-066X.54.7.493. Abstract opened.
