---
title: Dice rolling & scenes
sidebar_position: 2
---

## Dice Rolling

:::usage
**`/roll (dice) (?hidden)`**
:::

You can also use the "semi-direct" notation by adding a comment: `/roll (dice comments)`.

Please note that the "indirect" notation is not available in this mode.

![Roll](/assets/rolls/slash-commands.gif)

The `hidden` option only works if the [hidden rolls](../admin/config/index.md#hidden-dice-hidden_roll) are enabled. If the option is set to true, the result will be sent as an ephemeral message, and use the configured channel (if any) to save the results.

## Creating a New Scene

:::usage
**`/scene [name] (tempo)`**
:::

The bot will then create a new thread, prefixed with `🎲`, where it will send dice logs. This thread will be named after the `scene`, and all other threads prefixed with `🎲` will be archived.

![Scene](/assets/rolls/scene.gif)

The `tempo` argument allows you to create a "temporal bubble," which will create a thread prefixed with a clock icon, and by default, the channel name will be today's date.