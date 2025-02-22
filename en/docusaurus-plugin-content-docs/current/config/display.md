---
title: Display results
---

Diverses options allows to personalize the display of the dice's results, whether in the save section or in the channel where the throw was made.

## Timestamp: `timestamp`

:::usage
**`/config timestamp [?toggle]`**
:::

If the option is set to **true**, the timestamp will be displayed in the dice results.

![](/assets/rolls/config/timestamp.png)

:::tip
The timestamp automatically adapts to the user's time zone.
:::

## Time before deletion: `delete_after`

:::usage
**`/config delete_after [time]`**
:::

By default, dice roll result messages are deleted after **3** minutes. This command allows you to change the delay (up to 60 minutes) before messages are deleted.

If the value is set to **0**, messages will no longer be deleted.

This option is disabled if there is no channel or thread for saving the result.

:::tip
This command allow to have both the result log in a dedicated channel (or in threads) while keeping the result in the main channel for the players to see.
:::

## Context and backup links
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

:::tip
This option is disabled if there is no channel or thread for saving the result.
:::

### [Dice throw] Link to the saved dice: `save_link`

:::usage
**`/config save_link [?toggle]`**
:::

Adds a link to the die backup in the die result message.

![Link to backup](/assets/rolls/config/backup_link.png)

