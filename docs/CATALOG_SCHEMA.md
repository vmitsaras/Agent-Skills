# Catalog Schema

The catalog files make the library easy to scan, search, validate, and render into documentation.

## Files

```txt
catalog/skills.json
catalog/taxonomy.json
```

`catalog/skills.json` lists every skill.

`catalog/taxonomy.json` lists allowed categories and their display metadata.

## skills.json shape

Use this structure:

```json
{
  "skills": [
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
  ]
}
```

## Required skill fields

| Field | Type | Required | Notes |
|---|---|---:|---|
| `name` | string | Yes | Must match the skill folder and frontmatter `name` |
| `path` | string | Yes | Must point to `skills/<category>/<skill-name>/SKILL.md` |
| `category` | string | Yes | Must exist in taxonomy |
| `task_type` | string | Yes | Use a known task type |
| `tags` | string[] | Yes | Lowercase hyphenated tags |
| `status` | string | Yes | Usually `draft` for new skills |
| `side_effects` | string | Yes | Use known side-effect values |
| `summary` | string | Yes | Short human-readable summary |

## Sorting

Keep `skills` sorted alphabetically by `name`.

## Path rules

Good:

```json
"path": "skills/repo-readiness/github-pages-readiness/SKILL.md"
```

Bad:

```json
"path": ".agents/skills/github-pages-readiness/SKILL.md"
```

Bad:

```json
"path": "skills/github-pages-readiness.md"
```

## taxonomy.json shape

Use this structure:

```json
{
  "categories": [
    {
      "id": "repo-readiness",
      "label": "Repo Readiness",
      "description": "GitHub, release, CI, public repo, and project readiness skills."
    }
  ]
}
```

Keep categories sorted in the same order as `docs/TAXONOMY.md`.

## Consistency rules

For every skill:

- `catalog.skills[].name` must match frontmatter `name`.
- `catalog.skills[].category` must match the category folder.
- `catalog.skills[].path` must exist.
- README must link to the same path.
- Tags should be aligned with frontmatter tags.

## Empty initial catalog

Use this for a new repo:

```json
{
  "skills": []
}
```
