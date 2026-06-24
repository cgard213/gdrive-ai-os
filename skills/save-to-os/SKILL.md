---
name: save-to-os
description: Save a note, fact, or decision into the AI OS folder in Google Drive. Trigger when the user says "save this to my OS", "log this", "log this decision", "add this to my OS", "remember this in the OS", or asks to record something durable. Picks the right path (business, personal, work), writes a new dated markdown file in that path's decisions folder, and never edits existing files.
---

# Save to OS

Write durable knowledge into the AI OS folder in Google Drive. On Claude the Drive connector can create files but not edit them, so every save is a new file. Never try to modify an existing note.

## When to use

The user says any of: "save this to my OS", "log this", "log this decision", "add this to my OS", "remember this in the OS", or clearly wants something recorded rather than answered in chat.

## Steps

1. **Pick the path.** Which area does this belong to: `business/`, `personal/`, or `work/`? If it is obvious from the topic, choose it. If not, ask one short question: "Save this under business, personal, or work?"

2. **Decide where in the path.**
   - `<path>/decisions/` — a real call that was made (a price, a vendor, a policy, a lesson), or a change worth keeping. Default here.
   - `<path>/references/` — a framework, a checklist, or a reusable note.
   If a fact changes the standing picture of the area, also say so, so the `overview.md` rollup can be updated (you cannot edit it on Claude, so hand the user the new lines to paste).

3. **Write the note.** Keep it tight:
   - For a decision: **What we decided** (1 to 2 lines), **Why**, **What it affects**.
   - For a reference: a clear heading and the note in plain language.

4. **Name the file** `YYYY-MM-DD-short-slug.md`. Use today's date. Make the slug short and specific, for example `2026-06-24-raise-photo-budget.md`.

5. **Create the file** in the right subfolder. Do not overwrite anything. If a file with that exact name exists, add a short suffix like `-2`.

6. **Confirm back** in one line: what you saved, the filename, and the path. Example: "Saved to business/decisions/2026-06-24-raise-photo-budget.md."

## Rules

- One note per file. Never bundle two decisions into one.
- Never edit or delete an existing note. If something changed, write a new note that references the old date.
- If the Drive connector cannot create the file (file creation not enabled, or no access), say so plainly and show the user the note text so they can paste it in. Do not pretend it saved.
