# Cube Rule Skill Implementation Plan

> **For Claude:** REQUIRED SUB-SKILL: Use superpowers:executing-plans to implement this plan task-by-task.

**Goal:** Build a sharable Claude Code plugin that provides the Cube Rule of Food Identification as a skill.

**Architecture:** Single-file skill (SKILL.md) with inline classification table, packaged as a Claude Code plugin with proper manifest, README, CLAUDE.md, and LICENSE.

**Tech Stack:** Markdown, Claude Code plugin system (.claude-plugin/plugin.json)

**Design doc:** `docs/plans/2026-03-03-cube-rule-skill-design.md`

**Reference site:** https://cuberule.com/

---

### Task 1: Create plugin manifest

**Files:**
- Create: `.claude-plugin/plugin.json`

**Step 1: Create the plugin manifest**

```json
{
  "name": "cube-rule",
  "description": "The Cube Rule of Food Identification - classify any food by structural starch position",
  "version": "1.0.0",
  "author": {
    "name": "Your Name"
  },
  "homepage": "https://cuberule.com/",
  "license": "Unlicense",
  "keywords": ["food", "classification", "cube-rule", "taxonomy", "fun"]
}
```

**Step 2: Verify the JSON is valid**

Run: `python3 -c "import json; json.load(open('.claude-plugin/plugin.json')); print('Valid JSON')"`
Expected: `Valid JSON`

**Step 3: Commit**

```bash
git add .claude-plugin/plugin.json
git commit -m "feat: add plugin manifest"
```

---

### Task 2: Create the SKILL.md

**Files:**
- Create: `skills/cube-rule/SKILL.md`

**Step 1: Write the skill file**

Write `skills/cube-rule/SKILL.md` with the following sections:

1. YAML frontmatter with `name: cube-rule` and a `description` that triggers on food classification questions, food identity debates, and "what is X" food questions.

2. Overview section: one paragraph explaining that the Cube Rule classifies foods purely by the position of structural starch relative to the filling, using the six faces of a cube as a model. Created by @Phosphatide. Link to https://cuberule.com/.

3. Classification table with all 9 categories:

| # | Category | Starch Position | Examples |
|---|----------|----------------|----------|
| 0 | Salad | No structural starch | Steak, soup ("wet salad"), mashed potatoes, chocolate, flan, turducken |
| 1 | Toast | Bottom only | Pizza, nigiri sushi, pie slice (bent toast) |
| 2 | Sandwich | Top + bottom | Quesadilla (non-folded), toast sandwich, victoria sponge cake |
| 3 | Taco | Bottom + two sides | Hot dog, sub sandwich (uncut), pie slice on its side |
| 4 | Sushi | Bottom + top + two sides | Falafel wrap, pigs in a blanket, enchilada |
| 5 | Quiche | Bottom + all four sides (open top) | Cheesecake, bread bowl soup, falafel pita |
| 6 | Calzone | All six sides enclosed | Burrito, corn dog, whole pie, dumpling, pop-tart, uncrustables |
| 7 | Cake | Three stacked starch layers | Lasagna, Big Mac, flapjacks |
| 8 | Nachos | Smaller starch pieces within | Poutine, Lucky Charms, salad with croutons, ramen ("wet nachos"), couscous |

4. Classification method: identify structural starch → determine which cube faces it occupies → match to category.

5. Special rules:
   - Rice: interpreters have complete freedom defining its nature
   - Vanilla soy latte: a three-bean soup, therefore a wet salad (category 0)
   - Muffins/bread blocks: toast (category 1) in unsliced form
   - Humans: ravioli (per food critic Soleil Ho)

6. Handle absurdist edge cases enthusiastically - the cube rule's charm is in pushing it to ridiculous conclusions.

**Step 2: Verify the frontmatter is parseable**

Run: `head -5 skills/cube-rule/SKILL.md`
Expected: Valid YAML frontmatter with `---` delimiters, `name:`, and `description:`

**Step 3: Commit**

```bash
git add skills/cube-rule/SKILL.md
git commit -m "feat: add cube rule skill with complete classification system"
```

---

### Task 3: Create LICENSE file

**Files:**
- Create: `LICENSE`

**Step 1: Write the Unlicense**

Use the standard Unlicense text from https://unlicense.org/

**Step 2: Commit**

```bash
git add LICENSE
git commit -m "feat: add Unlicense"
```

---

### Task 4: Create CLAUDE.md

**Files:**
- Create: `CLAUDE.md`

**Step 1: Write CLAUDE.md**

Contents:
- Project description: Claude Code plugin providing the Cube Rule of Food Identification
- Structure overview: where skills live, where the manifest is
- How to test: install locally with `claude plugins add .` or symlink into `~/.claude/plugins/`
- No build steps required - pure markdown

**Step 2: Commit**

```bash
git add CLAUDE.md
git commit -m "docs: add CLAUDE.md with project instructions"
```

---

### Task 5: Create README.md

**Files:**
- Create: `README.md`

**Step 1: Write README.md**

Contents:
- Title and brief description of the cube rule
- Installation: `claude plugins add <repo-url>`
- Usage: how the skill triggers (food classification questions, debates, etc.)
- The classification table (reproduced for quick reference)
- Attribution to @Phosphatide and link to https://cuberule.com/
- License: Unlicense

**Step 2: Commit**

```bash
git add README.md
git commit -m "docs: add README with installation and usage instructions"
```

---

### Task 6: Final review and verification

**Step 1: Verify complete file structure**

Run: `find . -not -path './.git/*' -not -path './.git' | sort`

Expected output should include:
```
.
./.claude-plugin
./.claude-plugin/plugin.json
./CLAUDE.md
./docs
./docs/plans
./docs/plans/2026-03-03-cube-rule-implementation.md
./docs/plans/2026-03-03-cube-rule-skill-design.md
./LICENSE
./README.md
./skills
./skills/cube-rule
./skills/cube-rule/SKILL.md
```

**Step 2: Verify plugin.json is valid**

Run: `python3 -c "import json; json.load(open('.claude-plugin/plugin.json')); print('Valid')"`

**Step 3: Verify SKILL.md frontmatter**

Run: `head -5 skills/cube-rule/SKILL.md`

**Step 4: Review git log**

Run: `git log --oneline`

Expected: 6+ commits showing incremental progress.
