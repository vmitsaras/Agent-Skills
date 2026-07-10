# Authoring Guide

This guide defines how to write skills for this library.

## Goal

A skill should package a repeatable workflow so another agent or user can apply it consistently.

Do not write random prompt fragments. Do not write giant all-purpose assistants. A skill should do one clear job.

## Required package shape

Every skill must be a folder with a required `SKILL.md` file:

```txt
skills/<category>/<skill-name>/SKILL.md
```

Optional support folders:

```txt
references/
scripts/
assets/
agents/
```

Use optional folders only when they improve clarity or repeatability.

## Required frontmatter

Every `SKILL.md` must start with YAML frontmatter.

```yaml
---
name: skill-name
description: Clear action-first description of what this skill does and when to use it.
license: MIT
compatibility: Portable Agent Skill. Can be copied into an Agent Skills-compatible environment with repository file access unless stated otherwise.
metadata:
  category: repo-readiness
  task_type: review
  audience: frontend-package-maintainers
  tags:
    - github
    - release
  status: draft
  side_effects: none
---
```

## Frontmatter field rules

| Field | Required | Rule |
|---|---:|---|
| `name` | Yes | Must match the skill folder name exactly |
| `description` | Yes | Must say what the skill does and when to use it |
| `license` | Yes | Use `MIT` unless a skill requires another license |
| `compatibility` | Yes | Explain that the skill is portable and requires repo/file access if relevant |
| `metadata.category` | Yes | Must match the category folder |
| `metadata.task_type` | Yes | Use a known task type from `docs/TAXONOMY.md` |
| `metadata.audience` | Yes | Name the main user or maintainer group |
| `metadata.tags` | Yes | Use lowercase hyphenated tags |
| `metadata.status` | Yes | Usually `draft` for new skills |
| `metadata.side_effects` | Yes | Must declare operational impact |

## Description writing

The `description` is the most important field for discovery.

A strong description:

- starts with an action verb
- names the artifact or workflow
- includes common trigger phrases
- states when to use the skill
- avoids vague words such as “helps” without context

Good:

```yaml
description: Reviews a JavaScript or TypeScript package repository for npm publishing readiness. Use when the user asks to check package.json, exports, build output, type declarations, README, changelog, npm metadata, tests, or release blockers.
```

Bad:

```yaml
description: Helps with publishing.
```

## Standard body structure

Use this layout by default:

```md
# Skill Title

## Purpose

One short paragraph explaining the reusable workflow.

## When to use this skill

Use this skill when:
- ...

Do not use this skill when:
- ...

## Inputs to inspect

- ...

## Workflow

1. ...
2. ...
3. ...

## Output format

Return:
- Summary
- Findings
- Recommended changes
- Files to create or edit
- Validation checklist

## Quality bar

The task is complete only when:
- ...

## Edge cases

- ...

## Related skills

- ...
```

## Purpose section

Keep the purpose short.

Good:

```md
## Purpose

Review a package repository for npm publishing readiness, focusing on metadata, exports, build output, type declarations, docs, and release blockers.
```

Bad:

```md
## Purpose

This skill helps with many things around JavaScript projects, npm, docs, GitHub, CI, release notes, and maybe marketing.
```

## When to use section

Include both positive and negative triggers.

Good:

```md
Use this skill when:
- The user asks whether a package is ready to publish to npm.
- The user wants a pre-release checklist.
- The user asks to inspect package metadata, exports, build output, or type declarations.

Do not use this skill when:
- The user only wants help writing marketing copy.
- The package is not intended for npm.
- Another more specific release skill applies.
```

## Inputs to inspect section

List likely files and folders.

Examples:

```md
- `package.json`
- `README.md`
- `CHANGELOG.md`
- `LICENSE`
- `src/`
- `dist/`
- `types/`
- `.github/workflows/`
```

Do not tell the agent to read the whole repository unless necessary. Start with the smallest useful set of files.

## Workflow section

Write concrete steps.

Good:

```md
1. Inspect package metadata in `package.json`.
2. Verify the declared entry points exist in the build output.
3. Check whether type declarations are generated and referenced correctly.
4. Review README installation and usage instructions.
5. Report blockers before nice-to-have improvements.
```

Bad:

```md
1. Look around.
2. Fix things.
3. Make it good.
```

## Output format section

Make the output predictable.

Recommended format:

```md
## Summary

Brief outcome.

## Findings

| Priority | Issue | Evidence | Recommendation |
|---|---|---|---|

## Recommended changes

- ...

## Validation checklist

- [ ] ...
```

## Quality bar section

Define completion clearly.

Good:

```md
The task is complete only when:
- Each finding cites a specific file, field, command, or missing artifact.
- Release blockers are separated from improvements.
- The final answer includes a clear publish/no-publish recommendation.
```

## Optional references

Use `references/` for long supporting material, such as:

- detailed checklists
- standards summaries
- long examples
- comparison tables
- package-specific conventions

The main `SKILL.md` should point to these files instead of becoming a 2,000-line wall of doom. Walls of doom are for castles, not skills.

## Optional scripts

Use `scripts/` only when a repeatable command improves accuracy.

Good script use cases:

- inspecting `package.json`
- validating links
- checking bundle size
- checking generated files
- producing a machine-readable report

Do not add scripts just to look fancy.

## Side effects

Every skill must declare side effects.

Default to:

```yaml
side_effects: none
```

Use stronger labels only when needed:

```yaml
side_effects: file-write
side_effects: command-run
side_effects: network
side_effects: external-side-effect
```

A skill with external side effects must require explicit user approval before publishing, deploying, deleting, sending, or modifying remote systems.

## Related skills

List related skill names when useful. Do not invent non-existent related skills unless they are clearly marked as proposed.

Good:

```md
## Related skills

- `release-readiness-review`
- `github-pages-readiness`
```

## Final authoring checklist

Before accepting a skill:

- [ ] The skill does one clear job.
- [ ] The folder name and frontmatter `name` match.
- [ ] The category folder and `metadata.category` match.
- [ ] The description is action-first and trigger-oriented.
- [ ] The workflow is concrete and ordered.
- [ ] The output format is predictable.
- [ ] Side effects are declared.
- [ ] Long material is moved into support files when needed.
- [ ] The catalog entry is ready.
- [ ] The README row is ready.
