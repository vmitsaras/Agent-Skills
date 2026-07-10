# Review Checklist

Use this checklist before accepting a new or updated skill.

## Path and package shape

- [ ] The skill is stored under `skills/<category>/<skill-name>/SKILL.md`.
- [ ] The skill is not stored as a loose markdown file.
- [ ] The skill is not placed under `.agents/skills/` as the source copy.
- [ ] Optional folders are used only when useful:
  - [ ] `references/`
  - [ ] `scripts/`
  - [ ] `assets/`
  - [ ] `agents/`

## Naming

- [ ] The skill name uses lowercase letters, numbers, and hyphens only.
- [ ] The name contains no spaces.
- [ ] The name contains no underscores.
- [ ] The name contains no uppercase letters.
- [ ] The name contains no double hyphens.
- [ ] The name does not start or end with a hyphen.
- [ ] The folder name matches the frontmatter `name` exactly.

## Taxonomy

- [ ] The category folder exists in `docs/TAXONOMY.md`.
- [ ] `metadata.category` matches the category folder.
- [ ] The skill has one primary category.
- [ ] Secondary concepts are represented as tags, not nested folders.
- [ ] Tags are lowercase and hyphenated.

## Frontmatter

- [ ] Frontmatter exists at the top of `SKILL.md`.
- [ ] `name` is present.
- [ ] `description` is present.
- [ ] `license` is present.
- [ ] `compatibility` is present.
- [ ] `metadata.category` is present.
- [ ] `metadata.task_type` is present.
- [ ] `metadata.audience` is present.
- [ ] `metadata.tags` is present.
- [ ] `metadata.status` is present.
- [ ] `metadata.side_effects` is present.

## Description quality

- [ ] The description starts with the main action.
- [ ] The description names the artifact or workflow.
- [ ] The description says when to use the skill.
- [ ] The description includes likely user trigger phrases.
- [ ] The description is not vague.
- [ ] The description is not just “helps with X.”

## Body structure

- [ ] The skill has a clear title.
- [ ] The skill has a `Purpose` section.
- [ ] The skill has a `When to use this skill` section.
- [ ] The skill has positive use cases.
- [ ] The skill has negative use cases.
- [ ] The skill has an `Inputs to inspect` section.
- [ ] The skill has a step-by-step `Workflow` section.
- [ ] The skill has an explicit `Output format` section.
- [ ] The skill has a `Quality bar` section.
- [ ] The skill has an `Edge cases` section.
- [ ] The skill has a `Related skills` section or explicitly says none.

## Workflow quality

- [ ] The workflow is specific enough to execute.
- [ ] The workflow avoids vague steps like “make it better.”
- [ ] The workflow starts by inspecting the minimum useful inputs.
- [ ] The workflow prioritizes blockers before nice-to-have improvements.
- [ ] The workflow tells the agent what to return.
- [ ] The workflow does not require unavailable tools unless declared.

## Portability

- [ ] The skill does not depend on private user context.
- [ ] The skill does not include secrets or credentials.
- [ ] The skill does not assume one specific machine path.
- [ ] The skill can be copied into another environment.
- [ ] Any tool requirements are stated clearly.

## Side effects and safety

- [ ] Side effects are declared accurately.
- [ ] Review-only skills use `side_effects: none`.
- [ ] File-writing skills use `side_effects: file-write`.
- [ ] Command-running skills use `side_effects: command-run`.
- [ ] Network-dependent skills use `side_effects: network`.
- [ ] Publishing, deployment, deletion, sending, or remote mutation skills use `side_effects: external-side-effect`.
- [ ] External side effects require explicit user approval.

## Catalog and navigation

- [ ] `catalog/skills.json` contains an entry for the skill.
- [ ] The catalog path matches the actual file path.
- [ ] The catalog category matches the frontmatter category.
- [ ] The catalog tags match or reasonably summarize the frontmatter tags.
- [ ] The README navigation table contains the skill.
- [ ] The README link points to the actual `SKILL.md`.
- [ ] Catalog entries are sorted alphabetically by skill name.
- [ ] README rows are sorted alphabetically by skill name.

## Support files

- [ ] Long examples are moved to `references/` when needed.
- [ ] Scripts are present only if they improve repeatability.
- [ ] Scripts include clear usage instructions.
- [ ] Assets are named clearly.
- [ ] Support files are referenced from `SKILL.md`.

## Final acceptance

A skill is ready when:

- [ ] It has one clear reusable purpose.
- [ ] It follows the repository source layout.
- [ ] It has valid frontmatter.
- [ ] It belongs to the right taxonomy category.
- [ ] It has a strong trigger description.
- [ ] It has a concrete workflow.
- [ ] It has predictable output.
- [ ] It declares side effects.
- [ ] It is listed in the catalog.
- [ ] It is linked in the README.
