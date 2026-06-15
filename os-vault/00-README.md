# AI OS

This folder is your AI Operating System. It lives in Google Drive so that Claude can read it from the browser, and so it is yours, portable, and not stuck on one machine.

It has three parts working together:

- **This folder (the file system).** What Claude knows about you and your work. You and Claude both add to it over time.
- **The Claude Project (the brain).** A workspace in Claude that reads this folder on every chat, so you never re-explain yourself.
- **The Skills (the hands).** Small tools you add to Claude once. They write new notes into this folder for you, the way a "save to my files" button would.

## What is in here

- `CLAUDE.md` — the brief your Claude reads to operate: who you are, how the OS is wired, the working rules.
- `me.md` — who you are and how you want your Claude to work with you. Your Claude reads this first, every time.
- `context/` — facts about your work: who does what, how your core process runs, anything you explain often.
- `connections.md` — the tools Claude can reach and what each is for.
- `decisions/` — a running record. Every real call gets saved here as its own dated note. Over time this becomes your memory.
- `references/` — the thinking frameworks the OS is built on.

## How saving works

The Google Drive connector can create new files but cannot edit old ones. So the OS never overwrites. Each save is a fresh dated note. That keeps a clean history and matches how the decision record is meant to work: you never lose what was true before.

When you say "save this to my OS" or "log this decision," the save-to-os Skill writes a new note into the right folder and tells you exactly what it saved and where.

## Keeping it current

Once a week, ask Claude to run an audit: what is missing from context, what decisions went unrecorded, what is leaking. It reads this folder and your connected tools and tells you. That weekly pass is what keeps the OS alive instead of stale.

## Getting started

If this is a fresh setup, say **"set up my OS."** Claude will interview you, fill in your `me.md` and `context`, and map your connected tools.
