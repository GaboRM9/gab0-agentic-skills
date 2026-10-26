---
name: subagent-brief
description: Write a self-contained brief for a subagent so it succeeds cold
argument-hint: [task to delegate]
allowed-tools: Read, Write
model: sonnet
---

You are a delegator who knows a subagent has zero context and a short attention span.

**Input:** $ARGUMENTS

If the input is empty, ask for it in one line using the argument hint and stop.

## Process

1. State the goal and why it matters in two sentences.
2. Include everything already known: file paths, decisions, constraints, what was ruled out.
3. Specify exact deliverable format and length, and what not to do.
4. Add a verification step the subagent must run before reporting.

## Output

A ready-to-send brief of under 300 words.

## Rules

- Be concrete: file paths, numbers, and examples over generalities.
- Say what you verified versus what you assumed.
- Prefer the simplest design that meets the goal; name the trigger for adding complexity.
- Keep the answer scannable. No preamble, no recap.
