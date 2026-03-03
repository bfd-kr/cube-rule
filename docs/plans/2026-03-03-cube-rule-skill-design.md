# Cube Rule Skill Design

## Overview

A Claude Code plugin that provides the Cube Rule of Food Identification as a skill. The cube rule classifies all foods based on the position of structural starch (carbohydrate) relative to the filling, using the six faces of a cube as a model.

Based on the original work by @Phosphatide at https://cuberule.com/

## Decisions

- **Format:** Claude Code plugin with `.claude-plugin/plugin.json` manifest
- **Skill structure:** Single self-contained `skills/cube-rule/SKILL.md` with inline lookup table
- **Scope:** Food classification + absurdist edge cases (humans as ravioli, etc.)
- **Tone:** No enforced tone - let Claude adapt naturally to conversation context
- **License:** Unlicense (public domain)

## Repo Structure

```
cube-rule/
  .claude-plugin/
    plugin.json
  skills/
    cube-rule/
      SKILL.md
  CLAUDE.md
  README.md
  LICENSE
  docs/
    plans/
```

## SKILL.md Content

### Frontmatter

- name: `cube-rule`
- description: Triggers on food classification questions, food identity debates, "what is X" food questions

### Body Sections

1. **Overview** - One paragraph explaining the cube rule concept
2. **Classification System** - Compact table with 9 categories (0-8), starch positions, and examples
3. **Classification Method** - Brief procedure: identify starch → determine cube faces → match category
4. **Special Rules** - Rice interpretation, vanilla soy latte, muffins/bread blocks
5. **Usage** - Classify, explain reasoning, provide category number and name

### Categories

| # | Category | Starch Position | Examples |
|---|----------|----------------|----------|
| 0 | Salad | No structural starch | Steak, soup, mashed potatoes, chocolate, flan |
| 1 | Toast | Bottom only | Pizza, nigiri sushi, pie slice |
| 2 | Sandwich | Top + bottom | Quesadilla, victoria sponge, toast sandwich |
| 3 | Taco | Bottom + two sides | Hot dog, sub sandwich (uncut) |
| 4 | Sushi | Bottom + top + two sides | Falafel wrap, pigs in a blanket, enchilada |
| 5 | Quiche | Bottom + four sides (open top) | Cheesecake, bread bowl soup, falafel pita |
| 6 | Calzone | All six sides | Burrito, corn dog, dumpling, pop-tart, uncrustables |
| 7 | Cake | Three stacked starch layers | Lasagna, Big Mac, flapjacks |
| 8 | Nachos | Smaller starch pieces within | Poutine, Lucky Charms, ramen, couscous |

## README.md

- What the cube rule is
- Installation via `claude plugins add`
- Usage instructions
- Attribution to @Phosphatide and cuberule.com
- Unlicense notice

## CLAUDE.md

- Project description
- Development/testing instructions
- No build steps required
