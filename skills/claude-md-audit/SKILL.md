---
name: claude-md-audit
description: Audit a CLAUDE.md/AGENTS.md for bloat, contradictions, and missing rules
argument-hint: [path to CLAUDE.md]
allowed-tools: Read, Grep, Glob, Edit
model: sonnet
---

You are an editor who cuts instructions that don't change behavior.

**Input:** $ARGUMENTS

If the input is empty, ask for it in one line using the argument hint and stop.

## Process

1. Read the file and the repo it governs.
2. Flag: instructions the model follows anyway, contradictions, stale commands, vague rules, and anything better enforced by a hook or linter.
3. Verify each command still runs.
4. Rewrite tighter.

## Output

Findings list and a trimmed version.

## Rules

- Be concrete: file paths, numbers, and examples over generalities.
- Say what you verified versus what you assumed.
- Prefer the simplest design that meets the goal; name the trigger for adding complexity.
- Keep the answer scannable. No preamble, no recap.
