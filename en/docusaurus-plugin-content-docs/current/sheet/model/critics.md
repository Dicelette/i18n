---
title: Critics
sidebar_position: 3
---

You can define:
- Basic critics, linked to natural dice rolls, configurable for critical successes and failures.
- Custom critics, which can apply to natural rolls or total results and support formulas.

By default, critics are only active for the `/dbroll` command and display a special message based on the result.

## Basic critics

These are tied to a natural roll and trigger only on equality. The value is configurable, but the displayed message is not:
- For a critical success: the message will be `Critical Success`.
- For a critical failure: the message will be `Critical Failure`.

## Custom critics

Custom critics allow specific values to display a personalized message. Unlike basic critics, custom ones can compare totals **or** natural rolls and support formulas. They can also apply to skill dice. Up to 22 custom critics are allowed.

Custom critics support the `$` wildcard symbol (used for type dice comparisons) to compare against the active stat. You can also use stat names or combine them with other dice.

:::example[Call of Cthulhu]
*Reference*: [Call of Cthulhu RPG Wiki](https://cthulhuwiki.chaosium.com/rules/combat.html)  
In Call of Cthulhu, successes are based on the stat value. The type dice would be `1D100<=$`.  
Custom critics:
- "Major Success": `<=round($/2)`
- "Extreme Success": `<=round($/5)`
:::

### Skill Dice and Custom critics
Only dice with a comparator will trigger custom critics.

When a custom critical uses the `$` symbol, the value must appear in the **name** of the skill dice, enclosed in parentheses.

:::example
For a custom critical with the value `<=$`, if the skill dice is named `Animal Instinct (Strength)`, `$` will be replaced by the Strength stat value if it exists.  
If the name is not found, the comparison will not apply, and the dice will roll normally.
:::

Additionally, you can combine different stats, formulas, or dice rolls in the name of the dice.

:::note
If the name itself includes a dice roll, it will appear in the dice's comment instead of the result.
:::