# Taxonomy

This taxonomy keeps the Agent Skills library easy to scan, browse, and maintain.

Each skill has one primary category folder:

```txt
skills/<category>/<skill-name>/SKILL.md
```

Secondary concepts belong in tags, not folder nesting.

## Categories

| Category | Use for | Example skills |
|---|---|---|
| `skill-authoring` | Creating, refining, reviewing, validating, and maintaining skills | `skill-brief-writer`, `skill-smell-review`, `skill-authoring-review` |
| `project-planning` | Roadmaps, implementation plans, milestones, issue plans, and task breakdowns | `repo-roadmap-planner`, `implementation-checkpoint-writer` |
| `repo-readiness` | GitHub/public repo checks, release readiness, CI readiness, docs completeness, project hygiene | `github-pages-readiness`, `release-readiness-review` |
| `npm-publishing` | npm package metadata, exports, type declarations, build outputs, changelogs, publishing readiness | `npm-publish-readiness`, `package-json-normalizer` |
| `docs-seo` | README quality, documentation structure, demo pages, metadata, JSON-LD, search/discoverability | `demo-index-docs-enhancer`, `jsonld-plugin-schema-advisor` |
| `frontend-a11y` | Accessibility, semantic HTML, ARIA, keyboard navigation, focus states, WCAG-style review | `a11y-plugin-review`, `keyboard-flow-audit` |
| `ui-ux-polish` | Visual quality, motion, interactions, demo polish, landing pages, presentation quality | `motion-ui-review`, `demo-interaction-designer` |
| `code-review` | Static review, refactoring, dependencies, tests, maintainability, bundle size, import boundaries | `bundle-bloat-review`, `import-boundary-review` |
| `content-portfolio` | Case studies, launch posts, recruiter-facing summaries, portfolio pages, social content | `portfolio-case-study-writer`, `linkedin-mini-series-planner` |
| `research-synthesis` | Comparing sources, researching tools, producing decision briefs, summarizing technical tradeoffs | `docs-crosscheck-reporter`, `competitive-workflow-analysis` |
| `maintenance` | Cleanup, migrations, catalog upkeep, naming normalization, repo housekeeping | `skill-catalog-maintainer`, `taxonomy-consistency-check` |

## Category selection rules

Choose the category by the skill's main reusable job.

Examples:

- A skill that reviews `package.json`, exports, build output, and npm metadata belongs in `npm-publishing`.
- A skill that improves README structure, demo links, and SEO snippets belongs in `docs-seo`.
- A skill that checks keyboard navigation and ARIA belongs in `frontend-a11y`.
- A skill that creates or reviews other skills belongs in `skill-authoring`.
- A skill that updates the repo catalog belongs in `maintenance`.

When a skill could fit multiple categories, choose the category that best matches the user's primary intent. Put the other concepts in `metadata.tags`.

## Naming rules

Skill names must:

- use lowercase letters, numbers, and hyphens only
- avoid spaces, underscores, uppercase letters, and double hyphens
- not start or end with a hyphen
- be specific enough to be useful in a catalog
- describe a reusable workflow

Preferred patterns:

```txt
<domain>-<task>
<target>-readiness
<artifact>-writer
<workflow>-planner
<subject>-review
<subject>-audit
<subject>-advisor
```

Good examples:

```txt
skill-brief-writer
release-readiness-review
github-pages-readiness
npm-publish-readiness
demo-index-docs-enhancer
jsonld-plugin-schema-advisor
bundle-bloat-review
baseline-support-check
```

Bad examples:

```txt
SkillForNpm
my cool seo thing
a11y--review
release_review
review
helper
```

## Tag rules

Use tags for search and secondary classification.

Good tags:

```txt
github-pages
npm
package-json
readme
seo
a11y
aria
keyboard
bundle-size
typescript
release
portfolio
```

Tags must:

- be lowercase
- use hyphens instead of spaces
- be specific but not overly clever
- avoid duplicates of the exact category unless useful for search

## Task types

Use one of these `metadata.task_type` values when possible:

| Type | Meaning |
|---|---|
| `review` | Inspects existing files and reports findings |
| `writer` | Produces new text, docs, examples, or copy |
| `planner` | Creates plans, checklists, roadmaps, or sequences |
| `generator` | Creates structured artifacts from inputs |
| `refactor` | Changes existing code or content structure |
| `maintenance` | Keeps catalogs, names, folders, or conventions clean |
| `research` | Compares sources and synthesizes conclusions |

## Status values

Use one of these `metadata.status` values:

| Status | Meaning |
|---|---|
| `draft` | Initial usable version, not heavily tested |
| `reviewed` | Checked against the review checklist |
| `stable` | Used successfully multiple times |
| `deprecated` | Kept for historical reference but no longer preferred |

New skills should usually start as `draft`.

## Side-effect values

Use one of these `metadata.side_effects` values:

| Value | Meaning |
|---|---|
| `none` | Review, planning, or advice only |
| `file-write` | Creates or edits local files |
| `command-run` | Runs local commands or scripts |
| `network` | Uses external web, registry, API, or package data |
| `external-side-effect` | Publishes, deploys, sends, deletes, or mutates a remote system |

Default to `none`. Require explicit user approval for `external-side-effect`.
