---
title: Critics
sidebar_position: 3
---

It is possible to define :
- basic **critics**, linked to the natural die (e.g. 1 on 1d20), to represent a critical success or failure;
- custom **critics**, which apply to the natural die or to the total result, and which can use formulas or the value of a statistic.

By default, critics are active only on the `/dbroll` command, and display a special message depending on the result.


## Basic criticis

Basic criticisms only concern equality on the natural die.  
The message displayed is fixed:
- Critical success: `Critical success`.
- Critical failure: `Critical failure`.

**Configuration example:**

| Type | Natural die | Value | Display message |
|-----------------|------------|--------|----------------------|
| Critical success | 1d20 | 20 | Critical success |
| Critical Failure | 1d20 | 1 | Critical Failure |


## Custom critics

Custom critics let you define a value or formula to display a personalized message.  
They can be applied to the total or the natural die, and support mathematical formulas. Up to 22 custom critiques are possible.

You can use the `$` symbol (as with standard dice), the name of a statistic or combinations of dice.

:::example[Call of Cthulhu]
*Reference*: [Call of Cthulhu RPG Wiki](https://cthulhuwiki.chaosium.com/rules/combat.html)  
In Call of Cthulhu, successes are based on the value of the statistic. The typical die will therefore be `1D100<=$`.  
Customized reviews will be:
- Major Success": `<=round($/2)`.
- Extreme Success": `<=round($/5)`.
:::


### Skill dice and custom critics

Only dice with a comparator will be affected by custom critics.

If a custom critic uses `$`, the value used must be in the **name** of the skill dice, in brackets.

:::example
For a critical formula `<=$`, if the skill die is named `Animal Instinct (Strength)`, then `$` will be replaced by the Strength value (if any).
If the name is not found, the comparison will not be used and the die will be rolled normally.
:::

You can also combine different statistics, formulas or dice rolls in the die name.

:::note
If the name itself contains a die roll, the latter will be displayed in the die commentary, not in the result.
:::

## To remember

- Customized reviews only work on dice with comparators.
- The `$` value is replaced by the die name statistic (in brackets).
- Up to 22 custom reviews per model.

<small>For more information on field syntax: [see dedicated page](../../introduction/format.md).</small>