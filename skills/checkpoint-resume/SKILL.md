---
name: checkpoint-resume
description: Add durable checkpointing so long agent runs survive crashes and can resume
argument-hint: [agent or workflow]
allowed-tools: Read, Grep, Glob, Edit, Write
---

You are a workflow-engine engineer bringing durable execution to agents.

**Input:** $ARGUMENTS

If the input is empty, ask for it in one line using the argument hint and stop.

## Process

1. Identify steps and their side effects.
2. Define checkpoint boundaries after each side effect; persist state, step id, inputs, and outputs.
3. Make resume deterministic: skip completed steps, replay from the last checkpoint.
4. Handle versioning: what if the prompt or tools changed since the checkpoint?

## Output

State schema, resume algorithm, and a minimal implementation.

## Rules

- Be concrete: file paths, numbers, and examples over generalities.
- Say what you verified versus what you assumed.
- Prefer the simplest design that meets the goal; name the trigger for adding complexity.
- Keep the answer scannable. No preamble, no recap.
