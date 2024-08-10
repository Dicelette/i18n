---
title: Game Master Dice
sidebar_position: 4
---

:::info
The two following commands allow game masters to roll dice for any registered players.
:::

:::usage
- **`/gm dbroll (@player) [statistic] (*character) (?hidden)`**
- **`/gm dbd (@player) (*dice name) (*character) (?hidden)`**
:::

Both commands are similar to [dbroll](./model#dbroll-dbroll) and [dbd](./model#dbd-dbd), but additionally require specification of the player for whom the roll is being made. As with the other commands, you can choose a character belonging to this player or leave the default choice.

The hidden option only works if [hidden rolls](../admin/config/index.md#hidden-dice-hidden_roll) are enabled. If the option is set to true, the result will be sent as an ephemeral message, and use the configured channel (if any) to save the results. 