---
name: plain-writing
description: Write and edit clear business and informative texts in Dutch or English, such as reports, summaries, memos, minutes, status updates, advice notes, internal emails and explanations for non-experts. Use when the user wants a text that other people will read, or asks to rewrite, shorten or simplify one. Examples are "write a report on", "make this clearer", "rewrite this for management", "schrijf een verslag", "maak dit leesbaarder", "herschrijf dit in begrijpelijke taal" and "vat dit samen voor het team". Not for marketing or sales copy, fiction, social media posts, code comments, commit messages, technical API documentation, literal translation, spelling-only checks or quick answers in chat.
---

# Plain writing

Write or edit the requested text. The user's explicit brief overrides these style rules. Name a conflict once, then follow the brief.

## Before you write

If the audience, purpose or desired length is missing and not clear from context, ask exactly one question and wait for the answer. Don't ask about several missing items at once.

Don't ask a question if nobody can answer, for example because you are running as a subagent or because the user asks you to just write. Assume instead: an interested reader without specialist knowledge, the purpose of informing, and a text as short as the content allows. State that assumption in one line after the text.

Decide which language the text must be in. This is not always the language of the conversation. Then read the language file: [references/dutch.md](references/dutch.md) for Dutch or [references/english.md](references/english.md) for English. It holds the word lists and the rules that apply only to that language. If you write in another language, apply the general rules and choose comparable words yourself.

Decide before you write:

- the main message in one sentence;
- one concrete reader and what they already know;
- the point of view: first, second or third person;
- the tense and function of the text, for example advising, explaining or arguing.

Stick to those choices. If better information changes the plan, revise the plan and the whole text. Don't tack the new information on at the end. Start writing once the main message is clear and well supported. Don't plan further than you need.

## Sentences

Make the person, group or thing that acts the subject, and make the action the main verb. Avoid nominalisations and weak constructions such as "conduct an assessment" when "assess" will do.

Use the passive voice only when the actor is unknown, obvious or irrelevant. Never use it to hide responsibility.

Build sentences like this:

- start with known information and end with new information;
- put the most important or heaviest part at the end;
- get to the main verb quickly;
- keep the subject and its verb close together;
- mix short and longer sentences, averaging about 15 to 20 words;
- replace a negative phrasing with a direct, positive one if the meaning stays the same;
- split or shorten sentences over 30 words, unless the length is clearly needed.

## Concision

Cut, without losing meaning:

- empty intensifiers;
- redundant pairs;
- wordy phrases that one word can replace;
- slow openings;
- commentary about the text itself, unless the reader needs a guide.

The language file gives examples for each category.

When editing, aim to cut about a third. Keep what meaning, nuance and evidence need.

## Paragraphs and headings

Cover one topic per paragraph and put the core in the first sentence. Together, the first sentences of all paragraphs should show the line of reasoning. Order paragraphs logically and connect them with plain transition words, not formal ones. The language file lists both.

Vary paragraph length. A one-sentence paragraph is fine for emphasis. Use concrete headings that tell the reader where information is, such as "What it costs".

## Voice and word choice

By default, write at CEFR level B2: a reader who knows the language well, but not the subject, follows the text on first reading. Use short, common words and phrases, even for difficult topics.

Write for one reader, not for a nameless group. When you address the reader, use the form of address from the language file.

Take a clear position when one choice is demonstrably better. Name relevant trade-offs once, then give usable advice. Say honestly when something is uncertain.

Use jargon only if the reader knows it. Otherwise explain necessary jargon briefly, once. Choose specific facts over vague qualifiers, for example "three weeks late" instead of "significantly delayed".

Cut corporate speak, empty promises, clichés, metaphors and personification of documents. Avoid the vague words from the language file when they carry no concrete meaning. Never use the banned words from the language file.

Don't use dashes (— or –) between clauses. Choose a comma, full stop or parentheses. Don't make lists of exactly three items out of habit. Don't use random bold to suggest emphasis.

## Final check

Before delivering, check:

1. The reader sees the topic and main message in the first two sentences.
2. Every paragraph serves the main message and opens with its core.
3. Point of view, tense and function stay the same.
4. Where possible, the actor is the subject and the action is the verb.
5. Sentences start with known information and end with new information.
6. No sentence is longer than 30 words without reason.
7. Nominalisations, the passive voice and long lead-ins appear only where needed.
8. Every sentence sounds natural when you say it aloud to a colleague.
9. The text takes a position where needed.
10. The text addresses the reader directly, unless the chosen point of view rules that out.
11. No sentence is so generic that any company could use it about any topic.
12. The text contains no banned words from the language file, no dashes between clauses and no accidental sets of three.
13. The language-specific rules from the language file are applied.
14. Names, numbers, dates and links are correct.
15. Supported claims have a source link, and all sources also appear in a source list at the end.
16. In a document with chapters, every chapter ends with pointers to more information.

## Delivery

Deliver the finished text right away, without an introduction such as "Here is a draft" and without a closing summary of what you just wrote. If the user needs to know about a relevant editorial choice, mention it in one line after the text.

Place source links directly next to claims that need support, and end with a source list. Never invent sources. If no sources are needed or available, don't add an empty source list.

## Documents with chapters

Apply these rules only to documents with chapters, such as reports, guides and chapters of a book. Emails, memos and updates stay plain text in the conversation.

- End every chapter with pointers to more information, so the reader can go deeper. Point to real sources, documents or people, and say in one line what each one offers. Never invent a pointer.
- Save the result as a Markdown file. End your reply by asking whether you should also generate an EPUB.

If the brief or another skill sets the delivery format, follow that instead.
