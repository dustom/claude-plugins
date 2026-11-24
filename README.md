# Claude plugins

My plugins and skills for [Claude Code](https://claude.com/claude-code), published as a plugin marketplace.

## Install

In Claude Code:

```
/plugin marketplace add dustom/claude-plugins
/plugin install cycling-inspiration@dustom
```

Or from a terminal:

```bash
claude plugin marketplace add dustom/claude-plugins
claude plugin install cycling-inspiration@dustom
```

## Plugins

| Plugin | What it does |
|---|---|
| [cycling-inspiration](plugins/cycling-inspiration) | Turns a GPX file and ride photos into a bilingual (CZ/EN) route page for the Cycling Inspiration site. |

## Layout

```
.claude-plugin/marketplace.json   the catalogue Claude Code reads
plugins/<plugin>/                 one folder per plugin
  .claude-plugin/plugin.json      name, version, description
  skills/<skill>/SKILL.md         the skills it ships
  commands/ agents/ hooks/        optional, when a plugin needs them
templates/plugin/                 copy this to start a new plugin
```

## Adding a plugin or skill

1. Copy `templates/plugin` to `plugins/<new-name>` and rename `my-plugin` and `my-skill`.
2. Write the skill in `skills/<skill>/SKILL.md`. The `description` decides when Claude uses it, so say what it does and when.
3. Add the plugin to `plugins` in `.claude-plugin/marketplace.json`.
4. Check it with `claude plugin validate .`, then commit and push.
5. Update on another machine with `/plugin marketplace update dustom`.

To add a skill to an existing plugin, put a new `skills/<skill>/SKILL.md` folder in it and bump the plugin's `version`.
