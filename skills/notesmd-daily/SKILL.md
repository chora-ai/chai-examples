---
description: Create, read, and update daily notes.
capability_tier: minimal
variant_of: notesmd
metadata:
  requires:
    bins: ["notesmd-cli"]
---

## Skill Directives

- always use YYYY-MM-DD format for dates

## Composed Workflow: Create a Daily Note

1. Call `notesmd_daily_read` with `date` set to today. If the note exists, use `notesmd_daily_update` with `replace: false` to append instead.
2. Call `notesmd_daily_update` with `date`, `content`, and `replace` set to true.
3. Call `notesmd_daily_read` to verify the note was created correctly.
