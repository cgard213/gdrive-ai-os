# How the decision log works

This folder is your memory. Every real call gets its own dated note here. A price change, a vendor you picked, a policy, a lesson from something that went sideways. Small is fine. The point is that six months from now, you (and Claude) can see what was decided and why.

## The pattern

- One decision per file.
- Name it `YYYY-MM-DD-short-slug.md`, for example `2026-06-12-switch-email-provider.md`.
- Never edit an old one. If a decision changes, write a new note that says so and references the old date. The history stays intact.

## What goes in a note

- **What we decided.** One or two lines.
- **Why.** The reason, so future-you remembers the thinking.
- **What it affects.** Who or what changes because of this.

## How to add one

Tell Claude "log this decision" and the rest. The save-to-os Skill writes the note here for you and confirms the filename.
