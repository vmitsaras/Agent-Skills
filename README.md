# Agent Skills Library

A portable GitHub library for reusable Agent Skills.

This repo is designed for a workflow where ChatGPT helps brainstorm and author skills, while Codex creates folders, writes files, updates catalogs, and keeps the repository organized.

## What this repo is

This repository is a **source library** of skills.

Skills here are meant to be:

- browsed on GitHub
- copied into another project
- downloaded as reusable packages
- adapted for local agent environments
- maintained with taxonomy and catalog metadata

## What this repo is not

This repository is not primarily a live Codex runtime skill folder.

The source path is:

```txt
skills/<category>/<skill-name>/SKILL.md
```

Do not treat `.agents/skills/` as the source location for this library. That path may be used later only as an optional installation/export destination.

## Repository structure

```txt
.
├─ AGENTS.md
├─ CHATGPT_PROJECT_INSTRUCTIONS.md
├─ README.md
├─ catalog/
│  ├─ skills.json
│  └─ taxonomy.json
├─ docs/
│  ├─ PROJECT_SOURCE.md
│  ├─ TAXONOMY.md
│  ├─ AUTHORING_GUIDE.md
│  ├─ CODEX_WORKFLOW.md
│  ├─ REVIEW_CHECKLIST.md
│  ├─ EXPORT_INSTALL_GUIDE.md
│  └─ CATALOG_SCHEMA.md
├─ templates/
│  ├─ SKILL_TEMPLATE.md
│  ├─ SKILL_BRIEF_TEMPLATE.md
│  └─ CODEX_CREATE_SKILL_PROMPT.md
└─ skills/
   └─ <category>/
      └─ <skill-name>/
         └─ SKILL.md
```

## Skill package shape

Each skill is a folder with a required `SKILL.md` file.

Optional support folders may be added when useful:

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

## Taxonomy

Primary categories:

| Category | Use for |
|---|---|
| `skill-authoring` | Creating, refining, reviewing, and maintaining skills |
| `project-planning` | Roadmaps, implementation plans, milestones, and task breakdowns |
| `repo-readiness` | GitHub, release, CI, project structure, and public repo readiness |
| `npm-publishing` | npm package metadata, build output, exports, types, and release checks |
| `docs-seo` | README, documentation, demos, metadata, structured data, and discoverability |
| `frontend-a11y` | Accessibility, ARIA, semantic HTML, keyboard UX, and WCAG-style checks |
| `ui-ux-polish` | Visual polish, motion, interaction quality, and demo presentation |
| `code-review` | Static review, refactoring, dependency checks, tests, and maintainability |
| `content-portfolio` | Case studies, recruiter-facing content, launch content, and social posts |
| `research-synthesis` | Source comparison, technical research, and decision briefs |
| `maintenance` | Cleanup, migration, catalog upkeep, and miscellaneous repo care |

## Skill navigation

| Skill | Category | Type | Summary |
|---|---|---|---|

<<<<<<< ours
| [ui-design-direction-builder](skills/ui-ux-polish/ui-design-direction-builder/SKILL.md) | ui-ux-polish | planner | Builds a coherent, implementation-ready visual and interaction direction for a web interface. |
=======
| [interface-state-coverage-review](skills/ui-ux-polish/interface-state-coverage-review/SKILL.md) | ui-ux-polish | review | Reviews interfaces and user flows for missing, inconsistent, or poorly communicated states. |

>>>>>>> theirs
<!-- Add skills here. Keep rows sorted alphabetically by skill name. -->

## Creating a new skill

1. Draft the skill idea with ChatGPT.
2. Confirm the name, category, trigger description, and target path.
3. Ask Codex to create the skill package under:

   ```txt
   skills/<category>/<skill-name>/SKILL.md
   ```

4. Codex updates:

   ```txt
   catalog/skills.json
   README.md
   docs/TAXONOMY.md, if needed
   ```

5. Review the result with `docs/REVIEW_CHECKLIST.md`.

## Installing or copying a skill elsewhere

Copy the skill folder from:

```txt
skills/<category>/<skill-name>/
```

into the target agent environment expected by the consumer.

For example, a user may copy:

```txt
skills/repo-readiness/github-pages-readiness/
```

into a local skills directory supported by their agent tooling.

See `docs/EXPORT_INSTALL_GUIDE.md` for details.

## Authoring standards

A good skill:

- has one clear job
- has a specific trigger description
- names the files or inputs it inspects
- uses a step-by-step workflow
- declares side effects
- returns predictable output
- can be reused outside this repository

## License

MIT, unless a specific skill says otherwise.
