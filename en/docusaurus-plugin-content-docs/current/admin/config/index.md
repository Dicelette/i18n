---
title: General Configuration
---

The following commands are restricted by default to members with the `Manage Roles` permission.

You can view the current server configuration with the `/config display` command.

:::info
The following commands work for both text-only dice and dice thrown with slashcommands (whether `/roll` or `/dbd` and `/dbroll`).
:::

Unless otherwise specified, all options are disabled by default.

## Format

- Mandatory fields are enclosed in square brackets: `[fields]`.
- Optional fields are enclosed in brackets: `(fields)`.
- Auto-complete fields are marked with a `*` : `(*fields)`.
- Fields requiring a statement will be marked with `@` (`@fields`). These fields work with names (role or user, depending on the command) or Discord IDs. If the entry doesn't appear immediately, start typing the beginning of the name for auto-completion.
- Similarly, commands requesting a channel are preceded by `#` like `#fields`.
- Boolean fields are prefixed by `?` (`?fields`).

## Journalization
### Administration: `logs`

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

## Displaying results

Diverses options allows to personalize the display of the dice's results, whether in the save section or in the channel where the throw was made.

### Timestamp: `timestamp`

:::usage
**`/config timestamp [?toggle]`**
:::

If the option is set to **true**, the timestamp will be displayed in the dice results.

![](/assets/rolls/config/timestamp.png)

:::tip
The timestamp automatically adapts to the user's time zone.
:::

### Time before deletion: `delete_after`

:::usage
**`/config delete_after [time]`**
:::

By default, dice roll result messages are deleted after **3** minutes. This command allows you to change the delay (up to 60 minutes) before messages are deleted.

If the value is set to **0**, messages will no longer be deleted.

This option is disabled if `/config disable_threads` is enabled.

:::tip
This command allow to have both the result log in a dedicated channel (or in threads) while keeping the result in the main channel for the players to see.
:::

### [Save] Link to the dice's context: `context`

:::usage
**`/config context [?toggle]`**
:::

Adds a link to the context of the die in the die save.
- If auto-delete is enabled, the link created will return to the previous die message.
- If auto-delete is disabled, the link will refer to the die's message directly.

:::warning
If the context message is deleted, the link will no longer work.
:::

![Link to context](/assets/rolls/config/context.png)

### [Dice throw] Link to the saved dice: `save_link`

:::usage
**`/config save_link [?toggle]`**
:::

Adds a link to the die backup in the die result message.

![Link to backup](/assets/rolls/config/backup_link.png)

