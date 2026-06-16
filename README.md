# chai-examples

Example profiles and skills for [chai](https://github.com/chora-ai/chai).

## Profiles

Example profile configurations demonstrating agent setup patterns.

| Profile | Description |
|---|---|
| `assistant` | Example profile for knowledge base work |
| `developer` | Example profile for software development |
| `skillsmith` | Example profile for building chai skills |

### Installation

Copy a profile directory to `~/.chai/profiles/`:

```sh
cp -r profiles/assistant ~/.chai/profiles/
```

## Skills

Example skill packages that demonstrate CLI-backed skill design, compound subcommands, and `resolveCommand` patterns. These skills are not bundled with Chai because they depend on external binaries or deployment infrastructure not available by default.

| Skill | Tools | Tier | Depends On |
|---|---|---|---|
| `notesmd` | 7 | moderate | `notesmd-cli` |
| `notesmd-daily` | 2 | minimal | `notesmd-cli` |
| `websearch` | 2 | full | SearXNG instance |

### Installation

Copy a skill directory to `~/.chai/skills/`:

```sh
cp -r skills/websearch ~/.chai/skills/
```

Then enable the skill in your profile's `skillsEnabled` list.

### Bundled Variants

The bundled `kb-*` skill family provides equivalent functionality with sandbox enforcement:

| Example Skill | Bundled Replacement |
|---|---|
| `notesmd` | `kb`, `kb-frontmatter`, `kb-wikilink` |
| `notesmd-daily` | `kb-daily` |
