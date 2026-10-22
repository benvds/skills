# Skills

Agent skills I use every day, for the Claude and ChatGPT apps, Claude Code and other agents that read `SKILL.md` files. Copy what you like and change the rest.

| Skill | What it does |
|---|---|
| [active-learning](skills/active-learning/README.md) | A learning coach built on learning research. You try first or learn from worked examples, prove what you learned with a teach-back, keep it with flashcards in your own words, and plan with your measured pace. Every choice is backed by sources. |
| [plain-writing](skills/plain-writing/README.md) | Writes and edits clear reports, summaries, memos and other informative texts in Dutch or English. |

Each skill has its own README with what it does, examples and the choices you may want to change.

## Install in the Claude or ChatGPT app

You don't need git or a terminal for this. Download the ZIP file of the skill you want:

- [active-learning.zip](https://github.com/benvds/skills/releases/latest/download/active-learning.zip)
- [plain-writing.zip](https://github.com/benvds/skills/releases/latest/download/plain-writing.zip)

Don't unpack the file. Upload it as it is.

### Claude

Works on every plan, including Free, in the browser and in the desktop app.

1. Go to **Settings → Capabilities** and turn on **Code execution and file creation**. Skills don't work without it.
2. Go to **Customize → Skills**.
3. Click **+**, then **Create skill**, then **Upload a skill**, and choose the ZIP file.

The skill is now linked to your account, so it works everywhere you log in. On a Team or Enterprise plan, an admin may need to allow skills first.

### ChatGPT

Uploading skills works on Business, Enterprise, Edu and Healthcare plans. An admin can turn it off for your workspace.

1. Open the sidebar and go to **Plugins**.
2. Open the **Skills** tab and choose **Create**, then **Upload from your computer**.
3. Choose the ZIP file. ChatGPT checks it before you can use it.

On Plus or Pro you can't upload skills. As a workaround, create a Project, paste the text of `SKILL.md` into its instructions and add the files from `references/` as project files.

### Updates

The apps don't update a skill by themselves. When a skill changes, download the ZIP again, remove the old skill in the app and upload the new one. See [CHANGELOG.md](CHANGELOG.md) for what changed.

## Install for Claude Code and other agents

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

See [CHANGELOG.md](CHANGELOG.md). Every commit to `main` reaches you on your next sync. Every change to a skill also gets a new [release](https://github.com/benvds/skills/releases) with fresh ZIP files.

## License

[MIT](LICENSE)
