# GDrive AI OS

A browser-and-Google-Drive adaptation of [AIS-OS](https://github.com/nateherkai/AIS-OS) by Nate Herk.

## Why this fork exists

The original AIS-OS is excellent, and it runs in Claude Code: a local repo, a terminal, slash-command skills, files on your machine. That rules out most people, who use Claude in the browser and have never opened a command line.

This fork is for them. It rebuilds the same idea, a personal AI operating system that knows your world and runs things, **entirely inside Claude.ai**, with the file system living in **Google Drive**. No Claude Code. No terminal. No local files. If you can use Claude in a browser tab and you have a Google account, you can run this.

## What is different from upstream

- **Runs in the browser, not Claude Code.** No repo to clone, no command line.
- **The file system lives in Google Drive.** Claude reaches it through the Google Drive connector.
- **Skills replace the slash commands.** `/onboard`, `/audit`, and `/level-up` become uploaded Skills (`setup-os`, `os-audit`, `os-level-up`) you add at Customize, Skills.
- **Saving is create-only.** The Drive connector can create files but not edit them, so the OS never overwrites. Every save is a new dated note, and the decision log is a folder of dated notes rather than one appended file.

## What is in this repo

- `os-vault/` — the starter files that go into a Google Drive folder named **AI OS**. This is the file system: `CLAUDE.md`, `me.md`, `connections.md`, `context/`, `decisions/`, `references/`.
- `skills/` — the Skills you upload to Claude (one folder each, plus `INDEX.md`).
- `project-instructions.md` — the short block you paste into your Claude Project.

## How to set it up, in detail

Follow these in order. Nothing here needs code or a terminal.

### Prerequisites

- A Claude account with Connectors and Skills (a paid plan).
- A Google account (Drive, Gmail, Calendar). Plus any other tools you want connected (your CRM, project boards, design tool).

### Step 1 — Connect your sources

In claude.ai, open **Settings, then Connectors**. For each tool, find it by name, click **Connect**, and approve the sign-in: **Google Drive, Gmail, Google Calendar**, and whatever else you run on (many tools have one-click connectors; common ones include monday.com, ClickUp, Notion, Canva). After each, test it in a chat, for example "List five files from my Google Drive."

If a tool has no built-in connector (many CRMs do not), bridge it with **Zapier**: at **mcp.zapier.com**, create an MCP server, choose Claude as the client, switch on the actions you want, copy the server URL, then add it in Claude under **Settings, Connectors, Add custom connector**.

### Step 2 — Turn on file creation

In Claude **Settings**, enable file creation (the capability that lets Claude create and save files, sometimes shown alongside code execution). This is required: without it, the `setup-os` and `save-to-os` skills cannot write to your Drive.

### Step 3 — Create the Drive folder

In Google Drive, click **New, Folder**, and name it **AI OS**. Open it and upload everything from this repo's `os-vault/`, keeping the structure:

```
AI OS/
  00-README.md
  CLAUDE.md
  me.md
  connections.md
  context/
    business.md
  decisions/
    0000-how-the-log-works.md
  references/
    frameworks.md
```

### Step 4 — Create the Claude Project

In claude.ai, open **Projects, New project**, and name it **AI OS**. Open the project's settings and paste the contents of `project-instructions.md` into the **custom instructions** field. Then add the Google Drive **AI OS** folder to the project so Claude reads it. Test: ask "What is in my OS folder?" and it should list the files.

### Step 5 — Upload the skills

For each folder inside this repo's `skills/` (`setup-os`, `save-to-os`, `question-mode`, `skill-creator`, `os-audit`, `os-level-up`): **zip the folder** so the zip contains its `SKILL.md`, then in Claude go to **Customize, Skills, Create skill** and upload the zip. Six uploads, one per skill. (`INDEX.md` is a reference, not a skill; do not upload it.)

### Step 6 — Onboard

In the project, say **"set up my OS."** The `setup-os` skill interviews you one question at a time, then writes your `me.md` and `context` from your answers and pulls a first map of what your connected tools hold. It shows you each file before saving.

### Step 7 — Keep it alive

- As real decisions happen: **"log this decision."**
- Once a week: **"run my audit"** (what is thin or leaking) and **"level up"** (turn one manual task into a skill).

## Credit and license

Forked from [nateherkai/AIS-OS](https://github.com/nateherkai/AIS-OS), MIT licensed, © Nate Herk. The Four Cs and Three Ms frameworks are his; they are used here with attribution under the original MIT terms. "The Three Ms of AI" is his trademark. The LICENSE file is preserved unchanged. This fork only adapts the kit to run in browser Claude with Google Drive.
