---
title: Administration commands
sidebar_position: 2
---

The following commands are restricted by default to members with the `Manage Roles` permission.

You can view the current server configuration with the `/config` command.

## Configuration

The following commands are grouped in the `/config` command and allow you to configure the bot for your server.

### Logs

:::usage
**`/config logs (#channel)`**
:::

The `logs` command allows you to set up a channel to:
- Report all errors,
- Log any changes made to a character.

Sending the command without the `#channel` argument will remove logging.

### Changing the result log channel

:::usage
**`/config result_channel (#channel)`**
:::

The `/config result_channel` command sets a channel to receive dice roll results instead of using a thread each time. The channel ID will then be stored in the database similarly to the `logs` command.

Sending the command without the "channel" argument will remove the results channel, similar to the `logs` command.

### Disable thread auto-Creation

:::usage
**`/config disable_threads [true/false]`**
:::

If the option is set to **true**, it disables the default creation of threads for dice rolls. Everything will be sent (without deletion) to the channel where the command was executed.

It also disables sending to the channel configured by the `/config result_channel` command, if any.

Channels and threads prefixed with `🎲` will no longer receive logs either.

Setting the option to **false** reactivates the bot's normal behavior.

### Time before message deletion

:::usage
**`/config delete_after [time]`**
:::

By default, dice roll result messages are deleted after **3** minutes. This command allows you to change the delay (up to 60 minutes) before messages are deleted.

If the value is set to **0**, messages will no longer be deleted.

This option is disabled if `/config disable_threads` is enabled.

:::tip
This command allow to have both the result log in a dedicated channel (or in threads) while keeping the result in the main channel for the players to see.
:::

## Character sheet and template management
### Delete a character/player

:::usage
**`/delete_char [@player] (*character)`**
:::

The `delete_char` command removes a character or player from the database. 

It requires:
- `[@player]` - The player's name
- `(*character)` - And/or the character's name, based on the selected user.

If no character name is provided, it will delete all data for the player. If you wish to delete only the "unnamed character" of a player, you can do so by selecting "default" from the character name list.

### Auto-Role (`/auto_role`)

:::usage
- **`/config auto_role dé (@role)`**
- **`/config auto_role stats (@role)`**
:::

These commands allow automatically adding roles when:
- A die is rolled (`/config auto_role die`)
- Statistics are validated (`/config auto_role stats`)

This notably enables the use of `/dbd` and `/dbroll` for users who actually have permission to use these two commands.

If the role is not provided, the option will be disabled.

## Game Master Dice Rolls

:::info
The two following commands allow game masters to roll dice for any registered players.
:::

:::usage
- **`/gm dbroll (@player) [statistic] (*character)`**
- **`/gm dbd (@player) (*dice name) (*character)`**
:::

Both commands are similar to [dbroll](./model#dbroll-dbroll) and [dbd](./model#dbd-dbd), but additionally require specification of the player for whom the roll is being made. As with the other commands, you can choose a character belonging to this player or leave the default choice.

## Import and Export Data

The following commands allow you to import and export data from and to a CSV file.

:::tip About Dice
It is entirely possible to import specific dice for the command [`/dbd`](./model.mdx#dbd), but you need to fill in the `dice` column as follows:
```md
- [dice]: [value]
```
For example:
```md
'- Athletics: 1d20+Strength
- Stealth: 1d20+Dexterity
```
:::

:::important About Excel
- Excel does not handle cells starting with `-` well and may interpret them as formulas. If this happens, you need to add `'` before the `-`.
- Excel may have issues reading and exporting text with accents. It is recommended to save the file in UTF-8-BOM format, using tools like Notepad++ or VSCode.
- Player `id`s may be recognized as numbers and altered. It is advised to save them as text by adding `'` before the `id`, like `'123456789012345678`.

It is highly recommended to disable Excel's automatic conversions:
![Excel](/assets/csv/EXCEL_EN_disable.png)

And to disable the error checking rule "Numbers formatted as text or preceded by an apostrophe" in the error checking options (Formulas > Error Checking Rules):
![](/assets/csv/EN_disable_nb.png)

:::

![Example](/assets/csv/example.png)


### Import

:::usage
**`/import [csv]`**
:::

The `/import` command allows you to import data from a CSV file. You can download the template using the `/csv` command and fill it with the characters and statistics you wish to import.

:::important
- Imported data will overwrite existing data, but won't delete characters that are not in the CSV file. Moreover, if the character already exists, it will be updated with the new data in the base, but the old messages will not be deleted : it is up to you to delete them.
- The minimum, maximum, and total points are not verified (to allow the import of characters who have gained experience or differ from others, such as monsters).
- Combinations should not be entered as is but should be directly calculated. For example, if the HP column is a combination of `Constitution` and `Endurance`, you must enter the result of these columns directly. There is no issue using formulas in a CSV, as the file export will only include the result!
:::

The following columns are necessary for the import:
- `user`: The Discord ID of the player or their username (without the `@`).
- `charName`: Depending on your template, this might be required. It is the character's name.
- `isPrivate`: `true` or `false` to specify if the sheet is private or not. If your template does not use private sheets, you can leave this column empty.
- The following columns must be the statistics of your template.

Theses columns are optional:
- `avatar` : The link to the character's avatar. If you don't use an avatar, you can leave this column empty. The avatar used in the display will be the player's.
- `channel` : Allows you to set a channel to send the sheet to, rather than using the default channels set when registering the template.
- `dice` : Specific dice for the `/dbd` command. If you don't use this command, you can leave this column empty (or delete it).


### Export Data

:::usage
**`/export [csv] (private_sheet_only)`**
:::

This command allows you to export the list of characters and statistics into a CSV file. Depending on the 'private' option, the provided list will be different:
- If `false`, it will include **only** characters whose sheets are **public**.
- If `true`, it will include **only** characters whose sheets are **private**.
- If omitted, it will include **all** characters, regardless of the sheet status.

The exported CSV file uses a semicolon as the separator.