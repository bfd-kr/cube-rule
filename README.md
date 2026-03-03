# Cube Rule of Food Identification

A Claude Code plugin that gives Claude mastery of the [Cube Rule of Food Identification](https://cuberule.com/) - the grand unified theory of food classification.

Is a hot dog a sandwich? Is cereal a soup? The cube rule settles these debates once and for all by classifying foods purely by the position of structural starch.

## Installation

First, add the marketplace:

```bash
claude plugin marketplace add https://github.com/bfd-kr/cube-rule.git
```

Then install the plugin:

```bash
claude plugin install cube-rule
```

## Usage

Once installed, the skill activates when you ask Claude about food classification:

- "Is a hot dog a sandwich?"
- "Classify a burrito"
- "What type of food is lasagna?"
- "Is cereal a soup?"

## The Cube Rule

All foods are classified by where structural starch sits relative to the filling, mapped onto the six faces of a cube:

| # | Category | Starch Position | Examples |
|---|----------|----------------|----------|
| 0 | Salad | No structural starch | Steak, soup, mashed potatoes |
| 1 | Toast | Bottom only | Pizza, nigiri sushi |
| 2 | Sandwich | Top + bottom | Quesadilla, victoria sponge |
| 3 | Taco | Bottom + two sides | Hot dog, sub sandwich |
| 4 | Sushi | Bottom + top + two sides | Wrap, enchilada |
| 5 | Quiche | Bottom + four sides (open top) | Cheesecake, bread bowl |
| 6 | Calzone | All six sides | Burrito, corn dog, pop-tart |
| 7 | Cake | Three stacked starch layers | Lasagna, Big Mac |
| 8 | Nachos | Smaller starch pieces within | Poutine, Lucky Charms |

## Attribution

The Cube Rule of Food Identification was created by [@Phosphatide](https://cuberule.com/). This plugin packages their taxonomy as a Claude Code skill.

## License

This is free and unencumbered software released into the public domain. See [LICENSE](LICENSE) for details.
