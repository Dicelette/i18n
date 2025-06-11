---
title: Display results
sidebar_position: 4
---

Diverses options allows to personalize the display of the dice's results, whether in the save section or in the channel where the throw was made.

## Timestamp: `timestamp`

:::usage
**`/config timestamp [?toggle]`**
- `?toggle`: Disable or enable the timestamp.
:::

If the option is enabled (**true**), the timestamp will be displayed in the dice results.

![](/assets/rolls/config/timestamp.png)

:::tip
The timestamp automatically adapts to the user's time zone.
:::

## Time before deletion

:::usage
**`/config delete_after [time]`**
- `[time]` : Delay in second (0 = never deleted)
:::

Defines the delay before automatic deletion of result messages (from 0 to 3600s, default: 180s).

This setting is disabled if there are no backup channels or threads.

:::tip
Allows you to have both a dedicated log and to keep the result indefinitely in the original room if required.
:::

## Context's link
### Link to the die context

:::usage
**`/config context [?toggle]`**
- `?toggle`: Disable or enable the context link.
:::

Adds a link to the context of the die in the die save.
- If auto-delete is enabled, the link created will return to the previous die message.
- Otherwise the link will refer to the die's message directly.

:::warning
If the context message is deleted, the link will no longer work.
:::

![Link to context](/assets/rolls/config/context.png)

:::tip
This option is disabled if there is no channel or thread for saving the result.
:::

### Link to the saved dice

:::usage
**`/config save_link [?toggle]`**
- `?toggle`: Disable or enable the link to the saved dice.
:::

Adds a link to the die backup in the die result message.

![Link to backup](/assets/rolls/config/backup_link.png)

<small>For more information about the commands syntax, see: [the dedicated page](../introduction/format.mdx).</small>