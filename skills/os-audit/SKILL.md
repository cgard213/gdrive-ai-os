---
name: os-audit
description: Run a weekly health check on the OS using the Four Cs, triage the inbox, and flag what has gone stale. Trigger on "run my audit", "os audit", "weekly audit", "check my OS", or when the user wants to know what is missing or leaking in their setup.
---

# OS audit

Once a week, check the OS is complete and current using the Four Cs from `_shared/frameworks.md`. This is a conversation, not a document. Report what you find in chat. Do not write to the OS unless the user asks.

## How to run

Walk the Four Cs in order, checking each path the user runs and the shared files:

1. **Context.** Read each active path's `overview.md`. Is anything thin, blank, or out of date? Has the area changed since it was written? An overview that is months stale is the most common leak.
2. **Connections.** Read `_shared/connections.md`. Is every tool the user actually uses connected? Any blind spot, a tool they mention but the AI cannot reach?
3. **Capabilities.** Read `_shared/skills/INDEX.md`. What does the user keep asking for by hand that should be a skill?
4. **Cadence.** Read each path's `decisions/`. Are real calls getting logged, or has the record gone quiet? When was the last entry?

Then two passes the Four Cs do not cover on their own:

5. **Inbox triage.** Read `inbox/`. For each loose note, decide with the user: fold it into the right path's `overview.md` (hand them the lines to paste), save it as a decision, turn it into a skill, or drop it. The inbox should end close to empty.
6. **Decay.** Flag anything stale: an overview that no longer matches reality, a decision that has been superseded, a connection that is dead. Suggest a new dated note that supersedes the old one, or moving the old one to `_archive/`. Nothing gets deleted, it gets superseded.

## Output

A short report, one block per C, then inbox and decay:
- What is solid.
- What is leaking, the specific gap.
- The single highest-priority fix, with an offer to do it now.

## Rules

- Be specific. "Context is thin" is useless. "business/overview.md still has a blank listing-process section" is useful.
- One report. Do not nag across several messages.
- Findings stay in chat unless the user says to act on them.
