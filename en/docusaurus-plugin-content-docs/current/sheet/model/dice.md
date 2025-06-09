---
title: Dices
sidebar_position: 2
---

There are two types of dice:

- The dice used with `dbroll` (the **type dice**).
- The dice saved for `dbd` (the **saved dice**).

Both types follow the [dice-roller](https://dice-roller.github.io/documentation/) syntax and also support various [notation and expression](../../introduction/expression.mdx).

When targeting a stat, the method differs depending on the dice type:
- For type dice, use the `$` keyword. This symbol will be replaced by the stat value used in `/dbroll`.
- For saved dice, simply use the names of the stats.

:::tip[Example]
- For a type dice: `1d6>$` or `1d6+$`
- For a saved dice: `1d6 > Strength` or `1d6 + Strength`

For dice based on a formula:
- For a type dice: `1d6 + {{ceil($ / 2)}}`
- For a saved dice: `1d6 + {{ceil(Strength / 2)}}`

You can also compare using a formula:
- For a type dice: `1d6 > {{ceil($ / 2)}}`
- For a saved dice: `1d6 > {{ceil(Strength / 2)}}`
:::

The presence of the `$` sign makes the statistic mandatory. Otherwise, the die can be rolled without a sheet.

## Saved Dice  

You can customize saved dice using different syntaxes:  

- **Custom Critics:** If you use custom critical with `$`, the **dice name** must include the **statistic in parentheses**, like `Animal Instinct (Strength)`. See the [Custom Critics Hits](./critics.md#custom-critics) section for more details.  
- **Statistic Name:** Allows referencing a statistic directly in the dice.  

:::example
| Type                    | Dice Name                  | Replaced Value                                       | Syntax           | Example    |
|-------------------------|----------------------------|------------------------------------------------------|------------------|------------|
| **Specific Statistic**  | Strength                   | `Strength=20`                                        | `1d6 > Strength` | `1d6 > 20` |
| **Custom Critical Hit** | Animal Instinct (Strength) | <li>`Strength=20`</li><li>Custom Critical: `>$`</li> | `1d6`            | `1d6>20`   |
:::
