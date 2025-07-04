---
title: General configuration
sidebar_position: 1
---

The following commands are restricted by default to members with the <mark>Manage Roles</mark> permission.

You can view the current server configuration with the `/config display` commands :
:::usage
- **`/config display general`**: Display the server's general configuration.
- **`/config display template`**: Display the template configuration (links, statistics names, excluded or global dice names), if any.
:::

## Change language

:::usage
**`/config change_language [language]`
- `[language]`: Language to use (`fr` or `en`)
:::

Allow to change the language of the bot, overriding any language configuration (including client) settings.

For the moment, only English and French are available.

<small>For more information about the commands syntax, see: [the dedicated page](../introduction/format.mdx).</small>