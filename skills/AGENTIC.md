## Agentic Engineering Skills (50)

Install all: `cp skills/*/SKILL.md` into `~/.claude/commands/` as `<name>.md` (loop below).

```bash
for d in skills/*/; do n=$(basename $d); cp $d/SKILL.md ~/.claude/commands/$n.md; done
```

### Design

| Skill | Usage | What it does |
|---|---|---|
| [/agent-spec](./skills/agent-spec/SKILL.md) | `/agent-spec [agent idea]` | Turn a vague agent idea into a tight spec: goal, tools, boundaries, success metrics |
| [/workflow-vs-agent](./skills/workflow-vs-agent/SKILL.md) | `/workflow-vs-agent [task description]` | Decide whether a task needs an agent, a workflow, or one prompt |
| [/multi-agent-topology](./skills/multi-agent-topology/SKILL.md) | `/multi-agent-topology [system goal]` | Design a multi-agent topology with clear roles, handoffs, and shared state |
| [/tool-design](./skills/tool-design/SKILL.md) | `/tool-design [tool or file path]` | Design or audit an agent's tools so models call them correctly |
| [/autonomy-ladder](./skills/autonomy-ladder/SKILL.md) | `/autonomy-ladder [agent or workflow]` | Choose the right autonomy level and human-in-the-loop points for an agent |
| [/agent-persona-prompt](./skills/agent-persona-prompt/SKILL.md) | `/agent-persona-prompt [agent purpose]` | Write a production system prompt for an agent: role, rules, tools, output contract |

### Context

| Skill | Usage | What it does |
|---|---|---|
| [/context-budget](./skills/context-budget/SKILL.md) | `/context-budget [agent, prompt, or repo]` | Audit and shrink what an agent loads into its context window |
| [/memory-architecture](./skills/memory-architecture/SKILL.md) | `/memory-architecture [agent use case]` | Design short-term, long-term, and episodic memory for an agent |
| [/compaction-strategy](./skills/compaction-strategy/SKILL.md) | `/compaction-strategy [agent or transcript]` | Design summarization/compaction that keeps what long-running agents need |
| [/rag-or-not](./skills/rag-or-not/SKILL.md) | `/rag-or-not [corpus and question types]` | Decide between long context, RAG, grep-style agentic search, or fine-tuning |
| [/retrieval-eval](./skills/retrieval-eval/SKILL.md) | `/retrieval-eval [retriever or index]` | Build a quick retrieval quality eval: recall@k, precision, and failure taxonomy |
| [/prompt-cache-plan](./skills/prompt-cache-plan/SKILL.md) | `/prompt-cache-plan [prompt or agent loop]` | Restructure prompts to maximize prompt-cache hits and cut cost/latency |

### Reliability

| Skill | Usage | What it does |
|---|---|---|
| [/failure-modes](./skills/failure-modes/SKILL.md) | `/failure-modes [agent or workflow]` | FMEA for agents: enumerate how it breaks, how bad, how you'd notice |
| [/guardrail-design](./skills/guardrail-design/SKILL.md) | `/guardrail-design [agent or workflow]` | Design input, output, and action guardrails without crippling the agent |
| [/retry-and-fallback](./skills/retry-and-fallback/SKILL.md) | `/retry-and-fallback [agent or API client]` | Design retry, backoff, fallback-model, and idempotency strategy for agent calls |
| [/loop-breaker](./skills/loop-breaker/SKILL.md) | `/loop-breaker [agent or loop code]` | Detect and prevent agent infinite loops and thrashing |
| [/idempotent-tools](./skills/idempotent-tools/SKILL.md) | `/idempotent-tools [tool list or file]` | Make agent tool actions safe to retry, resume, and roll back |
| [/checkpoint-resume](./skills/checkpoint-resume/SKILL.md) | `/checkpoint-resume [agent or workflow]` | Add durable checkpointing so long agent runs survive crashes and can resume |
| [/rollback-plan](./skills/rollback-plan/SKILL.md) | `/rollback-plan [planned agent action]` | Write a rollback and blast-radius plan before an agent touches production |

### Evals

| Skill | Usage | What it does |
|---|---|---|
| [/eval-suite](./skills/eval-suite/SKILL.md) | `/eval-suite [agent or feature]` | Build an eval suite for an agent: cases, graders, and pass criteria |
| [/llm-judge-rubric](./skills/llm-judge-rubric/SKILL.md) | `/llm-judge-rubric [quality dimension]` | Write a reliable LLM-as-judge rubric and calibrate it against human labels |
| [/regression-eval-from-bug](./skills/regression-eval-from-bug/SKILL.md) | `/regression-eval-from-bug [bug description or trace]` | Turn a production failure into a permanent regression eval |
| [/trajectory-review](./skills/trajectory-review/SKILL.md) | `/trajectory-review [trace file or log]` | Analyze an agent trace step by step: where it went wrong and why |
| [/ab-test-prompts](./skills/ab-test-prompts/SKILL.md) | `/ab-test-prompts [variant A] [variant B]` | Run a statistically sane A/B comparison of two prompts or agent configs |

### Workflow

| Skill | Usage | What it does |
|---|---|---|
| [/task-decomposer](./skills/task-decomposer/SKILL.md) | `/task-decomposer [goal]` | Break a big goal into agent-sized tasks with dependencies and acceptance checks |
| [/parallel-agents-plan](./skills/parallel-agents-plan/SKILL.md) | `/parallel-agents-plan [work items]` | Plan safe parallel agent execution: isolation, ownership, and merge strategy |
| [/subagent-brief](./skills/subagent-brief/SKILL.md) | `/subagent-brief [task to delegate]` | Write a self-contained brief for a subagent so it succeeds cold |
| [/plan-before-code](./skills/plan-before-code/SKILL.md) | `/plan-before-code [feature or change]` | Produce and stress-test an implementation plan before an agent writes code |
| [/spec-to-tests](./skills/spec-to-tests/SKILL.md) | `/spec-to-tests [spec or file]` | Convert a spec or acceptance criteria into failing tests first |
| [/verify-before-done](./skills/verify-before-done/SKILL.md) | `/verify-before-done [claimed result or branch]` | Independent verification pass: prove the work meets the goal before declaring done |
| [/agent-pr-review](./skills/agent-pr-review/SKILL.md) | `/agent-pr-review [diff, branch, or PR]` | Review an agent-authored diff for the specific ways agents get it wrong |
| [/handoff-notes](./skills/handoff-notes/SKILL.md) | `/handoff-notes [current work]` | Write a session handoff so the next agent or human resumes with zero loss |
| [/repo-onboarding-map](./skills/repo-onboarding-map/SKILL.md) | `/repo-onboarding-map [repo path]` | Build an agent-friendly map of a repo: structure, commands, conventions, landmines |
| [/claude-md-audit](./skills/claude-md-audit/SKILL.md) | `/claude-md-audit [path to CLAUDE.md]` | Audit a CLAUDE.md/AGENTS.md for bloat, contradictions, and missing rules |

### Harness

| Skill | Usage | What it does |
|---|---|---|
| [/hook-designer](./skills/hook-designer/SKILL.md) | `/hook-designer [behavior to enforce]` | Design Claude Code hooks that enforce rules deterministically instead of by prompt |
| [/skill-author](./skills/skill-author/SKILL.md) | `/skill-author [skill idea]` | Write a high-quality skill/slash command with tight frontmatter and a testable output |
| [/permissions-audit](./skills/permissions-audit/SKILL.md) | `/permissions-audit [settings file or project]` | Audit agent permissions and allowlists for least privilege |
| [/mcp-server-eval](./skills/mcp-server-eval/SKILL.md) | `/mcp-server-eval [MCP server name or repo]` | Evaluate an MCP server before trusting it: tools, permissions, injection surface |
| [/prompt-injection-audit](./skills/prompt-injection-audit/SKILL.md) | `/prompt-injection-audit [agent or workflow]` | Red-team an agent for prompt injection through every untrusted input path |
| [/sandbox-plan](./skills/sandbox-plan/SKILL.md) | `/sandbox-plan [what the agent executes]` | Plan a sandbox for running agent-generated code safely |

### Ops

| Skill | Usage | What it does |
|---|---|---|
| [/agent-observability](./skills/agent-observability/SKILL.md) | `/agent-observability [agent code]` | Add tracing and metrics so every agent run is explainable after the fact |
| [/cost-optimizer](./skills/cost-optimizer/SKILL.md) | `/cost-optimizer [agent or usage logs]` | Cut agent cost per successful task without lowering quality |
| [/model-router](./skills/model-router/SKILL.md) | `/model-router [agent steps]` | Design a router that sends each step to the cheapest model that can handle it |
| [/incident-postmortem](./skills/incident-postmortem/SKILL.md) | `/incident-postmortem [incident description or logs]` | Blameless postmortem for an agent incident with systemic fixes |
| [/human-in-the-loop-ux](./skills/human-in-the-loop-ux/SKILL.md) | `/human-in-the-loop-ux [agent actions needing approval]` | Design approval and escalation UX that humans will actually use |

### Research

| Skill | Usage | What it does |
|---|---|---|
| [/framework-compare](./skills/framework-compare/SKILL.md) | `/framework-compare [use case] [candidates...]` | Compare agent frameworks/SDKs for your use case with live research |
| [/paper-to-prototype](./skills/paper-to-prototype/SKILL.md) | `/paper-to-prototype [paper URL or title]` | Turn an agent/LLM research paper into a minimal working prototype plan |
| [/agent-threat-model](./skills/agent-threat-model/SKILL.md) | `/agent-threat-model [system description]` | STRIDE-style threat model for an agentic system |
| [/synthetic-data-gen](./skills/synthetic-data-gen/SKILL.md) | `/synthetic-data-gen [task] [count]` | Generate diverse synthetic test and eval data with coverage control |
| [/structured-output-design](./skills/structured-output-design/SKILL.md) | `/structured-output-design [output need]` | Design output schemas and validation so agent results are machine-reliable |

