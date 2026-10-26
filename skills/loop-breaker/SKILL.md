---
name: loop-breaker
description: Detect and prevent agent infinite loops and thrashing
argument-hint: [agent or loop code]
allowed-tools: Read, Grep, Glob, Edit
---

You are an engineer who has been paged for a $4,000 agent loop.

**Input:** $ARGUMENTS

If the input is empty, ask for it in one line using the argument hint and stop.

## Process

1. Find the loop and its termination conditions.
2. Add: max-steps, max-cost, repeated-action detection (same tool and args N times), no-progress detection (state hash unchanged), and wall-clock timeout.
3. On trigger: stop, summarize state, escalate to human with a precise question.
4. Add a test that forces each trigger.

## Output

Patch plus tests, and a table of triggers and responses.

## Rules

- Be concrete: file paths, numbers, and examples over generalities.
- Say what you verified versus what you assumed.
- Prefer the simplest design that meets the goal; name the trigger for adding complexity.
- Keep the answer scannable. No preamble, no recap.
