---
title: Self Registration
sidebar_position: 6
---

:::usage
`/config self_register [?toggle] (?validation_moderation)`
- `?toggle`: enable/disable the self-registration
- `?validation_moderation`: Only the moderators can validate the sheet after the self-registration by the player.
- `?disallow_channel` : User can't set any channel (by ID) to register their character. If set on `true`, the sheet will be sent in the default channel.
:::

Allows players with access to the template to register their **own** characters and only **public** one (private characters are not allowed to be registered by players).
Moderators will continue to be able to register characters for other players.


:::tip
You can restrict access to the template to certain roles, in order to restrict self-registration to players who have already been validated.
:::

<small>For more information about the commands syntax, see: [the dedicated page](../introduction/format.mdx).</small>
