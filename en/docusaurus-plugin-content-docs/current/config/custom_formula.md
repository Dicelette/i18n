---
title: Custom formula
sidebar_position: 7
---

This command allows you to create a custom [Mathjs](https://mathjs.org/) formula, which serves as a "template". This template will automatically replace the values between brackets `[]`.

Custom formulas can be created in two ways:
- Either by a user for each server, via the command `/user_config custom_formula`
- Or by an administrator for the server, via the command `/config custom_formula`

:::info
If a custom formula is created by an administrator for the server, it will take precedence over the one created by a user.
:::

## Syntax

The custom formula must be a valid Mathjs formula. To symbolize the replacement of a value, you must use the `$` symbol as for the dice types.

Once the formula is created, the value that will be "replaced" in the `$` must be between brackets `[]`. For example, if the formula is `$ + 2`, then the rolled die must be written as `1d6 + [2]`.

:::example
- <u>Custom formula</u>: `$ + 2`
- <u>Rolled die</u>: `1d6 + [2]`
- <u>Result</u>: If the die rolls `4`, then the final result will be `4 + 2 = 6`.
:::

:::example[More complex]
- <u>Custom formula</u>: `$>85?85{cs:>=5+($-85)}:$`
- <u>Rolled die</u>: `1d100>=[$dexterity+$strength+$brawling]`
- <u>Result</u>: `1d100>={{$dexterity+$strength+$brawling>85?85{cs:>=5+($-85)}:$dexterity+$strength+$brawling}}` (*yes, this is a valid formula*)
:::

The dice can be used both in the custom formula and in the rolled die. For example, if the formula is `$ + 2d6`, then the rolled die must be written as `1d6 + [2]`. The final result will therefore be the sum of the rolled die and two six-sided dice.

## Configuration

:::usage
**`/user_config custom_formula configure (formula)`**
- `formula`: The custom formula to use. It must be a valid Mathjs formula, with the `$` symbol to represent the value between brackets `[]`.
:::

If the `formula` option is left empty, the custom formula will be deleted for the user or the server.

During configuration, the formulas are checked against the Mathjs rules. If the formula is not valid, an error message will be displayed.

:::tip
The administrative command `/config custom_formula` works in the same way.
:::

## Display

:::usage
**`/user_config custom_formula display`**
:::

Allows you to display the custom formula currently configured for the user or server. If no formula is configured, an error message will be displayed.