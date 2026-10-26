# gab0-agentic-skills

> My personal toolkit of agentic engineering skills: reusable prompts for designing, building, evaluating, and operating AI agents.

Each skill is a self-contained markdown prompt with a focused persona, a declared tool set, and a fixed output format. Invoke one as a slash command in any agent harness that loads markdown skills/commands.

---

## Quick Install

Copy the skills you want into your agent's skills/commands directory:

```bash
SKILLS_DIR=<your-skills-dir>
for d in skills/*/; do n=$(basename "$d"); cp "$d/SKILL.md" "$SKILLS_DIR/$n.md"; done
```

Then invoke by name:
```
/forecast "1 month" "OpenAI"
/agent-spec "support triage agent"
/failure-modes "./agents/refund-bot"
```

---

## Skills

- **[Agentic engineering (50 skills)](./skills/AGENTIC.md)**: design, context, reliability, evals, workflow, harness, ops, research.
- **[/forecast](./skills/forecast/README.md)**: `/forecast "[time-horizon]" "[topic]"`. Oracle-style prediction for any topic using adaptive live searches, a historical parallel, and falsifiable predictions with causal chains.

---

## Skill format

Each skill is `skills/<name>/SKILL.md`:

```markdown
---
name: skill-name
description: One-line description (used for routing and help)
argument-hint: [arg1] [arg2]
allowed-tools: Read, Grep, Glob
---

Prompt body. Use $ARGUMENTS for the full input, or $0, $1 for positional (0-based) arguments.
```

---

## Repo Structure

```
gab0-agentic-skills/
├── AGENTS.md          # Instructions for agents working in this repo
├── skills/
│   ├── AGENTIC.md     # Index of the agentic engineering skills
│   ├── forecast/      # SKILL.md, README.md, examples/
│   └── <name>/SKILL.md
├── README.md
├── CONTRIBUTING.md
└── LICENSE
```

---

## Contributing

See [CONTRIBUTING.md](./CONTRIBUTING.md) to add a skill.

---

Built by [Gabe](https://github.com/GaboRM9).
