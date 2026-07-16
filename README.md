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
| [accessibility-validation-planner](skills/frontend-a11y/accessibility-validation-planner/SKILL.md) | frontend-a11y | planner | Plans accessibility validation across semantic, keyboard, focus, screen-reader, zoom, contrast, motion, and automated checks. |
| [agent-workstream-planner](skills/project-planning/agent-workstream-planner/SKILL.md) | project-planning | planner | Divides a project into coordinated workstreams with explicit ownership, dependencies, handoffs, collision controls, and integration checkpoints. |
| [architecture-decision-planner](skills/project-planning/architecture-decision-planner/SKILL.md) | project-planning | planner | Identifies pre-implementation architecture decisions and prepares alternatives, trade-offs, criteria, evidence needs, owners, and deadlines. |
| [constraint-mapper](skills/project-planning/constraint-mapper/SKILL.md) | project-planning | planner | Maps technical, time, budget, platform, accessibility, privacy, and maintenance constraints to concrete planning decisions. |
| [data-model-planner](skills/project-planning/data-model-planner/SKILL.md) | project-planning | planner | Plans entities, relationships, validation, ownership, lifecycle, and migration concerns without generating implementation code. |
| [docs-discoverability-audit](skills/docs-seo/docs-discoverability-audit/SKILL.md) | docs-seo | review | Audits technical documentation for navigation, information architecture, internal linking, content findability, duplication, and technical SEO. |
| [edge-case-test-planner](skills/project-planning/edge-case-test-planner/SKILL.md) | project-planning | planner | Identifies unusual states, malformed inputs, race conditions, lifecycle problems, and recovery scenarios for targeted test planning. |
| [feature-priority-planner](skills/project-planning/feature-priority-planner/SKILL.md) | project-planning | planner | Ranks proposed features by user value, implementation cost, dependency impact, risk, and portfolio value. |
| [implementation-checkpoint-planner](skills/project-planning/implementation-checkpoint-planner/SKILL.md) | project-planning | planner | Adds evidence-based review checkpoints after risky or foundational work before dependent tasks proceed. |
| [implementation-order-planner](skills/project-planning/implementation-order-planner/SKILL.md) | project-planning | planner | Determines what should be built first using dependencies, uncertainty, integration risk, and validation value. |
| [implementation-plan-writer](skills/project-planning/implementation-plan-writer/SKILL.md) | project-planning | planner | Turns requirements and architecture decisions into an ordered implementation plan without writing code. |
| [interface-state-coverage-review](skills/ui-ux-polish/interface-state-coverage-review/SKILL.md) | ui-ux-polish | review | Reviews interfaces and user flows for missing, inconsistent, or poorly communicated states. |
| [layout-art-direction](skills/ui-ux-polish/layout-art-direction/SKILL.md) | ui-ux-polish | review | Reviews or develops intentional graphic layout and art direction using hierarchy, composition, rhythm, typography, imagery, and responsive behavior. |
| [milestone-planner](skills/project-planning/milestone-planner/SKILL.md) | project-planning | planner | Groups work into meaningful milestones with entry criteria, completion criteria, risks, dependencies, and expected outcomes. |
| [motion-behavior-planner](skills/ui-ux-polish/motion-behavior-planner/SKILL.md) | ui-ux-polish | planner | Plans purposeful UI motion behavior including intent, triggers, timing relationships, interruption, reduced motion, and performance boundaries. |
| [mvp-scope-planner](skills/project-planning/mvp-scope-planner/SKILL.md) | project-planning | planner | Defines the smallest coherent MVP scope with explicit inclusions, exclusions, validation criteria, tradeoffs, and follow-on triggers. |
| [phase-boundary-planner](skills/project-planning/phase-boundary-planner/SKILL.md) | project-planning | planner | Defines where project phases should end and begin using exit criteria, entry criteria, evidence, handoffs, dependencies, risks, and go/no-go gates. |
| [plan-to-issues-converter](skills/project-planning/plan-to-issues-converter/SKILL.md) | project-planning | generator | Converts roadmap tasks into GitHub-issue-ready drafts with labels, dependencies, acceptance criteria, and definitions of done. |
| [portfolio-project-planner](skills/project-planning/portfolio-project-planner/SKILL.md) | project-planning | planner | Plans portfolio-oriented projects so implementation, documentation, screenshots, demos, architecture reasoning, and case-study evidence develop together. |
| [problem-validation-planner](skills/project-planning/problem-validation-planner/SKILL.md) | project-planning | planner | Plans how to verify that a proposed problem is real, important, frequent, and worth solving before implementation begins. |
| [progressive-enhancement-planner](skills/project-planning/progressive-enhancement-planner/SKILL.md) | project-planning | planner | Defines baseline HTML, enhanced JavaScript behavior, failure recovery, and accessibility requirements for resilient web features. |
| [project-brief-builder](skills/project-planning/project-brief-builder/SKILL.md) | project-planning | generator | Converts a rough project idea into a structured brief with goals, users, constraints, success criteria, assumptions, and exclusions. |
| [project-concept-planner](skills/project-planning/project-concept-planner/SKILL.md) | project-planning | planner | Turns an undeveloped idea into a concrete project concept with a target user, core problem, value proposition, and initial boundaries. |
| [project-plan-reconciler](skills/project-planning/project-plan-reconciler/SKILL.md) | project-planning | review | Reconciles project plans with repository progress and produces a corrected execution sequence. |
| [project-roadmap-builder](skills/project-planning/project-roadmap-builder/SKILL.md) | project-planning | planner | Produces a phased project roadmap with goals, deliverables, dependencies, acceptance criteria, risks, and checkpoints. |
| [project-status-snapshot](skills/project-planning/project-status-snapshot/SKILL.md) | project-planning | generator | Summarizes completed work, current state, blockers, decisions, next tasks, and deviations from the original plan. |
| [refactor-roadmap-builder](skills/project-planning/refactor-roadmap-builder/SKILL.md) | project-planning | planner | Breaks a large refactor into behavior-preserving stages with tests, compatibility checkpoints, and rollback boundaries. |
| [repo-next-steps-review](skills/repo-readiness/repo-next-steps-review/SKILL.md) | repo-readiness | review | Reviews a repository's current state and recommends prioritized next steps. |
| [repo-public-profile-polish](skills/repo-readiness/repo-public-profile-polish/SKILL.md) | repo-readiness | review | Reviews a public repository's README, metadata, screenshots, demo links, and overall first-impression quality. |
| [repository-area-impact-planner](skills/project-planning/repository-area-impact-planner/SKILL.md) | project-planning | planner | Identifies likely affected files, modules, APIs, tests, examples, documentation, configuration, and validation areas for a proposed repository change. |
| [repository-feature-plan](skills/project-planning/repository-feature-plan/SKILL.md) | project-planning | planner | Plans how a proposed feature should fit into an existing repository's architecture, conventions, tests, documentation, examples, and demo surface. |
| [requirements-gap-finder](skills/project-planning/requirements-gap-finder/SKILL.md) | project-planning | review | Reviews project briefs for missing requirements, unresolved decisions, contradictions, hidden assumptions, and vague acceptance criteria. |
| [responsive-behavior-planner](skills/ui-ux-polish/responsive-behavior-planner/SKILL.md) | ui-ux-polish | planner | Defines how layout, controls, content priority, and interactions adapt across available space. |
| [scope-creep-guard](skills/project-planning/scope-creep-guard/SKILL.md) | project-planning | review | Reviews proposed additions against the project goal and classifies them as required, justified, deferred, or rejected. |
| [skill-quality-audit](skills/skill-authoring/skill-quality-audit/SKILL.md) | skill-authoring | review | Audits an Agent Skill for routing clarity, scope, executability, safety, portability, and repository consistency. |
| [task-context-packager](skills/project-planning/task-context-packager/SKILL.md) | project-planning | generator | Creates the minimum evidence-backed context package an agent needs to complete one repository task. |
| [task-dependency-mapper](skills/project-planning/task-dependency-mapper/SKILL.md) | project-planning | planner | Builds a task dependency graph and detects blockers, cycles, unnecessary coupling, and safe parallel work. |
| [ui-design-direction-builder](skills/ui-ux-polish/ui-design-direction-builder/SKILL.md) | ui-ux-polish | planner | Builds a coherent, implementation-ready visual and interaction direction for a web interface. |
| [user-flow-planner](skills/project-planning/user-flow-planner/SKILL.md) | project-planning | planner | Converts features into primary, secondary, failure, empty, loading, and recovery user flows before implementation. |
| [user-recovery-flow-planner](skills/project-planning/user-recovery-flow-planner/SKILL.md) | project-planning | planner | Plans recovery paths for user mistakes, invalid input, failed requests, expired sessions, interrupted workflows, and uncertain outcomes. |
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
