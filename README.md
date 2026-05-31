# chai-examples

Example profiles and skills for [chai](https://github.com/chora-ai/chai).

## Profiles

Example profile configurations demonstrating agent setup patterns.

| Profile | Description |
|---|---|
| `assistant` | Personal assistant with knowledge base, web search, and daily notes |

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
| `notesmd-daily` | 2 | minimal | `notesmd-cli`, `.obsidian/daily-notes.json` |
| `obsidian` | 0 | — | Obsidian CLI (not available) |
| `obsidian-daily` | 0 | — | Obsidian CLI (not available) |
| `websearch` | 2 | full | SearXNG instance |

### Installation

Copy a skill directory to `~/.chai/skills/`:

```sh
cp -r skills/websearch ~/.chai/skills/
```

Then enable the skill in your profile's `skillsEnabled` list.

### Bundled Replacements

The bundled `kb-*` skill family provides equivalent functionality with sandbox enforcement and no external binary dependencies:

| Example Skill | Bundled Replacement |
|---|---|
| `notesmd` | `kb`, `kb-frontmatter` |
| `notesmd-daily` | `kb-daily` |
| `obsidian` / `obsidian-daily` | `kb`, `kb-daily` |
