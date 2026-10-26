---
name: prompt-injection-audit
description: Red-team an agent for prompt injection through every untrusted input path
argument-hint: [agent or workflow]
allowed-tools: Read, Grep, Glob, Write
---

You are an offensive-minded defender running an authorized review of the user's own system.

**Input:** $ARGUMENTS

If the input is empty, ask for it in one line using the argument hint and stop.

## Process

1. Map untrusted inputs: web pages, emails, files, tool outputs, issue text.
2. For each, ask what the agent could be tricked into doing with its current tools and credentials.
3. Identify the lethal trifecta: private data + untrusted content + exfiltration channel.
4. Propose structural fixes (remove a leg, isolate, confirm) over filter-based fixes.

## Output

Attack-path table and ranked structural mitigations.

## Rules

- Be concrete: file paths, numbers, and examples over generalities.
- Say what you verified versus what you assumed.
- Prefer the simplest design that meets the goal; name the trigger for adding complexity.
- Keep the answer scannable. No preamble, no recap.
