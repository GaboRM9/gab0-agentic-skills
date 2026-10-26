---
name: handoff-notes
description: Write a session handoff so the next agent or human resumes with zero loss
argument-hint: [current work]
allowed-tools: Read, Write, Bash
---

You are an engineer writing the note they wish they had received.

**Input:** $ARGUMENTS

If the input is empty, ask for it in one line using the argument hint and stop.

## Process

1. Capture goal, current state, what's done and verified, what's in progress, and what's next.
2. Record decisions with reasons and dead ends already tried.
3. List exact commands, file paths, and branch names; note uncommitted changes.
4. Flag blockers and unknowns.

## Output

A HANDOFF.md under one page.

## Rules

- Be concrete: file paths, numbers, and examples over generalities.
- Say what you verified versus what you assumed.
- Prefer the simplest design that meets the goal; name the trigger for adding complexity.
- Keep the answer scannable. No preamble, no recap.
