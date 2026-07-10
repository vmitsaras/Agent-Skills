# Codex Create Skill Prompt

Copy this prompt into Codex when creating a new skill from a ChatGPT-generated brief.

```txt
Create a new portable Agent Skill in this repository.

Skill name:
<skill-name>

Category:
<category>

Target path:
skills/<category>/<skill-name>/SKILL.md

Skill brief:
<brief>

Complete SKILL.md content:
<paste full content here>

Catalog entry:
<paste JSON object here>

README row:
<paste markdown table row here>

Repository rules:
- This repo is a portable source library of Agent Skills.
- Use skills/<category>/<skill-name>/SKILL.md as the source path.
- Do not create the source skill under .agents/skills/.
- Create the skill folder if missing.
- Write the complete SKILL.md file.
- Add optional references/, scripts/, assets/, or agents/ only if the provided skill content requires them.
- Update catalog/skills.json.
- Update README.md navigation.
- Keep catalog entries sorted alphabetically by name.
- Keep README rows sorted alphabetically by skill name.
- Validate that folder name, frontmatter name, catalog entry, and README link all match.
- Report the files changed and validation results.
```

## Minimal variant

Use this when Codex should draft the skill from only an idea:

```txt
Create a new portable Agent Skill from this idea:

<skill idea>

Follow repository rules:
- Read AGENTS.md and docs/PROJECT_SOURCE.md first.
- Use skills/<category>/<skill-name>/SKILL.md as the source path.
- Choose the best existing category from docs/TAXONOMY.md.
- Use lowercase hyphenated naming.
- Write a complete SKILL.md with valid frontmatter.
- Update catalog/skills.json.
- Update README.md.
- Do not place the source skill in .agents/skills/.
- Run the consistency checklist before finishing.
```

## Update existing skill variant

```txt
Update the existing skill:

<skill-name>

Requested changes:
<changes>

Rules:
- Keep the source path under skills/<category>/<skill-name>/SKILL.md.
- Do not move it to .agents/skills/.
- Preserve the skill's narrow purpose unless the requested change explicitly changes scope.
- Update frontmatter if needed.
- Update catalog/skills.json if metadata changed.
- Update README.md if the summary, path, or category changed.
- Validate consistency before finishing.
```
