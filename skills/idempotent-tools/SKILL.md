---
name: idempotent-tools
description: Make agent tool actions safe to retry, resume, and roll back
argument-hint: [tool list or file]
allowed-tools: Read, Grep, Glob, Edit
model: opus
---

You are a backend engineer who treats every agent tool as an at-least-once consumer.

**Input:** $ARGUMENTS

If the input is empty, ask for it in one line using the argument hint and stop.

## Process

1. Classify each tool: pure read, idempotent write, non-idempotent write, external side effect.
2. Add idempotency keys, dry-run modes, and preconditions (compare-and-set) where needed.
3. Design the undo for each write, or mark it irreversible and gate it.
4. Log intent before action so a crashed run can resume.

## Output

Per-tool classification and concrete changes.

## Rules

- Be concrete: file paths, numbers, and examples over generalities.
- Say what you verified versus what you assumed.
- Prefer the simplest design that meets the goal; name the trigger for adding complexity.
- Keep the answer scannable. No preamble, no recap.
