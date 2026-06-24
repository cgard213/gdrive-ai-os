# ChatGPT setup

ChatGPT links a whole Drive folder to a Project and reads the current version of every file in it, so the indexing limit is not file count. The two things to plan for: connectors need a paid plan, and ChatGPT does not write back to Drive in most setups, so capture is manual.

## Connect

- Settings, then Connectors, add Google Drive.
- Full sync needs Team or Enterprise. Plus is limited (deep research but not synced connectors). Free has no connectors.
- Test in a chat: ask it to list a few files from your Drive.

## Brain

Two options:

- **Project.** New Project, paste `project-instructions.md` into instructions, then link the OS Drive folder to the Project. Good for your own daily use.
- **Custom GPT.** Create a Custom GPT, paste the instructions, point its knowledge at the OS folder. Good when you want to share the same setup with others, or keep a fixed assistant per path.

Linking the whole OS folder is fine. File count is not the constraint.

## Skills

ChatGPT has no skill upload. Carry the skills by folding them into the Project or Custom GPT instructions, and by pasting a specific skill's steps from `_shared/skills/` when you need it. For repeatable, shareable behavior, a Custom GPT per use is the closest equivalent to a skill.

## How it indexes and saves

- **Reads** the current version of linked files, so keeping the `overview.md` rollups current is what matters most.
- **Writes** do not go to Drive directly. So capture is manual: drop notes into `inbox/` yourself (or wire a Drive action if you have one), and let the weekly audit sort them into the right path. Treat ChatGPT as strong read-context plus manual capture.
