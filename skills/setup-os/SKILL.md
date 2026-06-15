---
name: setup-os
description: First-run setup for the OS. Interviews the user, uses the answers to populate me.md and the context, and pulls a first map of the connected tools. Trigger on "set up my OS", "onboard", "run setup", "initialize my OS", or the first time the user opens the OS project and it is still mostly blank.
---

# Set up OS

The one-time onboarding for the AI OS. Run it once, after the folder, the Project, and the tools are connected. It does three things in order: interview, populate, map. Use question mode throughout, one question at a time.

## 1. Interview

Ask these one at a time. Reflect each answer back in a line before the next. Keep your own words short; the user should be doing the talking.

- Who are you, and what do you do? (name, role, the business or team)
- Who else is involved, and who does what?
- Walk me through your most important workflow, start to finish (a sale, a project, a client engagement).
- How does a new lead, client, or request get handled today, step by step?
- What do you keep doing by hand that you wish ran itself?
- How do you want me to work with you? Peer or assistant, ask or guess, how much should I do before checking in.
- Paste two or three real messages you have written, so I can learn your voice.
- What does a great week look like, and what do you care about most?

## 2. Populate

From the answers, draft and save with the save-to-os skill (new files, never overwriting). Show each one, get a yes, then save.

- `me.md`: who they are, how they want you to work, their voice, their anti-patterns.
- `context/business.md`: the basics, who does what, the core process, how requests are handled, what good looks like. Fill the starter blanks with their real answers.
- A first note in `decisions/` if anything they said is a standing call worth recording.

## 3. Map

Pull a first map of what you can actually see, so the OS starts grounded in reality and not just in answers. Read-only.

- Look across the connected tools: recent folders in Google Drive, the boards in any project tool, the stages and a rough record count in their CRM, the shape of the calendar.
- Draft an updated `connections.md` recording what each tool holds and what you found in it.
- Show the map. Flag anything missing: a tool they mentioned that is not connected, or a blind spot.

## Output

A short recap: what you saved and where, and the map of what you can see. Then point them at the weekly rhythm: "run my audit" and "level up."

## Rules

- One question at a time. Never dump the whole interview at once.
- Confirm each file before saving. The user owns their me.md and their context.
- Pull the map read-only. Do not change anything in the connected tools during setup.
- If a tool is not connected yet, note it and move on. Do not stall.
