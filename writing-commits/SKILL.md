---
name: writing-commits
description: "The user's rules for git commits: message content, commit granularity, and splitting complex work into reviewable commits. Use whenever committing, staging, or planning changes in any git repository."
---

# Writing commits

## Messages

- Always write a meaningful message; concise. A single line is fine for
  something very trivial.
- Emphasize the change being made, plus technical details not apparent from
  the code: why an approach was taken, or why an alternative was avoided.
- Don't narrate the diff line by line.

## Granularity

- Each commit is limited to one minimal feature or change.
- Multiple trivial changes may be bundled (typos, minor reformats).
- Complex features are split into multiple commits that can each be reviewed
  and tested on their own (each commit should build/pass).
- Reformatting is always its own commit, separate from functional changes
  (see the `formatting-code` skill).
