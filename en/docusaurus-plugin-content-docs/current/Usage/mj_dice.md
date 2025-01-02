---
title: Game Master Dice
sidebar_position: 4
---

:::info
The two following commands allow game masters to roll dice for any registered players.
:::

:::usage
- **`/gm dbroll (@player) [statistic] (... other option) (*character) (?hidden)`**
- **`/gm dbd (@player) (*dice name) (... other options) (*character) (?hidden)`**
- **`/gm calc (@player) [statistic] [sign] [expression] (... other options) (*character) (?hidden)`**
:::

All commands are similar to [dbroll](./model.mdx#dbroll-dbroll), [dbd](./model.mdx#dbd-dbd) and [calc](./model.mdx#calculations-calc), but additionally require specification of the player for whom the roll is being made. As with the other commands, you can choose a character belonging to this player or leave the default choice.

The hidden option only works if [hidden rolls](../config/logs.md#hidden-dice-hidden_roll) are enabled. If the option is set to true, the result will be sent as an ephemeral message, and use the configured channel (if any) to save the results. 