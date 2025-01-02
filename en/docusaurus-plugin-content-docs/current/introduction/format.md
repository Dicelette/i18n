---
title: Commands syntax
---

- Mandatory fields are enclosed in square brackets: `[fields]`.
- Optional fields are enclosed in brackets: `(fields)`.
- Auto-complete fields are marked with a `*` : `(*fields)`.
- Fields requiring a statement will be marked with `@` (`@fields`). These fields work with names (role or user, depending on the command) or Discord IDs. If the entry doesn't appear immediately, start typing the beginning of the name for auto-completion.
- Similarly, commands requesting a channel are preceded by `#` like `#fields`.
- Boolean fields are prefixed by `?` (`?fields`).

## Auto-completion fields

In several commands, it is possible to combine both a username and a character name.

By default, the characters displayed in the list are those of the user who entered the command.

If you wish to display the characters of another player, you must mention the player first.

:::warning  
Due to certain limitations of the Discord API, if you want to switch to a different player, you must retype the entire command.  
:::

This functionality is extended for the `/mj dbd` command, as the listed dice will be based on the character, which is therefore displayed starting from the player. As a result, by default, the skills are listed based on the player who issued the command.
