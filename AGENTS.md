# gab0-agentic-skills — Agent Instructions

## What This Repo Is

My personal collection of agentic engineering skills. Each skill is a self-contained markdown prompt an agent executes when invoked as `/skill-name`. Skills are harness-agnostic: no vendor- or model-specific references.

## Skills in This Repo

| Skill | Invocation | Description |
|-------|-----------|-------------|
| forecast | `/forecast "1 week" "Mexico"` | Live-research Oracle forecast for any topic — domain-adaptive, causal predictions, historical parallel |

## Naming Conventions

- All skill folders use **lowercase-hyphenated** names (e.g., `skills/forecast/`, `skills/market-scan/`)
- `SKILL.md` is always uppercase
- `README.md` lives at the skill level for documentation
- Example files go in `examples/` subfolder

## Skill Structure Requirements

Every skill must have:

```
skills/<skill-name>/
├── SKILL.md              # The prompt file (with frontmatter)
├── README.md             # Skill documentation
└── examples/
    └── sample-output.md  # Annotated example output
```

### Required SKILL.md Frontmatter

```yaml
---
name: skill-name
description: One-line description of what the skill does
argument-hint: [arg1] [arg2]
allowed-tools: WebSearch, WebFetch   # list only what the skill actually needs
---
```

### Argument Syntax

Skills use **positional 0-based** argument variables:
- `$0` — first argument
- `$1` — second argument
- `$ARGUMENTS` — all arguments as a single string

Do NOT use `$1`/`$2` (1-based, wrong) or `$ARGUMENTS[0]`/`$ARGUMENTS[1]` (array syntax, not supported).

## How to Test a Skill Locally

1. Copy the skill's `SKILL.md` into your agent's skills/commands directory as `<skill-name>.md`
2. Open your agent in any project
3. Invoke with `/skill-name arg1 arg2`
4. Verify the output follows the skill's Output section
5. Remove the copy when done testing

## Adding a New Skill

See `CONTRIBUTING.md` for the full process.

The 50 agentic engineering skills are indexed in `skills/AGENTIC.md`; they ship as a single `SKILL.md` each. Add a README and example only where a skill earns one.
