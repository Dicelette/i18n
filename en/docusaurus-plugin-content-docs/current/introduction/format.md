---
title: Commands syntax
---

- Mandatory fields are enclosed in square brackets: `[fields]`.
- Optional fields are enclosed in brackets: `(fields)`.
- Auto-complete fields are marked with a `*`: `(*fields)`.
- Fields requiring a statement will be marked with `@` (`@fields`). These fields work with names (role or user, depending on the command) or Discord IDs. If the entry doesn't appear immediately, start typing the beginning of the name for auto-completion.
- In a similar way, commands requesting a salon are preceded by `#` like `#fields`.
- True/false fields (`true` or `false`) are prefixed by `?` (`?fields`).

## Auto-complete commands

In several commands, it's possible to combine both a username and a character.

By default, the characters displayed in the list are those of the user who typed the command.

If you wish to display another player's characters, you must mention the player first.

:::warning
Due to certain limitations of the Discord API, if you wish to change player, you must retype the entire command.
:::

This function is extended to the `/mj dbd` command, as the dice listed will be based on the character, listed therefore from the player. In fact, by default, skills are listed from the player who made the command.