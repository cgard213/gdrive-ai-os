---
name: save-to-os
description: Save a note, fact, or decision into the AI OS folder in Google Drive. Trigger when the user says "save this to my OS", "log this", "log this decision", "add this to my OS", "remember this in the OS", or asks to record something durable. Creates a new dated markdown file in the right subfolder via the Google Drive connector. Never edits existing files.
---

# Save to OS

Write durable knowledge into the AI OS folder in Google Drive. The Google Drive connector can create files but not edit them, so every save is a new file. Never try to modify an existing note.

## When to use

The user says any of: "save this to my OS", "log this", "log this decision", "add this to my OS", "remember this in the OS", or clearly wants something recorded rather than answered in chat.

## Steps

1. **Decide the subfolder** inside the `AI OS/` folder:
   - `decisions/` — a real call that was made (price, vendor, policy, a lesson). Default here when the user says "log this decision."
   - `context/` — a lasting fact about the business, a person, a process.
   - `references/` — a framework, a checklist, or a reusable note.
   If it is unclear, ask one short question: "Log this as a decision or as context?"

2. **Write the note.** Keep it tight and use this shape:
   - For a decision: **What we decided** (1 to 2 lines), **Why**, **What it affects**.
   - For context: a clear heading and the fact in plain language.

3. **Name the file** `YYYY-MM-DD-short-slug.md`. Use today's date. Make the slug short and specific.

4. **Create the file** in the correct subfolder of the `AI OS` folder in Google Drive using the Drive connector. Do not overwrite anything. If a file with that exact name exists, add a short suffix like `-2`.

5. **Confirm back** in one line: what you saved, the filename, and the folder. Example: "Saved to decisions/2026-06-12-switch-email-provider.md."

## Rules

- One note per file. Never bundle two decisions into one.
- Never edit or delete an existing note. If something changed, write a new note that references the old date.
- If the Drive connector cannot create the file (file creation not enabled, or no access), say so plainly and show the user the note text so they can paste it in themselves. Do not pretend it saved.
