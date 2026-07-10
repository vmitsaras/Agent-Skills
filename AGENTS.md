# AGENTS.md

## Repository purpose

This repository is a portable library of reusable Agent Skills.

It is a source catalog for browsing, copying, downloading, adapting, and installing skills elsewhere. It is not primarily a live runtime skill folder.

## Canonical source layout

All source skills must live under:

```txt
skills/<category>/<skill-name>/SKILL.md
```

Example:

```txt
skills/repo-readiness/github-pages-readiness/SKILL.md
skills/npm-publishing/npm-publish-readiness/SKILL.md
skills/docs-seo/demo-index-docs-enhancer/SKILL.md
```

Do not place source skills in `.agents/skills/`.

`.agents/skills/` may be mentioned only in documentation as an optional installation/export target for users who want to copy a finished skill into a local agent setup.

## Default Codex workflow

When asked to create a new skill:

1. Read this file, `docs/PROJECT_SOURCE.md`, `docs/TAXONOMY.md`, `docs/AUTHORING_GUIDE.md`, and `templates/SKILL_TEMPLATE.md`.
2. Convert the request into a specific reusable workflow.
3. Choose one taxonomy category.
4. Create the folder:

   ```txt
   skills/<category>/<skill-name>/
   ```

5. Create the required file:

   ```txt
   skills/<category>/<skill-name>/SKILL.md
   ```

6. Add optional support folders only when they materially improve the skill:

   ```txt
   references/
   scripts/
   assets/
   agents/
   ```

7. Update `catalog/skills.json`.
8. Update the skill navigation table in `README.md`.
9. Update `docs/TAXONOMY.md` only if a category or convention changes.
10. Run the repository consistency checklist before finishing.

## Skill naming rules

Skill names must:

- use lowercase letters, numbers, and hyphens only
- not contain spaces, underscores, uppercase letters, or double hyphens
- not start or end with a hyphen
- match the parent folder name exactly
- describe a reusable workflow

Preferred examples:

```txt
skill-brief-writer
github-pages-readiness
npm-publish-readiness
release-readiness-review
demo-index-docs-enhancer
bundle-bloat-review
a11y-plugin-review
```

Avoid:

```txt
SkillWriter
skill_writer
review
my-cool-thing
```

## Taxonomy categories

Use one of these values for `metadata.category`:

- `skill-authoring`
- `project-planning`
- `repo-readiness`
- `npm-publishing`
- `docs-seo`
- `frontend-a11y`
- `ui-ux-polish`
- `code-review`
- `content-portfolio`
- `research-synthesis`
- `maintenance`

If none fits, use `maintenance` and add a TODO in the relevant docs explaining the proposed new category.

## Required SKILL.md frontmatter

Every skill must start with frontmatter like this:

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

The `name` must match the skill folder name.

The `description` must be specific enough for an agent to decide when to use the skill.

## Standard SKILL.md body

Use this body structure by default:

```md
# Skill Name

## Purpose

Explain the reusable workflow.

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
- ...

## Quality bar

The task is complete only when:
- ...

## Edge cases

- ...

## Related skills

- ...
```

## Catalog update rules

When adding or changing a skill, update `catalog/skills.json`.

Use this shape:

```json
{
  "name": "release-readiness-review",
  "path": "skills/repo-readiness/release-readiness-review/SKILL.md",
  "category": "repo-readiness",
  "task_type": "review",
  "tags": ["release", "github", "npm", "qa"],
  "status": "draft",
  "side_effects": "none",
  "summary": "Reviews a repository for release or public GitHub readiness."
}
```

If `catalog/skills.json` does not exist, create it with:

```json
{
  "skills": []
}
```

Keep entries sorted alphabetically by `name`.

## README update rules

When adding a skill, update the README navigation table.

Use columns:

```md
| Skill | Category | Type | Summary |
|---|---|---|---|
```

Skill links must point to the source `SKILL.md` file.

Example:

```md
| [github-pages-readiness](skills/repo-readiness/github-pages-readiness/SKILL.md) | repo-readiness | review | Checks whether a repository is ready for GitHub Pages deployment. |
```

## Consistency checklist

Before finishing any skill creation or update, verify:

- The skill folder exists under `skills/<category>/<skill-name>/`.
- The file is named `SKILL.md`.
- The frontmatter has `name` and `description`.
- The frontmatter `name` matches the parent folder.
- The frontmatter category matches the category folder.
- The category exists in `docs/TAXONOMY.md`.
- The description is specific and trigger-oriented.
- The workflow is step-by-step.
- The output format is explicit.
- Side effects are declared.
- The skill is listed in `catalog/skills.json`.
- The README navigation row is updated.
- Optional folders exist only when useful.

## Do not

- Do not create source skills under `.agents/skills/`.
- Do not create loose markdown files such as `skills/foo.md`.
- Do not create one giant skill that handles unrelated workflows.
- Do not invent new categories without updating docs.
- Do not skip catalog updates.
- Do not add scripts unless they improve repeatability.
- Do not add external publishing, deletion, deployment, or remote mutation behavior unless explicitly requested.
- Do not include secrets, private credentials, or user-specific private context in reusable skills.
