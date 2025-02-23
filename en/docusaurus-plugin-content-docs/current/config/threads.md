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


:::usage
**`/config result_channel [?disable_thread] (#channel)`**
:::


There are two options:
- `disable_thread`: Enable this option to send the results directly in the specified channel without creating a thread. In this case, auto-deletion of messages is disabled.
- `#channel`: If you mention a channel, the results will be sent to a thread in that channel. This option is ignored if `disable_thread` is enabled.

If no arguments are provided, the behavior is the same as `/config result_channel true`: the results will be sent directly in the channel where the roll was performed.



:::example
- <u>Sent to a specific channel</u>: 
    - `/config result_channel #channel`  
    - `/config result_channel false #channel`   

- <u>Disable automatic thread/result channel</u>:
    - `/config result_channel true`
    - `/config result_channel true #channel`  
    - `/config result_channel` (if a previous configuration exists)
- <u>Use automatic thread creation</u>: `/config result_channel false` (the results will be sent to a thread prefixed by `🎲`) 
:::

If the copy is entirely disabled, the [automatic deletion](./display.md#time-before-deletion-delete_after) of the results will be disabled too.

### Hidden dice: `hidden_roll`

:::usage
**`/config hidden_roll [?toggle] (#channel)`**
:::

For `/gm` commands and `/roll` commands, allow to hide the dice roll for the players.

There are two configuration possible:
- If a channel is provided, this channel will be used for the saved dice, replacing `result_channel` when the option `hidden` is used in the roll. 
- If no channel is provided, the dice will be hidden in the channel where the command was executed, and no saved dice will be created.

In the two cases, the result will be sent as [**ephemeral** message](https://support.discord.com/hc/en-us/articles/1500000580222-Ephemeral-Messages-FAQ), meaning there will be no trace of the dice roll in the channel where the command was executed after some times, and no one else than the roller will see the result.

