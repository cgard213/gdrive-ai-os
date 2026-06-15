---
name: os-audit
description: Run a weekly health check on the OS using the Four Cs. Trigger on "run my audit", "os audit", "weekly audit", "check my OS", or when the user wants to know what is missing or leaking in their setup.
---

# OS audit

Once a week, check the OS is complete and current using the Four Cs from `references/frameworks.md`. This is a conversation, not a document. Report what you find in chat. Do not write to the OS unless the user asks.

## How to run

Walk the Four Cs in order, checking each against the OS folder and the connected tools:

1. **Context.** Read `context/`. Is anything thin, blank, or out of date? Are there blanks in `business.md` still unfilled? Has the work changed since it was written?
2. **Connections.** Read `connections.md`. Is every tool the user actually relies on connected? Any blind spot, a tool they mention but you cannot reach?
3. **Capabilities.** Read `skills/INDEX.md`. What does the user keep asking for by hand that should be a skill?
4. **Cadence.** Read `decisions/`. Are real calls getting logged, or has the record gone quiet? When was the last entry?

## Output

A short report, one block per C:
- What is solid.
- What is leaking, the specific gap.
- The single highest-priority fix, with an offer to do it now: fill a context blank, add a connection note, build a skill with skill-creator, or log a decision that went unrecorded.

## Rules

- Be specific. "Context is thin" is useless. "business.md still has blank core-process steps" is useful.
- One report. Do not nag across several messages.
- Findings stay in chat unless the user says to log them.
