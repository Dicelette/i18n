---
title: Result's channels
description: Disable the result's forwarding in threads or send them in specific channel.
sidebar_position: 2
---

By default, the bot will copy the dice's results (and other commands)

It is possible to:
- Disable the copy totally,
- Copy the results in a specific channel.

:::info
If the roll is made in a thread prefixed by `🎲`, the result will not be sent in the configured channel or an automatic thread.
:::

## Configure the result's channel

:::usage
**`/config result_channel [?disable_thread] (#channel)`**
- `?disable_thread`: Disable the automatic thread creation for the results.
- `#channel`: target channel
:::

- If `disable_thread` is enabled, results are sent to the salon without creating a thread (and auto-delete is disabled).
- If a salon is specified, results will be sent to a thread in that salon (unless `disable_thread` is enabled).
- Without arguments, the behavior corresponds to `/config result_channel true`.


:::example
- **Send to a specific channel**: `/config result_channel #channel`.
- **Disable automatic creation/result channel**: `/config result_channel true`
- **Use automatic thread creation**: `/config result_channel false`
:::

If the copy is entirely disabled, the [automatic deletion](./display.md#time-before-deletion) of the results will be disabled too.

### Hidden dice

:::usage
**`/config hidden_roll [?toggle] (#channel)`**
- `?toggle`: Enable or disable the hidden rolls.
- `#channel`: Channel to use to save the hidden rolls
:::

Enables the `hidden` option for `/gm` and `/roll` commands, and hides the result from other players.

- If a salon is mentioned, it will be used to save the invisible roll.
- Otherwise, no save is made.

In all cases, the message will be sent in [**ephemeral**](https://support.discord.com/hc/fr/articles/1500000580222-Ephemeral-Messages-FAQ): only the person who rolled the die will see the result.

<small>For more information about the commands syntax, see: [the dedicated page](../introduction/format.mdx).</small>