# Skill Brief Template

Use this template before writing a new `SKILL.md`.

## Skill idea

Describe the skill in one sentence.

```txt
<This skill will...>
```

## Proposed name

```txt
<lowercase-hyphenated-skill-name>
```

## Category

Choose one:

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

Selected category:

```txt
<category>
```

## Target path

```txt
skills/<category>/<skill-name>/SKILL.md
```

## User trigger phrases

List phrases that should cause an agent to use this skill.

- "..."
- "..."
- "..."

## Description draft

Write the frontmatter `description`.

```yaml
description: <action-first description that says what the skill does and when to use it>
```

## Skill purpose

What reusable job does this skill perform?

```txt
<answer>
```

## In scope

- ...
- ...
- ...

## Out of scope

- ...
- ...
- ...

## Inputs to inspect

- `...`
- `...`
- `...`

## Workflow outline

1. ...
2. ...
3. ...
4. ...
5. ...

## Output format

The skill should return:

- Summary
- Findings
- Recommended changes
- Files changed or files to create
- Validation checklist

## Side effects

Choose one:

- `none`
- `file-write`
- `command-run`
- `network`
- `external-side-effect`

Selected value:

```txt
<side_effects>
```

## Optional support files

Will this skill need support files?

- [ ] No
- [ ] `references/`
- [ ] `scripts/`
- [ ] `assets/`
- [ ] `agents/`

If yes, list them:

```txt
<file paths and purposes>
```

## Catalog entry draft

```json
{
  "name": "<skill-name>",
  "path": "skills/<category>/<skill-name>/SKILL.md",
  "category": "<category>",
  "task_type": "<task_type>",
  "tags": [],
  "status": "draft",
  "side_effects": "<side_effects>",
  "summary": "<short summary>"
}
```

## README row draft

```md
| [<skill-name>](skills/<category>/<skill-name>/SKILL.md) | <category> | <task_type> | <summary> |
```

## Review notes

- [ ] Name is valid.
- [ ] Category is valid.
- [ ] Description is trigger-oriented.
- [ ] Scope is narrow.
- [ ] Output is explicit.
- [ ] Side effects are declared.
