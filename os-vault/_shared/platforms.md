# Platforms

This OS is provider-agnostic. The file system in Google Drive is the single source of truth. Claude, Gemini, and ChatGPT are three different front doors into the same folder. This file is how the OS adapts to whichever one you use. The `onboard` skill reads it during setup and scaffolds the right shape.

## The shared model

Every path (`business/`, `personal/`, `work/`) keeps two things:

- **A living rollup (`overview.md`).** The canonical current state: who, what, the processes, the standing facts. Always kept current. This is the file a Gemini Gem references, so it has to stay small and whole.
- **An append-only `decisions/`.** Dated notes for history: decisions made, things that changed, items pulled from the inbox. Never edited, never overwritten. The weekly audit folds what matters from these notes back into the rollup.

That split is what lets the same folder work on all three platforms. The rollup is the small, current view. The decisions folder is the long, never-lost history.

## Per platform

### Claude (Projects, Skills, Drive connector)

- **Connect.** claude.ai: Settings then Connectors, or the + menu in the message composer. Desktop: Customize, Connectors, +. On Team or Enterprise an org owner enables the connector first.
- **Reads** files on demand and supports @-mentions of Drive files.
- **Writes** are create-only. The connector can make new files but cannot edit existing ones. So saves are new dated files in `decisions/`. The rollup is updated by you (it is your Drive, edit it in Google Docs) or by the audit handing you a fresh version to paste.
- **Capabilities.** Skills. Upload the skill folders in `skills/` as zips at Customize, Skills, Create skill.
- **Indexing.** Many small dated notes are fine. Add the OS folder to the Project.

### ChatGPT (Projects, Custom GPTs, connectors)

- **Connect.** Settings then Connectors, add Google Drive, then link the OS folder to a Project for live context. Full sync needs Team or Enterprise (Plus is limited, Free has no connectors).
- **Reads** the current version of linked files. Many files are fine.
- **Writes.** No direct write to Drive in most setups. Capture is manual: paste into the inbox, or wire a Drive action. Treat ChatGPT as read-context plus manual capture.
- **Capabilities.** No native skills. Build a Custom GPT whose instructions point at the OS folder and the skills in `_shared/skills/`. Reuse them as saved prompts.
- **Indexing.** Link the whole OS folder to the Project. File count is not the constraint.

### Gemini (Gems, Workspace)

- **Connect.** Native, no connector step. An admin turns on Workspace apps in Gemini. Build a Gem that references the OS files, or use the Gemini app with Workspace access for broader Drive reach.
- **Reads** the most recent version of referenced files.
- **Writes.** Gemini in Drive can edit Docs directly, so the rollup can be kept current in place. Capture still lands in the inbox.
- **Capabilities.** No native skills. Gem instructions plus Workspace Studio flows plus saved prompts carry the skills in `_shared/skills/`.
- **Indexing, the real constraint.** A Gem references about 10 files. It cannot hold hundreds of dated notes. So a Gemini deployment points its Gem at the rollups only (one `overview.md` per active path, `me.md`, `_shared/`), not at `decisions/`. The decisions stay in Drive for history and for the app to search, but the Gem runs off the rollups.

## What onboarding changes by platform

- **Gemini chosen.** Lean hard on rollups. Keep the per-path `overview.md` tight and current. Point the Gem at the handful of rollup files. Keep `decisions/` for history but out of the Gem.
- **Claude chosen.** Dated-notes model. Saves go to `decisions/` as new files. Upload the skills. The audit regenerates the rollup for you to paste.
- **ChatGPT chosen.** Link the folder to a Project. Build a Custom GPT off the skills. Capture is manual into the inbox.
- **More than one chosen.** The Drive folder is shared. Keep rollups current for Gemini, keep `decisions/` for Claude history, link the folder for ChatGPT. One source, three doors.
