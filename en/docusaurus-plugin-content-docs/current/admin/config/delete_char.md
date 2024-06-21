---
title: Delete a character
---

:::usage
**`/delete_char [@player] (*character)`**
:::

This command allow to delete a character or a player from the database.

It asks:
- `[@player]` : The player username (mention) to delete
- `(*character)` : The character name to delete, depending of the specified player.

If no character is specified, the entire data of the player will be deleted. You can use the `default` key to delete the default character of the player (character without name, if not set).