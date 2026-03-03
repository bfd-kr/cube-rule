# Cube Rule of Food Identification

A Claude Code plugin providing the Cube Rule of Food Identification as a skill. The cube rule classifies all foods by the position of structural starch relative to filling, using a cube model with 9 categories (0-8).

## Structure

- `.claude-plugin/plugin.json` - Plugin manifest
- `skills/cube-rule/SKILL.md` - The skill file (loaded when invoked)
- `docs/plans/` - Design and implementation documents

## Development

This is a pure markdown plugin - no build steps required.

**Test locally:** `claude plugins add .` from the repo root, then ask Claude a food classification question.

**Modify classifications:** Edit `skills/cube-rule/SKILL.md` directly. The classification table and special rules are all inline.
