---
description: Create, read, search, update, and delete notes.
capability_tier: moderate
metadata:
  requires:
    bins: ["notesmd-cli"]
---

## Skill Directives

- always read a note before updating it to avoid overwriting content
- always confirm before deleting a note

## Composed Workflow: Create or Update a Note

1. Call `notesmd_list` to verify the target directory exists.
2. Call `notesmd_create` with `path`, `content` (including YAML frontmatter), and `replace` set to true.
3. Call `notesmd_read` to verify the note was created correctly.

For appending to an existing note, call `notesmd_create` with `replace` set to false.
