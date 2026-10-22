# Design taste: what taste is, and why the skill works this way

This document explains what the skill means by taste, and why it works the way it does. The first half is a meta-analysis: what two published design skills and the research on aesthetic judgement say taste is, and where they agree. The second half lists the choices the skill makes, each with its reason and the alternative that was rejected. Source references appear as [S1], [S2] and so on. The source list at the bottom states for each source how it was checked.

Written 22 October 2026.

## Goal

When an assistant makes something people look at, such as a web page, an app screen, a slide deck or a document, the result should look decided, not assembled. It should fit its subject and its use so well that it could not belong to a competitor, and it should still be easy to use. The skill does this with instructions only, so it works in every assistant that reads skills.

## Part 1: What taste is

### The two skills that were studied

**Impeccable** [S1] is a large design skill for coding agents: one skill with 24 commands, about 415 KB of reference files, a compiled engine and 61 deterministic detector rules. It sorts each surface into a mode by what the visitor's success looks like (persuade, operate, read, experience), asks what will change the work, and then makes the agent derive five to seven candidate directions from the audience's cultural world. A script then deals the direction to build, "breaking the ranking rut", and the agent has to beat it with a fused challenger or build it. A separate reviewer agent checks the rendered result against the written direction.

**Taste Skill** [S2] is a design skill for web pages and app screens, built on a study of 247 gallery sites (One Page Love and Awwwards Sites of the Day) that 21 model reviewers scored. A script deals three of twenty researched directions, the agent picks the one that fits the subject, and a browser inspector fails the page on measured "tells". The agent then critiques its own screenshots with a fourteen-pass rubric for up to three rounds.

Both are large and depend on scripts. Both start from the same diagnosis, and that diagnosis is the most useful part of them.

### Their shared diagnosis: the model ships the mode

Taste Skill puts it in one line: a page built by a model looks like the average of every page the model has seen, and "nothing in it is wrong and nothing in it was decided" [S2]. Impeccable says that AI-generated interfaces cluster around a few looks regardless of subject, and that "if someone could guess your aesthetic from the category alone, or from category-plus-avoidance", the work failed [S1].

The research explains why. People find easy-to-process things more pleasant: symmetry, contrast, repetition and prototypicality all raise processing fluency, and fluency is felt as beauty [S5]. Annotators who rate model outputs share that bias, so preference data rewards the typical answer, and alignment sharpens models towards it. Zhang and colleagues call this typicality bias and show it is a data-level cause of mode collapse [S7]. A model's first design idea is therefore the category's most typical idea, by construction.

The cost also shows up at group level. In an experiment with short stories, ideas from a language model made each story better, most of all for the least creative writers, but the stories became more similar to each other [S6]. Design help from a model can do the same: every single page improves and all pages converge.

So taste, for an assistant, starts as a correction: noticing the mode and deciding whether to stay there.

### Seven claims about taste

Reading the two skills next to the philosophy and psychology of aesthetic judgement gives seven claims that hold up across sources.

**1. Taste is judgement, not preference.** If taste were only preference, nobody could get better at design. Designers do get better, and they see their earlier taste as worse, not just different [S8]. Hume made the same argument in 1757: individual responses differ, but some judges are better than others, and what makes them better can be named [S9]. A skill can therefore teach taste. It cannot teach it as a list of likes.

**2. Taste is fit between a form and its context.** Alexander defined design as making a form that fits its context, and noticed that we recognise misfit much more easily than fit [S10]. Both skills say this in their own words. Impeccable lets the mode of the surface set the ambition: bold on a landing page, precise and restrained on a working screen [S1]. Taste Skill found that what separated the best gallery sites from forgettable ones was an idea taken from the subject itself, not the styling [S2]. Its competitor test makes fit checkable: put the nearest competitor's name in the idea sentence. If the sentence still works, the idea belongs to the category, not to the client.

**3. Taste balances the typical and the new.** Loewy's MAYA principle, "most advanced, yet acceptable", was tested by Hekkert and colleagues: typicality and novelty are opposed, yet both predict preference, and each hides the effect of the other when measured alone [S4]. The best design is as new as it can be while the audience still recognises what it is. Pure fluency is bland; pure novelty is rejected. Experts give novelty more weight than novices [S4]. This is why the skill does not simply ban the familiar: a shop must still look like a place where you can buy something.

**4. Taste is trained pattern recognition, and the feeling of being right proves nothing.** Hume's good judge has delicacy improved by practice and perfected by comparison [S9]. Kahneman and Klein state when intuition becomes skill: in a regular environment, with the chance to learn its patterns through feedback. They add that subjective confidence is not a reliable sign of accuracy [S11]. Experts look at art more in terms of style, and novices more in terms of personal feeling [S12]. For an assistant, the comparison has already happened in training, but the feedback on this particular artefact has not. That is why both skills make the agent look at the rendered result, and why Taste Skill tells it to judge only the screenshots: "you wrote the code, so you will read your intentions into it" [S2].

**5. Taste is decision, and removal is not a decision.** This is the most important lesson from the testing of Taste Skill. In blind comparisons judged by a model juror, the skill lost to building with no skill at all in four of five rounds, until it stopped only removing ornaments and started demanding substance: larger type, whole fields of colour, real pictures, full content [S2]. Its critique rubric notes that a richer page full of template devices beat a cleaner page that was thin, every time. Its registry of tells calls the result of pure removal "an empty page with good manners". Impeccable reaches the same point from the other side: "when torn between refined and committed, commit" [S1].

**6. Taste is coherence.** One idea, carried into every part. Impeccable asks to "commit every atom": navigation, buttons and inputs rebuilt in the chosen world's vocabulary [S1]. Taste Skill found that the commonest failure, even among good sites, was a distinctive first screen followed by stock blocks [S2]. A choice that is right on its own but belongs to another system reads as a mistake.

**7. Taste has a social side, so rules about taste date.** Bourdieu showed that taste also marks social position: what counts as good taste is set by people with cultural capital and spreads as distinction [S13]. Devices start as signs of care on good sites, get copied, become cheap, and turn into signs of no care. Taste Skill documents this with a dated registry of three waves of generated-page tells. The third wave is the published remedy for the first two ("warm it up and make it editorial"), which models adopted wholesale [S2]. Impeccable warns about the same cream-and-serif look, and adds a note to its Claude build that this model's own measured default for warm subjects is cream grounds and italic serif display [S1]. Both skills therefore refuse to name replacement fonts or colours: every "use this instead" list becomes the next wave. Replacements must be procedures.

Taste Skill is also honest that part of its rules are house style, not evidence. Monospace labels, index numbers and hairline rules are *more* common on top-scored sites than on weak ones in its own data, and it bans them anyway, as the owner's choice [S2]. A skill about taste should say which of its rules are evidence and which are opinion.

### A working definition

Taste is the trained judgement that picks, from everything that would work, the form that fits this subject and this use best, carries that choice through every part, and can explain each choice. For an assistant it has three practical parts:

1. **Notice the default.** Name the category's usual answer and your own usual answer before choosing.
2. **Choose by fit.** Pick the least typical option that the audience still accepts, and that only this subject could own.
3. **Look and correct.** Judge the result as a stranger would, on what is visible, not on what you meant.

## Part 2: Choices

### Choice 1: Instructions only, no scripts

**Decision.** The skill contains only Markdown. It works for any visual artefact the assistant can make, in any assistant that reads skills.

**Why.** Both studied skills depend on scripts: a dealing script, a browser inspector, a compiled engine. That ties them to coding agents with Node or a binary, a browser and a shell. The ideas that carry the quality (noticing the default, choosing by fit, looking at the result) need no code. The skill may still run code to render and screenshot an artefact when the assistant can.

**Rejected.** A detector script. It measures what can be measured, and the research above says the decisive failures (no idea, no fit, thin content) cannot be measured that way.

### Choice 2: Candidates with typicality instead of dice

**Decision.** Before choosing a direction, the assistant writes the rut (the category's usual answer, its predictable opposite, and its own known defaults), then five to seven candidates from the subject's world across at least three material families, each with an honest estimate of how often a model would land there. It strikes the rut, and chooses the least typical candidate that passes the fit tests.

**Why.** Both skills use randomness to break the mode, because a model asked for one idea returns the typical one. Without scripts there is no true randomness. Asking a model for several candidates with their probabilities is a prompting method that raised diversity in creative writing 1.6 to 2.1 times over a direct request [S7]. Choosing the least typical candidate that is still acceptable is MAYA made into a procedure [S4]. The fit tests stop novelty for its own sake.

**Rejected.** Pseudo-random selection, such as counting letters in the brief. It looks like a die but is not one, and it hides the choice instead of making it.

### Choice 3: The mode sets the ambition

**Decision.** Every surface gets one mode: persuade, operate, read or experience. The mode decides how far expression may go. The terms come from Impeccable [S1].

**Why.** Fit means different things for different uses (claim 2). A landing page that looks like a spreadsheet fails, and so does a spreadsheet that looks like a landing page. Taste Skill draws the same line between pages that are read and screens that are worked in, with separate rules [S2].

### Choice 4: The brief wins, and refinement preserves

**Decision.** Aesthetics, fonts, colours or eras the user pins override the skill's taste. A refinement keeps the existing identity; a redesign replaces it on purpose.

**Why.** Impeccable states it plainly: "Redirecting a clear brief toward your taste is failure" [S1]. Taste is fit to context, and the user's stated constraints are part of the context.

### Choice 5: Substance before restraint

**Decision.** Every element the skill removes is replaced: by scale, by full content, by a real picture, by a field of colour, or by a deliberate rest. A page is not done when nothing is wrong with it.

**Why.** Claim 5. In Taste Skill's own tests, removal alone lost to no skill at all [S2].

### Choice 6: Judge the render, not the intention

**Decision.** When the assistant can render the result, it looks at it at the sizes it ships at and critiques what it sees. When it cannot, it says so and marks its judgement as unchecked.

**Why.** Claim 4. Confidence is not accuracy [S11], and the builder reads intentions into the code [S2]. Both skills make looking a required step.

### Choice 7: A dated list of defaults, with evidence and opinion apart

**Decision.** `references/tells.md` lists current defaults, each marked with when it became a default, whether the evidence or the house style condemns it, and a procedure instead of a product to replace it.

**Why.** Claim 7. A list without dates hardens into dogma; a list of replacement products becomes the next default.

### Choice 8: Never invent proof

**Decision.** The skill may write sample content (dish names, sample data) when the brief leaves gaps, and lists it for the user. It never invents customers, quotes, reviews, logos, prices or statistics.

**Why.** Both skills draw this line [S1] [S2]. Invented proof is a lie, and a design that needs it to look finished is not finished.

## What the two skills teach, side by side

| | Impeccable | Taste Skill | This skill |
| --- | --- | --- | --- |
| Diagnosis | Output clusters around a few looks | Output is the average page | Both, explained by fluency and typicality bias |
| Breaking the mode | Script deals one of your candidates | Script deals 3 of 20 researched directions | Candidates with typicality, least typical that fits |
| Fit | Mode of the surface, the user's cultural world | Inventory of what only this client has, competitor test | Mode, inventory, competitor test |
| Checking | Detector rules, separate reviewer agent | Browser inspector, 14-pass self-critique | Critique passes on the render |
| Size | ~415 KB references, engine, scripts | ~340 KB references, data library, scripts | Markdown only |
| Media | Web and native app UI | Web pages and app screens | Any visual artefact |

## Known limitations

- The skill has not been tested in blind comparisons. Taste Skill's tests show that a design skill can make results worse than no skill [S2]; the same could be true here.
- Taste Skill's study used model reviewers on still frames, not human jurors [S2]. Its numbers describe gallery fashion as much as quality, as it says itself.
- Without randomness, the candidate list can still converge on a second-order default. The typicality estimates are the model's own guesses.
- Without rendering, the critique passes run on code or descriptions, which is weaker evidence.

## What this document does not prove

The sources support the elements one by one. They do not prove that this combination produces better design. The seven claims are a synthesis, not a finding of any single study.

## Sources

For each source, this states how it was checked when this document was written:
- **opened:** the page, repository or article was read
- **location confirmed:** title, authors and location confirmed via a search result, content not reread
- **via secondary source:** the content comes from an overview or summary by others

| ID | Source | Check |
| --- | --- | --- |
| S1 | Bakaus, P. Impeccable. GitHub repository, Apache 2.0. https://github.com/pbakaus/impeccable (read 22 October 2026: `skill/SKILL.src.md`, `reference/craft-floor.md`, `reference/new-work.md`, `reference/critique.md`, README) | opened |
| S2 | Leonxlnx. Taste Skill v2. GitHub repository, MIT. https://github.com/Leonxlnx/taste-skill (read 22 October 2026: `SKILL.md`, `references/research.md`, `references/tells.md`, `references/critique.md`, README) | opened |
| S3 | Loewy, R. (1951). *Never Leave Well Enough Alone*. Simon & Schuster. Source of the MAYA principle. | via secondary source [S4] |
| S4 | Hekkert, P., Snelders, D., & van Wieringen, P. C. W. (2003). "Most advanced, yet acceptable": Typicality and novelty as joint predictors of aesthetic preference in industrial design. *British Journal of Psychology*, 94(1), 111-124. Summary: https://www.jimdavies.org/summaries/HekkertSneldersVanwieringen2003.html | location confirmed; content via secondary source |
| S5 | Reber, R., Schwarz, N., & Winkielman, P. (2004). Processing fluency and aesthetic pleasure: Is beauty in the perceiver's processing experience? *Personality and Social Psychology Review*, 8(4), 364-382. https://pages.ucsd.edu/~pwinkielman/reber-schwarz-winkielman-beauty-PSPR-2004.pdf | location confirmed |
| S6 | Doshi, A. R., & Hauser, O. P. (2024). Generative AI enhances individual creativity but reduces the collective diversity of novel content. *Science Advances*, 10(28), eadn5290. https://pmc.ncbi.nlm.nih.gov/articles/PMC11244532 | opened |
| S7 | Zhang, J., et al. (2025). Verbalized sampling: How to mitigate mode collapse and unlock LLM diversity. arXiv:2510.01171. https://arxiv.org/abs/2510.01171 | opened (abstract and introduction) |
| S8 | Graham, P. (2002). Taste for makers. https://paulgraham.com/taste.html | opened |
| S9 | Hume, D. (1757). Of the standard of taste. In *Four Dissertations*. Overview: https://en.wikipedia.org/wiki/Aesthetic_taste | via secondary source |
| S10 | Alexander, C. (1964). *Notes on the Synthesis of Form*. Harvard University Press. | via secondary source |
| S11 | Kahneman, D., & Klein, G. (2009). Conditions for intuitive expertise: A failure to disagree. *American Psychologist*, 64(6), 515-526. https://doi.org/10.1037/a0016755 | location confirmed; abstract via search result |
| S12 | Leder, H., Belke, B., Oeberst, A., & Augustin, D. (2004). A model of aesthetic appreciation and aesthetic judgments. *British Journal of Psychology*, 95, 489-508. Overview of the model and later expert studies: https://aesthetics.univie.ac.at/research/models-of-aesthetic-appreciation | location confirmed; expert findings via secondary source |
| S13 | Bourdieu, P. (1979). *La Distinction: Critique sociale du jugement*. Éditions de Minuit. English: *Distinction* (1984). Overview: https://en.wikipedia.org/wiki/Distinction_(book) | via secondary source |
