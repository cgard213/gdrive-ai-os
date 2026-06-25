# AI OS (Google Drive)

Your own AI that actually knows you. It lives in a Google Drive folder and works with Claude, Gemini, or ChatGPT. You do not need to know how to code. Your AI sets up almost all of it for you.

Adapted from Nate Herk's AIS-OS (github.com/nateherkai/AIS-OS). Credit to him for the frameworks and the shape.

## Set it up

Open Claude, Gemini, or ChatGPT. Start a new chat. Copy the whole prompt below, paste it in, and do what it says. It goes one step at a time and handles everything it can for you.

```
You are setting up my AI Operating System with me. Treat me like I have
never done anything technical. Do everything you are able to do yourself.
For the few things only I can click, tell me exactly where to click, one
step at a time, and wait for me. Never give me more than one step at once.
Make every choice you reasonably can for me with a sensible default, and
only ask me when you truly cannot decide.

The system is in this public GitHub repo:
https://github.com/cgard213/gdrive-ai-os
Read it first, especially README.md, os-vault/instructions.md, and
os-vault/_shared/platforms.md, so you know how it works and how it should
be set up for the assistant I am using.

Then walk me through this, one step at a time, waiting for me each time:

1. Ask me which assistant I am talking to right now: Claude, Gemini, or
   ChatGPT. Follow that platform's path for everything after this.
2. Help me connect Google Drive to you. Give me the exact clicks for my
   platform. Have me confirm it works by asking you to list a few of my
   Drive files.
3. Tell me to create one new, empty folder in Google Drive named
   "My AI OS" and paste you the link to it.
4. Put the OS files into that folder: create the files from this repo's
   os-vault/ folder inside my folder, keeping the same structure. If you
   cannot write to my Drive on this platform, tell me to download the repo
   as a ZIP from GitHub (Code, then Download ZIP) and drop the os-vault
   contents in, then check it with me.
5. Help me create my workspace (a Claude Project, a Gemini Gem, or a
   ChatGPT Project or Custom GPT), paste in the text from this repo's
   project-instructions.md, and connect my folder. On Gemini, point it
   only at the small rollup files, not the whole folder; the repo explains
   why.
6. On Claude, help me add the skills from the repo's skills/ folder. On
   Gemini and ChatGPT, set them up the way the repo describes instead.
7. Once everything is connected, start onboarding me: ask me about myself
   one question at a time, and write my files, showing me each one before
   you save it.

Keep it friendly and plain. Expect me to get confused, and slow down if I do.
```

That is the whole setup. The assistant takes it from there.

## What you need

- A Google account (for Google Drive).
- Claude, Gemini, or ChatGPT on a plan that can connect to Google Drive. Free plans are usually too limited; a paid plan works.
- About fifteen minutes.

## What the assistant is doing for you

So nothing feels like a black box, here is the same flow in plain words. You do not run this yourself, the prompt above does.

1. Finds out which assistant you use.
2. Helps you connect Google Drive.
3. Has you make one empty Drive folder and share the link.
4. Fills that folder with the OS files from this repo.
5. Builds your project, Gem, or Custom GPT and connects your folder.
6. Adds the skills (Claude) or the equivalent (Gemini, ChatGPT).
7. Interviews you, one question at a time, and writes your files.

After that you just talk to it. Say "log this decision" when you decide something, drop quick notes in the inbox, and once a week say "run my audit" and "level up."

## What is inside

- `os-vault/` — the files that go into your Google Drive folder. This is the part your AI reads to know you.
- `skills/` — the small reusable tools (uploaded as Skills on Claude; folded into a Gem or Custom GPT elsewhere).
- `platform-setup/` — the deeper per-assistant guide: `claude.md`, `gemini.md`, `chatgpt.md`.
- `project-instructions.md` — the short block your AI pastes into your project, Gem, or Custom GPT.

## The folder, once it is built

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

You only keep the paths you want (business, personal, work). Your AI sets up the ones you use and skips the rest.

## For the curious

- How it adapts to each assistant: `os-vault/_shared/platforms.md`.
- The thinking it runs on (the Four Cs and Three Ms): `os-vault/_shared/frameworks.md`, from AIS-OS, used with attribution.
