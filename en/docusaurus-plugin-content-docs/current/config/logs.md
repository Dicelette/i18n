---
title: Logs
---
## Edit's logs and errors: `/config logs`

:::usage
**`/config logs (#channel)`**
:::

The `logs` command allows you to set up a channel to:
- Report all errors,
- Log any changes made to a character.

Sending the command without the `#channel` argument will remove logging.

### Save dice result: `result_channel`

:::usage
**`/config result_channel [?disable_thread] (#channel)`**
:::

This command lets you choose where the bot stores the dice roll results (the logs). By default, results are sent to a thread whose name begins with `🎲`.

There are two options:
- `disable_thread`: Enable this option to send the results directly in the specified channel without creating a thread. In this case, auto-deletion of messages is disabled.
- `#channel`: If you mention a channel, the results will be sent to a thread in that channel. This option is ignored if `disable_thread` is enabled.

If no arguments are provided, the behavior is the same as `disable_thread true`: the results will be sent directly in the channel where the roll was performed.

:::example
- `/config result_channel #channel` or `/config result_channel false #channel`: The results will be sent to a thread in the mentioned channel.
- `/config result_channel true` or `/config result_channel true #channel` or `/config result_channel` (if a previous configuration exists): Dice roll saving is disabled.
- `/config result_channel false`: The results will be sent to a thread prefixed by `🎲` (only if no channel is mentioned).
:::

### Hidden dice: `hidden_roll`

:::usage
**`/config hidden_roll [?toggle] (#channel)`**
:::

For `/gm` commands and `/roll` commands, allow to hide the dice roll for the players.

There are two configuration possible:
- If a channel is provided, this channel will be used for the saved dice, replacing `result_channel` when the option `hidden` is used in the roll. 
- If no channel is provided, the dice will be hidden in the channel where the command was executed, and no saved dice will be created.

In the two cases, the result will be send as [**ephemeral** message](https://support.discord.com/hc/en-us/articles/1500000580222-Ephemeral-Messages-FAQ), meaning there will be no trace of the dice roll in the channel where the command was executed after some times, and no one else than the roller will see the result.

