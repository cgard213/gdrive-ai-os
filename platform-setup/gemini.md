# Gemini setup

Gemini reaches Google Drive natively, so there is no connector to install. The catch is the indexing limit: a Gem references about 10 files, so it cannot hold a folder of hundreds of dated notes. The OS is built for this. A Gem runs off the rollups, not the history.

## Connect

- An admin turns on Workspace apps in Gemini (Drive, Gmail, Calendar) for your account.
- Test in a chat: ask Gemini to list a few files from your Drive.

## Brain

Build a Gem (New Gem). Paste `project-instructions.md` into its instructions. Then add file references, but only the rollups, to stay under the cap:

- `me.md`
- `instructions.md`
- `_shared/connections.md`, `_shared/platforms.md`, `_shared/frameworks.md`
- one `overview.md` per active path

Do not reference the `decisions/` folders or the inbox from the Gem. They stay in Drive for history and for the Gemini app to search when you ask, but the Gem itself runs lean.

If you need the AI to see everything (not just the rollups), use the Gemini app with Workspace access rather than a Gem. The app can reach across Drive; the Gem is the focused, always-on version.

## Skills

Gemini has no skill upload. Carry the skills two ways:

- Fold the everyday ones (save-to-os behavior, question-mode) into the Gem's instructions.
- For a specific skill, open `_shared/skills/` and paste that skill's steps into the chat when you need it.

You can also turn a skill into a Workspace Studio flow if you want it to run on a trigger.

## How it indexes

Keep each `overview.md` tight and current, because the Gem leans on it. When something changes, edit the overview in place (Gemini can edit Docs) and add a dated note to that path's `decisions/` for the history.
