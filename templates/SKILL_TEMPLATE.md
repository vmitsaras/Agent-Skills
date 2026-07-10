---
name: replace-with-skill-name
description: Replace with a clear action-first description of what this skill does and when to use it. Include likely trigger phrases the user may type.
license: MIT
compatibility: Portable Agent Skill. Can be copied into an Agent Skills-compatible environment with repository file access unless stated otherwise.
metadata:
  category: replace-with-category
  task_type: replace-with-review-writer-planner-generator-refactor-maintenance-or-research
  audience: replace-with-target-audience
  tags:
    - replace-me
  status: draft
  side_effects: none
---

# Replace With Skill Title

## Purpose

Explain the reusable workflow this skill performs.

Keep this focused. One skill should do one repeatable job.

## When to use this skill

Use this skill when:

- The user asks to ...
- The repository contains ...
- The task involves ...

Do not use this skill when:

- The request is unrelated to ...
- The user only needs a quick explanation, not a repeatable workflow.
- Another more specific skill already covers the task.

## Inputs to inspect

Inspect relevant files such as:

- `package.json`
- `README.md`
- `CHANGELOG.md`
- `LICENSE`
- `docs/`
- `src/`
- `examples/`
- `demo/`
- `.github/workflows/`

Adjust this list to the skill.

## Workflow

1. Identify the target artifact or repository area.
2. Read the minimum files needed to understand the current state.
3. Compare the current state against the expected standard.
4. Record findings as clear issues, not vague opinions.
5. Propose changes in priority order.
6. Apply file changes only if the user asked for implementation.
7. Validate the result against the quality bar.

## Output format

Return the result using this structure:

```md
## Summary

Brief outcome.

## Findings

| Priority | Issue | Evidence | Recommendation |
|---|---|---|---|

## Changes made

- ...

## Remaining TODOs

- ...

## Validation

- [ ] ...
```

If no files were changed, replace `Changes made` with `Recommended changes`.

## Quality bar

The task is complete only when:

- The answer is specific to the actual repository or provided brief.
- Findings include evidence.
- Recommendations are actionable.
- The output format is consistent.
- Any created files follow project naming and taxonomy rules.
- Side effects are avoided unless explicitly requested.

## Edge cases

- If required files are missing, report what is missing and provide a minimal recommended structure.
- If the repository uses an unusual layout, adapt without forcing a standard layout blindly.
- If the task requires current external data, state that web/package registry verification is required before final claims.
- If the user asks for implementation but the risk is high, make the smallest safe change first.

## Related skills

- Add related skill names here.
