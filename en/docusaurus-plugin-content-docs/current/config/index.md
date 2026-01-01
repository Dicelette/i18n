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

## Edit the bot

:::usage
**`/config edit_me (nick) (bio) (avatar) (banner)`**
- `(nick)`: New nickname for the bot on the server.
- `(bio)`: New biography for the bot.
- `(avatar)`: New avatar image for the bot, as a file.
- `(banner)`: New banner image for the bot, as a file.
:::

Allow to set a custom profile for the bot on the server.

When a value is not provided, the corresponding fields will be reset to default.

## Pity

:::usage
**`/config pity (threshold)`**
- `(threshold)` : Number of fail before pity activation (min: 2)
:::

Enable the pity on dice rolls: after a certain number of consecutives failures, the bot guarantees automatic success on the next rolls.

How it works: the closer you get to the threshold the greater the probability of activation, starting at 75%. Once the threshold is reached (aka 100%), pity is automatically triggered[^1].

:::tip
The "pity" is a re-lauch of the die (until 100 reroll) until it reach a success. It only works for dice that have a comparison (`XdY+Z>A`).
:::

:::warning
To prevent cheating, the consecutive failure counter is cached for so-called "trivial" comparisons, with timestamps to identify consecutive failure.
A trivial comparison is always a success or a failure, whatever the outcome of the roll (ex: `1d20>100` is always a failure).

However, trivial comparisons may be counted if the message is not detected within the allocated time (one minute). This is rare, but it is recommanded that you:
- Do not overuse trivial comparisons.
- Increase the pity threshold to limit the risk of cheating.
:::

To disable the pity sustem, simply enter the command without any parameters.

<small>For more information about the commands syntax, see: [the dedicated page](../introduction/format.mdx).</small>

[^1]: You can found the probability code [here](https://github.com/Dicelette/discord-dicelette/blob/07e3be0ac67a4c6971f0b553d69d53026428691f/packages/bot/src/commands/admin/configuration/pity.ts#L37-L64).