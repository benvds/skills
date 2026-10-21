# Platform: Claude, ChatGPT and other environments

The skill follows the open SKILL.md standard and works in every assistant that reads skills. The learning approach is the same everywhere. What differs is how you save, deliver files and ask questions. At the start of a conversation, decide which storage you have based on the tools available, not on the name of the product. Then follow the matching column. If you have more than one kind of storage, choose the first column that fits, from left to right.

## What to use per kind of storage

| Needed for | Memory with files | Project with files (ChatGPT) | Working folder | No storage |
| --- | --- | --- | --- | --- |
| Recognise | you have tools to read and write memory files, such as `memory_read` and `memory_write` in the Claude apps | you run in ChatGPT, or in a Project where the user adds files | you can read and write files in a working folder, as in Claude Code or another coding agent | none of the three |
| Keep status | three memory files per track | status files in the track's Project; a short pointer in the saved memory | status files in `.active-learning/[slug]/` in the working folder | code block at the end of the session |
| Multiple-choice question | a question tool if there is one (such as `AskUserQuestion`); otherwise text | text, with numbered options | a question tool if there is one; otherwise text | text |
| Deliver a file | the tool for sending files to the user | downloadable file from the code environment | file in the working folder | code block |
| Search | web search tool | web search | web search tool if there is one | none: say so, and mark the research as unchecked |
| Make zip and EPUB | code execution | code execution (Python) | local shell; otherwise give the command | give the command |

## Memory with files

The status lives in three memory files per track (see `storage.md`). In the Claude apps, these are available on every device and in every conversation. Read them at the start of a session and update them at the end. The user doesn't need to do anything.

## Project with files (ChatGPT)

ChatGPT cannot write files to its memory. So storage here works with files that the user keeps:

1. **One Project per track.** At the start, say something like: "Create a Project for this track and add the three status files as project files. Always work in that Project from now on." A Project is available on every device.
2. **Read.** At the start of a session, read the status files from the project files or the attachments.
3. **Update.** At the end of every session, deliver the changed status files as downloads, and ask the user to replace the old versions in the Project. Deliver only what changed.
4. **Saved memory.** If memory is on, save one short pointer: "User follows learning track [name] with active learning; status is in Project [name]." More does not fit well in that memory.
5. **If the files are missing:** ask for them. Don't restart a track unless the user wants that.

Say once, at the start, that this is a manual step per session.

## Working folder

Write the three files to `.active-learning/[slug]/` in the working folder and read them at the start. Tracks from an earlier version of this skill may be in `.actief-leren/[slug]/`; read them there and keep writing there. At the start of a track, say once that the status is in that folder, and that the user can add the folder to `.gitignore` if it does not belong in version control.

The working folder is only available on this computer. If the user wants to continue on another device, they can export the status (see **Moving between platforms**).

## No storage

After every session, give the complete files as code blocks and ask the user to keep them. At the next session, read them from the attachments or the user's message.

## Moving between platforms

The files have the same format everywhere. If the user asks to export the status ("give me my status files"), deliver the three files unchanged. On another platform, the user adds them, and the track continues where it was. If you receive files from another platform, read them and write them to the storage of the current platform.
