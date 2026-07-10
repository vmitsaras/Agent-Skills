# Codex Workflow

This file defines how Codex should automate work in the Agent Skills library.

## Role of Codex

Codex is the repository automation worker.

Codex should:

- create folders
- write `SKILL.md` files
- update catalog files
- update README navigation
- keep taxonomy consistent
- perform consistency checks

Codex should not decide a totally new repository philosophy unless asked. The source layout is already defined.

## Source layout

Use this for every source skill:

```txt
skills/<category>/<skill-name>/SKILL.md
```

Never use `.agents/skills/` as the source location for this repository.

## Creating a new skill

When asked to create a new skill, Codex should perform this sequence:

1. Read repository guidance:

   ```txt
   AGENTS.md
   docs/PROJECT_SOURCE.md
   docs/TAXONOMY.md
   docs/AUTHORING_GUIDE.md
   templates/SKILL_TEMPLATE.md
   ```

2. Determine:

   ```txt
   skill name
   category
   target path
   task type
   tags
   side effects
   summary
   ```

3. Create the folder:

   ```txt
   skills/<category>/<skill-name>/
   ```

4. Create:

   ```txt
   skills/<category>/<skill-name>/SKILL.md
   ```

5. Add optional support folders only when useful:

   ```txt
   references/
   scripts/
   assets/
   agents/
   ```

6. Update:

   ```txt
   catalog/skills.json
   README.md
   ```

7. Update only if needed:

   ```txt
   docs/TAXONOMY.md
   catalog/taxonomy.json
   ```

8. Run consistency checks.

## Create-skill prompt template

Use this prompt when asking Codex to create a skill:

```txt
Create a new portable Agent Skill in this repository.

Skill idea:
<describe the skill>

Requirements:
- Use the source layout skills/<category>/<skill-name>/SKILL.md.
- Do not place the source skill in .agents/skills/.
- Choose the best existing taxonomy category from docs/TAXONOMY.md.
- Use lowercase hyphenated naming.
- Write a complete SKILL.md with frontmatter and standard sections.
- Update catalog/skills.json.
- Update the README skill navigation table.
- Keep catalog entries and README rows sorted alphabetically by skill name.
- Add references/, scripts/, assets/, or agents/ only if useful.
- Run the consistency checklist before finishing.
```

## Updating an existing skill

When asked to update a skill:

1. Locate the skill by name in:

   ```txt
   skills/<category>/<skill-name>/SKILL.md
   catalog/skills.json
   README.md
   ```

2. Read the current skill before editing.
3. Keep the original purpose unless the user asks for a redesign.
4. Update frontmatter, body, support files, catalog, and README if needed.
5. Preserve portability.
6. Run the review checklist.

## Update-skill prompt template

```txt
Update the existing skill named <skill-name>.

Goals:
<describe requested changes>

Rules:
- Keep the source skill under skills/<category>/<skill-name>/SKILL.md.
- Do not move it to .agents/skills/.
- Preserve the existing skill purpose unless the request clearly changes it.
- Update frontmatter if category, tags, status, side effects, or description changed.
- Update catalog/skills.json.
- Update README.md if the summary, category, or path changed.
- Keep entries sorted alphabetically.
- Run the consistency checklist before finishing.
```

## Renaming a skill

Renaming requires more care than editing.

Codex must:

1. Create the new path.
2. Move or rewrite `SKILL.md`.
3. Ensure frontmatter `name` matches the new folder.
4. Update `catalog/skills.json`.
5. Update `README.md` links.
6. Search the repo for references to the old name.
7. Add a migration note if the old skill was likely used externally.

## Renaming prompt template

```txt
Rename the skill <old-skill-name> to <new-skill-name>.

Rules:
- Keep the skill in the correct taxonomy folder under skills/.
- Update the SKILL.md frontmatter name.
- Update catalog/skills.json.
- Update README.md navigation links.
- Search for old-name references and update them where appropriate.
- Do not create a duplicate stale skill unless a deprecation stub is explicitly requested.
```

## Bulk cleanup workflow

Use this workflow for repo-wide cleanup:

1. Inspect all files under `skills/`.
2. Check names, categories, frontmatter, paths, catalog entries, and README rows.
3. Report mismatches before changing files if changes are broad.
4. Apply small, obvious fixes directly.
5. Avoid semantic rewrites unless requested.

## Bulk cleanup prompt template

```txt
Audit this Agent Skills library for consistency.

Check:
- every skill is under skills/<category>/<skill-name>/SKILL.md
- every SKILL.md has valid frontmatter
- frontmatter name matches folder name
- frontmatter category matches category folder
- every skill appears in catalog/skills.json
- every skill appears in the README navigation table
- catalog and README entries are sorted alphabetically
- no source skills exist under .agents/skills/

Make safe fixes. Report anything ambiguous instead of guessing.
```

## Suggested consistency commands

Use shell commands only when appropriate for the repo and environment.

Examples:

```bash
find skills -name SKILL.md | sort
find skills -maxdepth 3 -type f | sort
find . -path './.agents/skills/*' -print
```

Potential JSON validation:

```bash
python -m json.tool catalog/skills.json > /tmp/skills.json.checked
python -m json.tool catalog/taxonomy.json > /tmp/taxonomy.json.checked
```

Potential frontmatter/name check can be done manually or with a small script if the repo grows.

## Completion report

After Codex creates or updates a skill, it should summarize:

```md
## Summary

- Created/updated: ...

## Files changed

- ...

## Catalog/navigation

- Updated catalog: yes/no
- Updated README: yes/no

## Validation

- [x] Path uses skills/<category>/<skill-name>/SKILL.md
- [x] Frontmatter name matches folder
- [x] Category matches taxonomy
- [x] Catalog entry exists
- [x] README row exists

## Notes

- ...
```
