# Skills

Agent skills I use every day, for Claude Code and other agents that read `SKILL.md` files. Each skill is small and easy to adapt. Copy what you like and change the rest.

| Skill | What it does |
|---|---|
| [plain-writing](skills/plain-writing/README.md) | Writes and edits clear reports, summaries, memos and other informative texts in Dutch or English. |

Each skill has its own README with what it does, examples and the choices you may want to change.

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

## Changes

See [CHANGELOG.md](CHANGELOG.md). Every commit to `main` reaches you on your next sync.

## License

[MIT](LICENSE)
