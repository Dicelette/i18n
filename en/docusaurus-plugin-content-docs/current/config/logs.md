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
**`/config result_channel (#channel)`**
:::

The `/config result_channel` command sets a channel to receive dice roll results instead of using a thread each time. The channel ID will then be stored in the database similarly to the `logs` command.

Sending the command without the "channel" argument will remove the results channel, similar to the `logs` command.

### Disable auto thread creation: `disable_thread`

:::usage
**`/config disable_threads [?toggle]`**
:::

If the option is set to **true**, it disables the default creation of threads for dice rolls. Everything will be sent (without deletion) to the channel where the command was executed.

:::warning
This option overwrite the `/config result_channel` command, meaning if it is enabled, the results won't be send in the channel configured by `/config result_channel` (if any).
:::
Channels and threads prefixed with `🎲` will no longer receive logs either.

Setting the option to **false** reactivates the bot's normal behavior.

### Hidden dice: `hidden_roll`

:::usage
**`/config hidden_roll [?toggle] (#channel)`**
:::

For `/gm` commands and `/roll` commands, allow to hide the dice roll for the players.

There are two configuration possible:
- If a channel is provided, this channel will be used for the saved dice, replacing `result_channel` when the option `hidden` is used in the roll. 
- If no channel is provided, the dice will be hidden in the channel where the command was executed, and no saved dice will be created.

In the two cases, the result will be send as [**ephemeral** message](https://support.discord.com/hc/en-us/articles/1500000580222-Ephemeral-Messages-FAQ), meaning there will be no trace of the dice roll in the channel where the command was executed after some times, and no one else than the roller will see the result.

