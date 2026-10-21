# Cards for the spaced repetition app

You make cards only after a part is learned. The user imports them into a spaced repetition app, which plans the reviews. The status file says which app (see **Card format**).

## How many cards: the content decides

There is no fixed number. The number follows from two steps.

**1. List the pieces of knowledge.** Go through the part and note every separate piece of knowledge the user has built. Use these kinds as a checklist, not as a quota:
- what it does
- why it works
- the conditions: when it applies
- when not: the limit or the wrong use
- the difference from something related
- a pitfall the user fell into
- the lesson from the "what if" question

A small part may have two pieces of knowledge, a large part ten.

**2. Filter.** A piece of knowledge gets a card only if it meets both requirements:
- an end task or a later part needs it;
- the user must still have it ready in a month, and cannot easily look it up when it is needed.

What drops out only costs review time. If in doubt, ask the user.

**A signal, not a limit.** If one part produces more than about ten cards, check whether the part is really two parts, or whether cards still hold more than one idea. Say so, and let the user choose.

## What goes on a card

- **One idea per card.** No lists, no "name the five ...". Split such a card. This way the number follows from the content.
- **No yes/no questions.** They test guessing, not knowledge.
- **Short answer.** One to three sentences. If that does not work, the question is too broad.
- **Only `basic` cards.** No `cloze`.
- **The user's language.** Questions and answers are in the language of the track.

## Answers come from the user

In research, self-made cards lead to better learning than ready-made cards. In the teach-back, the user has already rephrased the material; reusing that wording keeps the user's own thinking on the card. But the wording must be correct before it is reviewed for years.

1. You write the **questions**.
2. You take each **answer** from the user's teach-back or attempt, as literally as possible. You may shorten it and fix grammar, but not replace the content. If the teach-back is from an earlier conversation, use the core wording from the log.
3. If the user did not explain something: put a placeholder such as `[fill in yourself]` as the answer. Don't write it in yourself.
4. Show the set in the chat:

```
Cards for 03 · p-value

1. Q: Why does p = 0.03 not mean that the null hypothesis has a 3% chance of being true?
   A: [the user's wording]
2. Q: ...
   A: [fill in yourself]
```

5. Ask the user to edit the answers and fill in the placeholders, in one message.
6. **Check each answer on content,** including the answers that come literally from the teach-back. A small gap could stay in the teach-back, but not on a card. Check for:
   - **correctness:** is what it says right?
   - **conditions:** is an "only if" or "except when" missing that makes the answer too broad?
   - **misleading wording:** could someone who reads the answer in six months take something wrong from it?
7. **If there is an error:** explain what is wrong and why. Let the user rephrase the answer. Don't write it for the user. Check the new wording again.
8. Make the files only when all answers are right.

If a placeholder or an uncorrected error remains at the end, and the user wants to go on anyway, leave that card out and say which one.

## Card format

The skill delivers cards in two formats. The user chooses at the intake (see `curriculum.md`), and the choice is in the status file under `Cards`.

| Spaced repetition app | Format |
| --- | --- |
| Active Retrieval | **Active Retrieval:** one Markdown file per card, together in a zip |
| Anki | **Anki:** one text file per part, with one card per line |
| Another app, or none yet | **Anki.** Many spaced repetition apps import Anki text files or tab-separated text. Tell the user to check in their app how to import a text file |

If an existing status file has no format, ask once and add it.

The card ID is the same in both formats: `[curriculum-slug]-[part, two digits]-[card, two digits]`, for example `statistics-03-02`. The ID is fixed: an improved card keeps the same ID and replaces the old one.

## Format: Active Retrieval

One `.md` file per card. Exactly this format:

```markdown
---
card_id: "statistics-03-02"
card_schema: 1
card_type: basic
card_status: active
decks: ["Statistics"]
deck_emojis: {"Statistics":"📊"}
created_at: "2026-10-17"
---

# Vraag

Why does p = 0.03 not mean that the null hypothesis has a 3% chance of being true?

# Antwoord

The p-value says how strange my data are if H0 is true, not how likely H0 is.
```

**Rules for Active Retrieval:**
- Exactly one non-empty `# Vraag` followed by one non-empty `# Antwoord`. The app only recognises these Dutch headings, also when the cards are in another language.
- No other lines starting with `# `, not even in the answer. If you want structure in an answer, use plain sentences or a short list.
- `card_id` in quotes.
- `decks`: inline JSON list with the deck name from the status file.
- `deck_emojis`: inline JSON object, with the deck emoji from the status file.
- `created_at`: today's date as `"YYYY-MM-DD"`.
- Leave out `generation`, `source_path`, `source_vault`, `source_hash` and `source_excerpt`.
- File name: `[card_id].md`.

## Format: Anki

One UTF-8 text file per part, with these header lines at the top and then one card per line. The columns are separated by a tab: card ID, question, answer, deck, tags.

```text
#separator:tab
#html:true
#notetype:Basic
#guid column:1
#deck column:4
#tags column:5
statistics-03-01	What does a p-value tell you?	How strange my data are if H0 is true.	Statistics	active-learning statistics part-03
statistics-03-02	Why does p = 0.03 not mean that the null hypothesis has a 3% chance of being true?	The p-value says how strange my data are if H0 is true,<br>not how likely H0 is.	Statistics	active-learning statistics part-03
```

**Rules for Anki:**
- Exactly five columns per line, separated by one tab. Replace a tab in the text with a space.
- In the question and answer, replace `&` with `&amp;`, `<` with `&lt;` and `>` with `&gt;`. Do this before the next rule.
- A new line in an answer becomes `<br>`. There are no real line breaks inside a card.
- Anki does not render Markdown. Use plain sentences, and for a short list `<br>` between the items.
- Column 1 is the card ID. Anki uses it as the GUID, so an improved card updates the old one and keeps its review schedule.
- Column 4 is the deck name from the status file. Anki creates the deck if it does not exist yet.
- Column 5 holds the tags, separated by spaces: `active-learning`, the curriculum slug and `part-[number]`.
- `#notetype:Basic` works in an English Anki. If the default note type has another name, for example `Basis` in a Dutch Anki, the user chooses it when importing.
- File name: `[curriculum-slug]-[part]-anki.txt`.

## Delivering

**Active Retrieval**
1. Create the files with code execution, in a new folder.
2. Zip them: `[curriculum-slug]-[part]-cards.zip`, with the card files directly in the zip.
3. Deliver the zip as a downloadable file (see `platform.md`). Caption the first time: "Unzip this in the Active Retrieval card folder." After that, this is enough: "[n] cards for [part]."

**Anki**
1. Create the text file, preferably with code execution, so the tabs and replacements are right.
2. Deliver it as a downloadable file (see `platform.md`). Caption the first time: "Import in Anki via File > Import. For existing notes, choose update." After that, this is enough: "[n] cards for [part]."

**Then, for both formats**
1. Update the status file: part on `learned`, date, card IDs (for example `statistics-03-01 to 07`).
2. Log: "cards made, [n]".

**No code execution in this environment:** for Active Retrieval, give each card as a separate code block with the file name above it. For Anki, give the whole text file in one code block, and tell the user to check that the columns are still separated by tabs after copying. Tell the user to save the files themselves, or to have the cards made again later in an environment with code execution.

## Improving a card

If the user wants to change a card later: make only that card again, with the same card ID.
- **Active Retrieval:** deliver a zip with only the changed cards, with the same file names. Tell the user to overwrite the old files.
- **Anki:** deliver a text file with only the changed cards. When importing, Anki updates the existing cards via the card ID.
