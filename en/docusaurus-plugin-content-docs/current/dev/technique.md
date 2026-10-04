---
title: Technical overview
sidebar_position: 3
---

This page describes how Dicelette works internally and how your data is handled. For the full list of stored data, see the [Terms of Service](./TOS/index.md) and the [privacy policy](./TOS/policy.md).

## Technical Architecture

The bot uses the [@diceRoller](https://dice-roller.github.io/documentation/) API for all dice calculations, ensuring reliable results and a wide variety of supported expressions. The differences between Dice Roller's syntax and Dicelette's are detailed in the [Dice Notations](../introduction/expression.mdx) page.

The random number generator in use is described in the [FAQ](../introduction/faq.md#is-it-possible-to-cheat).

## Data-Respectful Approach

Unlike other solutions, this bot prioritizes your control over your data:
- **Minimal storage**: Only message IDs and essential information are saved
- **Full control**: Your character sheets remain in your Discord messages
- **Automatic cleanup**: Obsolete data is automatically deleted

This approach guarantees maximum security and full control over your gaming information.

## Data Management

### What is Stored

The bot uses a SQLite3 database[^1] to store only:
- IDs of messages containing your sheets
- Links between users and their characters
- Server configuration settings
- Custom statistics templates

### Automatic Cleanup

Data is automatically deleted in several cases:
- Deletion of registered messages or channels
- Bot removal from the server
- Use of integrated cleanup features

### Privacy Respect

:::note Contact for deletion
If you want to delete your data after leaving a server, contact us via Discord (`@mara__li`) or email (`lisandra_dev@yahoo.com`) with your Discord ID or server ID.
:::

:::warning Manual cleanup
In case of issues with automatic deletion, use the manual deletion commands available in the bot to clean up your data.
:::

[^1]: Local database using [Enmap](https://enmap.evie.dev/) for optimized management.
