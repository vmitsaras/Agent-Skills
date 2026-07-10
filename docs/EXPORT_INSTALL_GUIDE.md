# Export and Install Guide

This repository stores source copies of skills.

Source skills live here:

```txt
skills/<category>/<skill-name>/SKILL.md
```

A user may later copy a finished skill package into an agent environment that supports skills.

## Source versus install target

Source path in this repository:

```txt
skills/repo-readiness/github-pages-readiness/SKILL.md
```

Possible copied package shape:

```txt
github-pages-readiness/
└─ SKILL.md
```

The exact install destination depends on the user's agent tooling.

For Codex-style local skills, a user may copy the skill folder into a supported local or project skills directory. This repository should still keep its own source copy under `skills/<category>/`.

## Exporting a single skill

To export one skill manually:

1. Locate the source package:

   ```txt
   skills/<category>/<skill-name>/
   ```

2. Copy the entire folder, not only `SKILL.md`.
3. Preserve optional folders if they exist:

   ```txt
   references/
   scripts/
   assets/
   agents/
   ```

4. Place the copied folder in the target environment.
5. Verify the target environment can see the skill.

## Example manual copy

Source:

```txt
skills/repo-readiness/github-pages-readiness/
├─ SKILL.md
└─ references/
   └─ deployment-checklist.md
```

Copied package:

```txt
github-pages-readiness/
├─ SKILL.md
└─ references/
   └─ deployment-checklist.md
```

## Do not flatten packages

Do not export a skill as a loose file:

```txt
github-pages-readiness.md
```

Use the folder package shape:

```txt
github-pages-readiness/SKILL.md
```

## Export checklist

Before publishing or sharing a skill package:

- [ ] The folder name matches frontmatter `name`.
- [ ] `SKILL.md` exists at the package root.
- [ ] Optional support folders are included.
- [ ] The skill does not contain private paths, secrets, or credentials.
- [ ] The skill declares side effects.
- [ ] The skill license is clear.
- [ ] The source repository catalog entry is up to date.

## Installation note for README snippets

Use wording like this when documenting install instructions:

```md
Copy the skill package from `skills/<category>/<skill-name>/` into the skills directory supported by your agent environment. Keep the folder name and `SKILL.md` file intact.
```

Avoid wording that implies this repository's source path is itself the user's runtime install path.
