---
title: General information
sidebar_position: 1
---

## Dice Rolling

:::usage
**`/roll (dice) (?hidden)`**
- `dice`: The dice to roll, which can be a simple die (e.g., `d20`, `2d6+3`, etc.) or a more [complex expression](./../introduction/expression.mdx).
- `?hidden`: Optional boolean to indicate if the roll should be hidden (cf. [hidden roll](../config/threads.md#hidden-dice)).
:::

To understand all the dice notations that can be used with the bot (direct, indirect, semi-direct notation), see [this page](./message.md).

![Roll](/assets/rolls/slash-commands.gif)

## Creating a New Scene

:::usage
**`/scene [name] (tempo)`**
- `name`: The name of the scene, which will be used to create a thread.
- `tempo`: Create a time bubble (the thread will be prefixed by a clock and named with today's date by default)
:::

The bot will then create a new thread, prefixed with `🎲`, where it will send dice logs. This thread will be named after the `scene`, and all other threads prefixed with `🎲` will be archived.

![Scene](/assets/rolls/scene.gif)

## Luck Meter

The bot will automatically count successful and failed rolls on the server by user. <mark>This only works for dice rolled with the bot with a comparison</mark>, indicating `Failure` or `Success` in the message. Criticals are also counted.

This command allows you to obtain:
- A leaderboard of the most (or least!) lucky players on the server,
- The metrics of a specific player,
- Global statistics for the server.

:::usage
**`/luck_meter bilan (@user)`**
- `@user`: Optional, allows you to get statistics for a specific user.
:::

:::usage
**`/luck_meter leaderboard [type]`**
- `type`: Required, allows you to choose the type of dice to display. Choices are `Success`, `Failures`, `Critical Success`, and `Critical Failure`.
:::

:::usage
**`/luck_meter average`**
Displays the global statistics for the server.
:::

:::warning
Obviously, the luck meter only works for dice rolled with the bot, and does not work with custom crits that do not match the standard texts `Failure`, `Success`, etc.
:::

## Help

There are several help commands, depending on what you need:
- `/help info`: Displays general bot info, including how to roll a die or create a scene.
- `/help admin`: Displays administration commands, such as [logs](../config/logs.md) or [result_channel](../config/threads.md#configure-the-results-channel).
- `/help register`: Displays specific help for registering a server model and character files, and directs you to [documentation](../sheet/model/index.md).
- `/help bug`: Displays a link to create a bug report.
- `/help suggestion`: Displays a link to make a suggestion.
