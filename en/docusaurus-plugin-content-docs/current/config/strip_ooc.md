---
title: Deleting OOC Messages
description: Configure automatic deletion of out-of-character (OOC) messages in specific channels.
sidebar_position: 5
---

The `/config delete_ooc` command allows you to configure the automatic deletion of out-of-character (OOC) messages in specific channels.

:::info
This feature is especially useful for maintaining immersion in roleplay channels by automatically deleting OOC messages after a defined delay.
:::

## Basic Configuration

:::usage
**`/config delete_ooc (prefix) (suffix) (regex) (timer) (#channel) (?thread_mode)`**
- `prefix`: Prefix of OOC messages to delete  
- `suffix`: Suffix of OOC messages to delete  
- `regex`: Regular expression to detect OOC messages  
- `timer`: Duration in seconds after which OOC messages will be deleted  
- `channel`: Channel where OOC messages will be transferred before deletion  
- `thread_mode`: If `true`, messages will be transferred to a thread  
:::

### Detection Parameters

You can use three methods to identify OOC messages:

1. **Prefix and suffix**: Messages framed by specific characters  
2. **Regular expression**: For more complex patterns (advanced users)

:::warning
Regular expressions can be complex and may lead to unintended deletions. Prefer the `prefix` and `suffix` fields if you're not familiar with regex.
:::

### Transfer Options

- **No channel specified**: Messages will be deleted directly  
- **With a channel (`#channel`)**: Messages will be transferred to the specified channel before deletion  
- **Thread mode (`thread_mode: true`)**: Messages will be moved to a thread (similar to [result threads](./threads.md))  

## Usage Examples

:::example
**Deletion using prefix/suffix:**
```

/config delete\_ooc prefix:- suffix:- timer:180 channel:#ooc

```
Deletes OOC messages wrapped in `-` (e.g., `-ooc message-`) and transfers them to `#ooc` after 3 minutes.

**Deletion using regex:**
```

/config delete\_ooc regex:$ooc::(.*)$ timer:60

```
Deletes messages like `(ooc:: message)` after one minute.

**Direct deletion:**
```

/config delete\_ooc prefix:((( suffix:))) timer:120

```
Deletes messages wrapped in `(((` and `)))` after 2 minutes without transferring them.
:::

## Channel Selection

When using the command, a selection interface will appear to choose the channels, categories, forums, or threads where OOC deletion will be active.

:::tip Limits
- **Minimum**: 1 channel must be selected to activate the feature  
- **Maximum**: Up to 25 channels/threads/categories can be selected  
:::

## Disabling

To disable OOC message deletion:

:::usage
**`/config delete_ooc`** (without parameters)  
**`/config delete_ooc timer:0`**
:::

Both methods fully disable the feature.

## Integration with Other Features

This feature can be used alongside:
- [Result Threads](./threads.md) to organize dice roll messages  
- [Roll Display](./display.md) to manage dice roll deletion timers  

<small>For more information on field syntax: [see the dedicated page](../introduction/format.mdx).</small>