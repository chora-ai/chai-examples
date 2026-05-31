# General Conventions

Cross-cutting conventions that apply to all note types. Type-specific conventions live in sibling files within this directory.

## Filenames

Notes use title case (e.g., `Sample Project.md`). Meta subdirectory files use lowercase (e.g., `general.md`, `daily.md`). Multi-word meta filenames use kebab-case.

## Wikilinks

All notes should wikilink references to existing notes. Cross-folder links use the path prefix: `[[path/Note Name|Note Name]]`. Within-folder links use bare links: `[[Note Name]]`.

In markdown tables, escape the pipe character in wikilinks with a backslash (`\|`) to prevent it from being interpreted as a column delimiter.

## Note References

When referencing a note in prose, include its type after the wikilink or name to make the reference self-describing. Examples: "the [[01-projects/Example|Example]] project note", "the Example inbox note".

For inbox notes, use the name without a wikilink (inbox notes are transient).

## Frontmatter Schema

- `type`: daily | meta | project
- `status`: active | exploring | paused | resolved | retired
- `role`: owner | contributor | member | participant
- `date`: ISO date (`YYYY-MM-DD`), used on daily notes
- `website`: Primary website URL
- `description`: One-line summary of the note's purpose
- `tags`: topic/domain only (not type or status)

### Status Definitions

| Status | Meaning |
|---|---|
| `active` | Currently doing the work |
| `exploring` | Actively investigating, deciding whether to commit |
| `paused` | Was active, intentionally stopped; may resume |
| `resolved` | Successfully completed or achieved its goal |
| `retired` | No longer relevant |

## Section Structure

All note types follow a header/body pattern. A horizontal rule (`---`) separates the header from body content. The separator appears only when body content exists.

## Templates

Templates live in `00-meta/templates/`. Templates define starting structure for new notes; conventions are the authority for section order and content rules when editing existing notes.
