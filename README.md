# AI OS (Google Drive)

A provider-agnostic adaptation of Nate Herk's AIS-OS (github.com/nateherkai/AIS-OS). Credit to him for the frameworks and the shape.

The original AIS-OS runs in Claude Code on a local machine. This version is built for someone working entirely in the browser, with the file system living in Google Drive, and it runs through any of the three major assistants: Claude, Gemini, or ChatGPT. No command line, no install.

## What is different from upstream AIS-OS

- **Runs in the browser, not Claude Code.** No local repo, no terminal.
- **Provider-agnostic.** One Google Drive folder is the source of truth. Claude, Gemini, and ChatGPT are three front doors into it. Onboarding asks which one you use and indexes accordingly. See `os-vault/_shared/platforms.md`.
- **Split by path.** The OS holds `business/`, `personal/`, and `work/` as separate areas. You set up only the ones you use.
- **Rollup plus history.** Each path keeps one living `overview.md` (the current state, small enough for a Gemini Gem) and an append-only `decisions/` of dated notes (the history). The weekly audit folds those notes back into the rollup.
- **Skills as reusable procedures.** Each repeatable task is written once as a skill. On Claude you upload it as a Skill, on Gemini you fold it into a Gem, on ChatGPT into a Custom GPT. Same procedure, each platform's own word for it.

## What is in this repo

- `os-vault/` — the starter files that go into your Google Drive folder. This is the file system: `start-here.md`, `instructions.md`, `me.md`, the path folders, and `_shared/`.
- `skills/` — the Claude Skill packaging of each skill (one folder each).
- `platform-setup/` — the deeper setup guide for each assistant: `claude.md`, `gemini.md`, `chatgpt.md`.
- `project-instructions.md` — the short block you paste into your project, gem, or custom GPT.

## Setup

Follow these in order. Nothing here needs code or a terminal.

### Step 1 — Connect your sources

The connect step is different on each platform. Do the one for your assistant. The full per-platform walkthrough is in `platform-setup/`.

**Claude.** Open claude.ai. Go to Settings, then Connectors, or use the + menu in the message composer. (On desktop it is Customize, Connectors, +.) Connect Google Drive, and any of Gmail, Google Calendar, and your other tools, approving each sign-in window. On a Team or Enterprise plan an org owner has to enable a connector before you can. For a tool with no built-in connector (for example a CRM like Follow Up Boss), use mcp.zapier.com to create an MCP server, switch on the actions you want, copy the server URL, then in Claude add it under Settings, Connectors, Add custom connector.

**ChatGPT.** Open chatgpt.com. Go to Settings, then Connectors, and add Google Drive. Full sync needs a Team or Enterprise plan (Plus is limited, Free has no connectors). You will link the OS folder to a Project in Step 4.

**Gemini.** There is no connector to add. An admin turns on Workspace apps in Gemini (Drive, Gmail, Calendar) for your account. Gemini reaches Drive natively. You will reference the OS files from a Gem in Step 4.

After connecting, test it in a new chat, for example "List five files from my Google Drive."

### Step 2 — Turn on file creation (Claude only)

In Claude Settings, enable file creation (the capability that lets Claude create and save files). Without it the onboard and save skills cannot write to your Drive. On Gemini and ChatGPT this step does not apply, capture works differently (see `platforms.md`).

### Step 3 — Create the Drive folder

In Google Drive, click New, Folder, and name it for yourself (for example "My AI OS"). Open it and upload everything from this repo's `os-vault/`, keeping the structure:

```
My AI OS/
  start-here.md
  instructions.md
  me.md
  inbox/
  business/
    overview.md
    references/
    decisions/
  personal/
    overview.md
    references/
    decisions/
  work/
    overview.md
    references/
    decisions/
  _shared/
    connections.md
    platforms.md
    frameworks.md
    skills/
      INDEX.md
```

You can delete the path folders you do not plan to use. Onboarding will only fill in the ones you keep.

### Step 4 — Create the project, gem, or custom GPT

Open `project-instructions.md` and paste the block into your assistant's instructions field.

- **Claude:** Projects, New project, paste into custom instructions, then add the OS Drive folder to the project.
- **ChatGPT:** New Project (or a Custom GPT), paste into instructions, then link the OS Drive folder.
- **Gemini:** New Gem, paste into instructions, then reference the rollup files (`me.md`, `_shared/`, each `overview.md`). Do not point a Gem at the whole folder, it caps at about 10 files.

Test: ask "What is in my OS folder?" and it should describe it.

### Step 5 — Add the skills

- **Claude:** for each folder in this repo's `skills/`, zip the folder so the zip holds its `SKILL.md`, then in Claude go to Customize, Skills, Create skill and upload the zip. One upload per skill. (`INDEX.md` is a reference, not a skill, do not upload it.)
- **Gemini and ChatGPT:** there is no skill upload. The skills live in `_shared/skills/`. Paste the one you need into the chat, or fold the common ones into your Gem or Custom GPT instructions.

### Step 6 — Onboard

In your project, gem, or GPT, say **"onboard me."** The onboard skill asks which platform you run and which paths you want, interviews you one question at a time, writes your `me.md` and each path's `overview.md` from your answers, and pulls a first map of what your connected tools hold. It shows you each file before saving.

### Step 7 — Keep it alive

- As real calls happen: **"log this decision."**
- Whatever lands in your head: drop a one-line note in `inbox/`.
- Once a week: **"run my audit"** (what is thin or leaking, and triage the inbox) and **"level up"** (turn one manual task into a skill).

## Frameworks

The Four Cs (Context, Connections, Capabilities, Cadence) and the Three Ms (Mindset, Method, Machine) are from AIS-OS. See `os-vault/_shared/frameworks.md`. They are used as-is with attribution, not repackaged.
