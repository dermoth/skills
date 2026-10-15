---
name: managing-skills
description: "Records the user's preferences, rules and workflows as local skills in ~/DEV/skills, organized by topic, committing each change. Use whenever the user states a preference or standing rule (always/never/prefer...), corrects how the agent works, defines a style or standard, or asks to add, change or remove a skill."
---

# Managing local skills

The skills repository lives at `~/DEV/skills` (git, branch `main`) and is
symlinked to `~/.config/agents/skills` so Amp discovers it globally.

`global-AGENTS.md` is symlinked to `~/.config/amp/AGENTS.md`, which Amp
always loads. It lists each skill with its trigger so skills are loaded
proactively; add, update or remove its entry whenever a skill is created,
renamed, re-scoped or deleted.

## Layout

* One skill directory per topic (`writing-commits/`, `formatting-code/`, ...).
  Directory name == frontmatter `name`, gerund form, lowercase-hyphenated.
* `SKILL.md` holds the core rules (keep it short, well under 500 lines).
* Sub-topics that are only needed sometimes go in `reference/<subtopic>.md`
  and are linked from `SKILL.md` (e.g. one file per language).
* The `description` must say what the skill covers AND when to use it; it is
  the only part always in context, so make the triggers specific.

## Workflow

1. When the user gives input that is a reusable preference, rule or workflow
   (not a one-off instruction for the current task), capture it.
2. Find the existing topic skill it belongs to; extend it rather than creating
   a new one. Create a new skill only for a genuinely new topic. Split a skill
   when it grows to cover unrelated topics.
3. Record the rule in the user's intent, concise and actionable. Keep the
   reason when one was given. Remove or rewrite rules that the new input
   supersedes instead of leaving contradictions.
4. Commit in `~/DEV/skills` following the `writing-commits` skill, one commit
   per logical change.
5. Run `reload_skills` so the current session picks up the change.
6. **Always mention it in the chat output**: which skill/file was created or
   updated, a one-line summary of the change, and the commit.

Ask before deleting a skill or removing a rule the user did not explicitly
retract. Never push; the repository has no remote unless the user adds one.
