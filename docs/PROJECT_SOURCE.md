# Agent Skills Library — Project Source

## Purpose

This repository stores reusable Agent Skills as a portable source library.

The goal is to create a clean collection of skills that can be browsed, copied, downloaded, installed, or adapted. The repository should be easy to scan on GitHub and easy for Codex to maintain.

## Main workflow

The intended workflow is:

1. ChatGPT brainstorms skill ideas.
2. ChatGPT turns a selected idea into a structured skill brief.
3. ChatGPT writes complete `SKILL.md` content.
4. Codex creates or updates the correct folders and files in the GitHub repo.
5. Codex categorizes the skill in the taxonomy.
6. Codex updates the catalog and README navigation.
7. A user can later copy or download the finished skill into their own agent setup.

Codex is the repository automation worker. It should create folders, write markdown files, update indexes, and maintain consistency.

## Canonical source location

All source skills in this repository must use this structure:

```txt
skills/<category>/<skill-name>/SKILL.md
```

Examples:

```txt
skills/skill-authoring/skill-brief-writer/SKILL.md
skills/repo-readiness/github-pages-readiness/SKILL.md
skills/npm-publishing/npm-publish-readiness/SKILL.md
skills/docs-seo/demo-index-docs-enhancer/SKILL.md
skills/code-review/bundle-bloat-review/SKILL.md
```

Do not use `.agents/skills/` as the main source location for this repository.

`.agents/skills/` may be referenced only as an optional export or install target for users who want to copy a skill into a local agent environment.

## Skill package shape

Each skill must be a folder containing a `SKILL.md` file.

Allowed optional folders inside a skill package:

```txt
references/
scripts/
assets/
agents/
```

Example:

```txt
skills/code-review/bundle-bloat-review/
├─ SKILL.md
├─ references/
│  └─ bundling-checklist.md
└─ scripts/
   └─ inspect-package.mjs
```

Only create optional folders when they are useful.

## Taxonomy

Use taxonomy folders for human navigation.

Primary categories:

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

A skill belongs to one primary category folder.

Additional tags can be stored in frontmatter and in `catalog/skills.json`.

## Skill naming rules

Skill names must:

- use lowercase letters, numbers, and hyphens only
- avoid spaces, underscores, uppercase letters, and double hyphens
- not start or end with a hyphen
- match the skill folder name exactly
- describe a reusable workflow

Good examples:

```txt
skill-brief-writer
github-pages-readiness
npm-publish-readiness
release-readiness-review
demo-index-docs-enhancer
bundle-bloat-review
baseline-support-check
```

Bad examples:

```txt
Skill Writer
npm_publish
review
my-cool-skill
```

## Required SKILL.md frontmatter

Every `SKILL.md` must start with YAML frontmatter:

```yaml
---
name: github-pages-readiness
description: Checks whether a repository is ready to be published with GitHub Pages. Use when the user asks to verify build output, base paths, asset URLs, routing, demo links, README instructions, or GitHub Pages deployment readiness.
license: MIT
compatibility: Portable Agent Skill. Can be copied into an Agent Skills-compatible environment with repository file access unless stated otherwise.
metadata:
  category: repo-readiness
  task_type: review
  audience: frontend-developers
  tags:
    - github-pages
    - deployment
    - static-site
    - docs
  status: draft
  side_effects: none
---
```

## Standard SKILL.md body

Use this body structure unless the skill needs a justified variation:

```md
# Skill Title

## Purpose

Explain what this skill helps the agent do.

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

## Catalog rules

Every skill must be listed in:

```txt
catalog/skills.json
```

Use this shape:

```json
{
  "name": "github-pages-readiness",
  "path": "skills/repo-readiness/github-pages-readiness/SKILL.md",
  "category": "repo-readiness",
  "task_type": "review",
  "tags": ["github-pages", "deployment", "static-site", "docs"],
  "status": "draft",
  "side_effects": "none",
  "summary": "Checks whether a repository is ready to publish through GitHub Pages."
}
```

Keep catalog entries sorted alphabetically by `name`.

## README navigation rules

The root `README.md` must include a skill table:

```md
| Skill | Category | Type | Summary |
|---|---|---|---|
| [github-pages-readiness](skills/repo-readiness/github-pages-readiness/SKILL.md) | repo-readiness | review | Checks whether a repository is ready for GitHub Pages. |
```

Keep rows sorted alphabetically by skill name.

## Codex responsibilities

When Codex is asked to create a skill, it must:

1. Determine the correct skill name.
2. Determine the correct category folder.
3. Create the folder:

   ```txt
   skills/<category>/<skill-name>/
   ```

4. Create the file:

   ```txt
   skills/<category>/<skill-name>/SKILL.md
   ```

5. Add optional support files only if required.
6. Update `catalog/skills.json`.
7. Update `README.md`.
8. Update `docs/TAXONOMY.md` if a new category or convention is introduced.
9. Run a consistency check before finishing.

## What Codex must not do

Codex must not:

- place source skills in `.agents/skills/`
- create loose markdown files instead of skill folders
- invent categories without updating taxonomy docs
- skip catalog updates
- create giant multi-purpose skills
- add scripts unless they improve repeatability
- add destructive or publishing actions without explicit user approval
