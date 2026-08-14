# Model and Effort Routing

Use this reference only when selecting a model or reasoning effort for delegated work. Inspect the current runtime's model list first; identifiers and supported effort levels can change.

## Contents

1. [Model tiers](#model-tiers)
2. [Workload routing](#workload-routing)
3. [Reasoning effort](#reasoning-effort)
4. [Escalation](#escalation)
5. [Common patterns](#common-patterns)
6. [Runtime constraints](#runtime-constraints)

## Model tiers

Route by capability profile, then choose an available identifier.

| Tier | Use for | Current examples when available |
|---|---|---|
| Fast | Tiny deterministic lookup, repetitive extraction, small mechanical checks | `gpt-5.6-luna` |
| Balanced | Targeted inspection, repository exploration, large-file review, documentation research, evidence gathering | `gpt-5.6-terra` |
| Frontier reasoning | Complex review, architecture, difficult debugging, security, non-trivial implementation, synthesis, adjudication | `gpt-5.6-sol`, or the strongest suitable frontier model exposed by the runtime |

Model names are examples, not requirements. Never request a model that the spawn tool does not expose.

### Fast tier

Choose the fast tier when the task is narrow, unambiguous, repeatable, inexpensive to verify, and mostly mechanical.

Examples:

- Locate files or symbols.
- Extract exported function names.
- Check a list of files for one pattern.
- Summarize individual test failures.
- Verify that named artifacts exist.

Do not choose the fast tier merely because a task is delegated.

### Balanced tier

Choose the balanced tier for read-heavy, search-heavy, or large-context supporting work.

Examples:

- Map an authentication flow.
- Trace where component state is controlled.
- Inspect build configuration.
- Review documentation for inconsistencies.
- Gather evidence for likely regression causes.

Use balanced agents as scouts. Escalate the reasoning step only if their evidence reveals genuine ambiguity.

### Frontier reasoning tier

Choose the frontier tier when the task requires ambiguity resolution, multi-step planning, architectural judgment, difficult debugging, consequential code modification, security analysis, conflict resolution, or tool-orchestrated validation.

Examples:

- Determine the root cause from competing hypotheses.
- Design an implementation strategy across several systems.
- Review concurrency correctness.
- Implement and verify a non-trivial feature.
- Reconcile conflicting agent evidence.

Do not spend the strongest model on work that is essentially search plus summarization.

## Workload routing

| Task class | Default tier | Default effort | Escalate when |
|---|---|---|---|
| Lookup or extraction | Fast | low | Inputs are inconsistent or interpretation is required |
| Scan or targeted inspection | Fast or balanced | low or medium | Scope is broad or relationships must be traced |
| Exploration or research | Balanced | medium | Evidence conflicts or architectural judgment is needed |
| Review | Balanced or frontier | medium | Correctness, security, or subtle edge cases dominate |
| Debugging | Frontier | high | Cross-system behavior or several plausible causes remain |
| Planning | Frontier | medium or high | Trade-offs are consequential or architecture is unresolved |
| Implementation | Frontier | medium | Blast radius, ambiguity, or failure cost is high |
| Validation | Balanced or frontier | medium or high | The change affects guarantees or high-risk behavior |
| Adjudication | Frontier | high | Evidence is contradictory or incomplete |

## Reasoning effort

Choose effort independently from model tier.

### Low

Use for nearly deterministic work with tiny scope and few meaningful alternatives:

- File location
- Value extraction
- Simple existence or consistency checks

### Medium

Use as the normal default when several files or facts need bounded synthesis and uncertainty is moderate.

### High

Use when the agent must trace complex behavior, challenge assumptions, investigate edge cases, review correctness, debug ambiguous failures, or validate consequential behavior.

### Xhigh or max

Reserve for unusually difficult architecture, concurrency, correctness, cross-system debugging, or adjudication where deeper reasoning can materially alter the result. Prefer one deeply reasoning agent to several duplicative agents when the problem is fundamentally one hard reasoning task.

### Ultra

Use only when the runtime supports it and the task demonstrably warrants the maximum available reasoning. Availability alone is not justification.

## Escalation

Reduce uncertainty cheaply before escalating:

```txt
Scout -> Reason -> Implement -> Validate
```

Escalate only when a result is required and the current route:

- Cannot resolve material ambiguity
- Produces contradictory evidence
- Repeatedly misses necessary context
- Discovers substantially higher complexity than expected

A typical escalation path is:

```txt
fast / low
    -> balanced / medium
    -> frontier / high
    -> frontier / xhigh or max
```

Do not escalate merely because an answer is concise.

## Common patterns

### Repository review

```txt
balanced / medium -> architecture explorer --\
balanced / medium -> test explorer --------+-> parent synthesis
frontier / high  -> correctness reviewer --/
```

### Bug investigation

```txt
balanced / medium -> reproduce and gather evidence --\
balanced / medium -> map responsible code ----------+-> frontier / high root-cause analysis
                                                        -> frontier / medium implementation
                                                        -> frontier / high validation
```

### Large documentation task

```txt
fast / low        -> deterministic extraction --\
balanced / medium -> section analysis --------+-> frontier / medium synthesis
balanced / medium -> consistency review ------/
```

### Multi-dimensional review

Run only relevant dimensions independently, such as correctness, security, performance, test coverage, accessibility, or maintainability. Use lighter agents for evidence gathering and frontier reasoning for dimensions that require it.

## Runtime constraints

- Inspect actual concurrency capacity before choosing agent count.
- Use the runtime's exact model and reasoning parameter names.
- If per-spawn model selection is unavailable, delegate with the closest available agent and describe the workload requirements in its prompt.
- If a model override requires limited or no inherited conversation context, include the necessary task-local context explicitly.
- Do not assume a named built-in role exists. Express the role and constraints in the subagent prompt.
- Do not rely on permission labels the runtime cannot enforce; state write prohibitions and ownership boundaries explicitly.
- Do not fail the workflow because an example model identifier is unavailable.
