---
title: General configuration
sidebar_position: 1
---

The following commands are restricted by default to members with the `Manage Roles` permission.

You can view the current server configuration with the `/config display` command.

:::info
The following commands work for both text-only dice and dice thrown with slashcommands (whether `/roll` or `/dbd` and `/dbroll`).
:::

Unless otherwise specified, all options are disabled by default.

## Change language

:::usage`/config change_language [language]`:::

Allow to change the language of the bot, overriding any language configuration (including client) settings.

For the moment, only English and French are available.