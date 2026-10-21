# Skills

Agent skills I use every day, for Claude Code and other agents that read `SKILL.md` files. Each skill is small and easy to adapt. Copy what you like and change the rest.

| Skill | What it does |
|---|---|
| [plain-writing](skills/plain-writing/SKILL.md) | Writes and edits clear reports, summaries, memos and other informative texts in Dutch or English. |

## Installation

I sync these skills with [skills-sync](https://github.com/benvds/skills-sync). Add this repo to your `.skills.toml`:

```toml
[skills]
repos = [
    "benvds/skills",                      # every skill in this repo
    # "benvds/skills/skills/plain-writing", # or just one
]
```

Then run:

```bash
skills-sync
```

Add `--global` to install into `~/.claude/skills/` instead of the current project. Run the same command again to update.

You can also copy a skill folder by hand into `~/.claude/skills/`. You then update it by hand too.

## plain-writing

Use it when you want a text that other people will read: a report, a summary for your team, a memo to your manager or an explanation for someone outside your field. It also edits existing texts that are too long, too formal or too vague.

It doesn't activate for marketing copy, fiction, social media posts, code comments or commit messages.

### What it does

- It asks one question if the audience, purpose or length is unclear. If nobody can answer, it states its assumption after the text.
- It makes the actor the subject and the action the verb, and puts new information at the end of the sentence.
- It cuts filler, wordy phrases and slow openings. When editing, it aims to cut about a third.
- It writes at CEFR level B2 by default, so a reader who knows the language but not the subject follows the text on first reading.
- It loads a separate word list for Dutch or English, so both languages get the same care.
- For documents with chapters, it ends each chapter with pointers for further reading, saves the result as Markdown and offers an EPUB.

### Before and after

> It is important to note that, due to the fact that the API was delivered late by the vendor on October 2, the migration has been significantly delayed by three weeks. Moreover, various factors, such as two engineers being out sick, have impacted the timeline.

> The migration is three weeks late. The vendor delivered the API late, on October 2, and two engineers were out sick.

### Opinions you may not share

This skill takes positions. Change them in [SKILL.md](skills/plain-writing/SKILL.md) or the language files in [references/](skills/plain-writing/references/) if they don't suit you.

- No dashes between clauses.
- A list of banned words, such as *delve*, *leverage* and *seamless*, and in Dutch *cruciaal* and *naadloos*.
- Informal *je* instead of *u* in Dutch, unless you ask for *u*.
- A source link for every supported claim, with a source list at the end.

## Credits

The sentence rules build on Joseph M. Williams, *Style: Lessons in Clarity and Grace*. The idea of publishing personal skills came from [mattpocock/skills](https://github.com/mattpocock/skills).

## Changes

See [CHANGELOG.md](CHANGELOG.md). Every commit to `main` reaches you on your next sync.

## License

[MIT](LICENSE)
