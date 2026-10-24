# Platform: Claude, ChatGPT and other environments

The skill follows the open SKILL.md standard and works in every assistant that reads skills. The coaching is the same everywhere. What differs is where you save, how research runs in the background, where the draft lives and how you ask questions. At the start of a conversation, decide based on the tools you have, not on the name of the product. If more than one column fits, choose the first one from the left.

## What to use per environment

| Needed for | Claude apps (memory with files) | ChatGPT (Project with files) | Working folder (Claude Code or another agent) | No storage |
| --- | --- | --- | --- | --- |
| Recognise | memory tools such as `memory_read` and `memory_write` | you run in ChatGPT, or in a Project where the user adds files | you can read and write files in a working folder | none of these |
| Status and sources | two memory files per project | two project files; a short pointer in saved memory | `.writing-coach/[slug]/` in the working folder | code blocks at the end of the session |
| The draft | a living document the user can edit, if a document tool is available (such as Claude Docs); otherwise a Markdown file delivered after each session | a project file the user replaces | `[slug].md` in the working folder, or the file the user names | the user's own file; they paste the part to work on |
| Background research | a background agent (`Agent` with `run_in_background`) if available; otherwise research between turns | research between turns | a background agent if available; otherwise between turns | none: say so |
| Multiple-choice question | a question tool such as `AskUserQuestion`; otherwise text | text with numbered options | a question tool if there is one; otherwise text | text |
| Deliver a file | the tool for sending files | downloadable file | file in the working folder | code block |
| EPUB | code execution with pandoc | code execution | local shell; otherwise give the command | give the command |

## Claude apps

Status and sources live in memory and are available on every device. The draft lives best in a document the user can open and edit themselves, so they write their paragraphs there and you see them next session. If no document tool is available, keep the draft as a Markdown file: deliver it after every session in which it changed, and ask the user to attach it next time.

## ChatGPT

ChatGPT cannot write files to its memory. So:

1. **One Project per writing project.** At the start, ask the user to create a Project and add the status file, the sources file and the draft as project files.
2. **Read** them at the start of a session.
3. **Update.** At the end of every session, deliver the changed files as downloads and ask the user to replace the old versions. Always deliver complete files.
4. **Saved memory.** If memory is on, save one pointer: "User has writing project [name] with the writing coach; status is in Project [name]."

Say once, at the start, that this is a manual step per session.

## Working folder

Write the two files to `.writing-coach/[slug]/` and the draft to `[slug].md`, unless the user names another place. Say once that the status is in that folder, and that it can go in `.gitignore`.

## No storage

At the end of every session, give the status and sources files as code blocks and ask the user to keep them, together with their draft. Next time, read them from the attachments or the message.

## Background research without agents

If you cannot run an agent in the background, do the research in one turn of your own. Before you start, give the user a task they can do in the meantime, such as writing the core sentences for the first two sections. Keep the research turn focused: the sub-questions that need it, and the brief from `research.md`.

## Moving between platforms

The files have the same format everywhere. If the user asks for an export, deliver the two files unchanged, plus the draft. On another platform, the user adds them and the project continues.
