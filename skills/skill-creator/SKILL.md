---
name: skill-creator
description: Help the user build a new Skill for their OS and record it in the skills index. Trigger when the user says "create a skill", "make a new skill", "I want a skill that...", or describes a repeatable task they want to turn into a reusable tool.
---

# Skill creator

Turn a repeatable task into a Skill the user can add to Claude.

## Steps

1. **Get the trigger and the job.** Ask, one at a time (use question mode): what words should set this off, and what should happen, step by step.
2. **Write the SKILL.md.** Start with frontmatter:
   - `name`: short, kebab-case.
   - `description`: when to trigger it and what it does. This is what makes Claude pick the skill up, so be specific about the trigger words.
   Then the steps in plain order, and any rules.
3. **Keep it small.** One job per skill. If it is doing two things, split it.
4. **Tell them how to add it.** Put the SKILL.md in a folder named after the skill, zip that folder, then in Claude go to Customize, Skills, Create skill, and upload the zip.
5. **Record it in the index.** Draft the new row for `skills/INDEX.md`: skill name, what it does, trigger words. The Drive connector cannot edit files, so either the user pastes the row into INDEX.md by hand (it is their Drive), or you save a dated note in `skills/` with the new row and they fold it in.

## Rules

- Match the style of the existing skills (save-to-os, question-mode). Plain language, clear triggers.
- Do not invent capabilities the OS does not have. A skill can only use tools that are actually connected.
- One job per skill.
