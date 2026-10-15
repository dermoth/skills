# Local agent skills

Personal agent skills, one directory per topic. Each directory holds a
`SKILL.md` (frontmatter `name` must match the directory name) and optional
topic files under `reference/`.

Amp discovers these through the symlink:

    ~/.config/agents/skills -> ~/DEV/skills

`global-AGENTS.md` is always-loaded guidance that tells the agent when to
load each skill:

    ~/.config/amp/AGENTS.md -> ~/DEV/skills/global-AGENTS.md

See `managing-skills/SKILL.md` for how skills are added and maintained.
