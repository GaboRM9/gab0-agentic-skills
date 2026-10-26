# Contributing a New Skill

## Folder Structure

Each skill lives in its own folder under `skills/`:

```
skills/<skill-name>/
├── SKILL.md              # The prompt file
├── README.md             # Skill documentation
└── examples/
    └── sample-output.md  # Annotated example output
```

Use **lowercase-hyphenated** names (e.g., `market-scan`, `code-review`, `pitch-coach`).

---

## SKILL.md Template

```markdown
---
name: skill-name
description: One-line description of what the skill does
argument-hint: [arg1] [arg2]
allowed-tools: WebSearch, WebFetch
---

[Your skill prompt here. Use $0, $1 for positional arguments.]
```

### Frontmatter Fields

| Field | Required | Notes |
|-------|----------|-------|
| `name` | Yes | Lowercase-hyphenated, matches folder name |
| `description` | Yes | Shown in `/help` — be specific |
| `argument-hint` | Yes | Shown as usage hint |
| `allowed-tools` | Yes | Only list tools the skill actually uses |

### Argument Syntax

Use **0-based positional variables**:
- `$0` — first argument
- `$1` — second argument
- `$ARGUMENTS` — all arguments as a single string

```markdown
**Topic:** $1
**Time Horizon:** $0
```

Do NOT use `$1`/`$2` (1-based bash syntax) or `$ARGUMENTS[0]` (array syntax — not supported).

---

## README.md Template

Every skill needs a `README.md` covering:

```markdown
# /skill-name

One-sentence description of what the skill does.

## Install
[copy command]

## Invoke
[invocation syntax + argument table]

## Examples
[3–5 example invocations across different use cases]

## What It Produces
[table of output sections with descriptions]

## How It Works (Internal)
[brief description of the research or processing logic]

## Tips
[2–4 tips for best results]
```

See [skills/forecast/README.md](./skills/forecast/README.md) as the reference implementation.

---

## sample-output.md Template

Provide an annotated real example — not a template with `[placeholder]` values.
Show actual example content for each section with a brief note explaining what it is.

```markdown
# /skill-name — Sample Output

## Invocation
[the exact command used]

## Output Structure (Annotated)

### Section Name
[Example content from a real run]
[One sentence explaining what this section is and why it matters]

...repeat for each section...

## Notes
[Quirks, caveats, tips for best results]
```

See [skills/forecast/examples/sample-output.md](./skills/forecast/examples/sample-output.md) as the reference implementation.

---

## Testing Locally

1. Copy your skill into your agent's skills/commands directory as `<skill-name>.md`
2. Open your agent in any project
3. Invoke with `/skill-name arg1 arg2`
4. Verify the output matches the structure in `examples/sample-output.md`
5. Test edge cases: missing args, broad topics, unusual inputs
6. Remove the copy when done

---

## Adding to README.md

Add a row to the Skills table:

```markdown
| [/skill-name](./skills/skill-name/README.md) | `/skill-name "[arg1]" "[arg2]"` | Brief one-line description |
```

Link to the skill's `README.md`, not `SKILL.md`.
