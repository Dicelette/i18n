---
title: Others
sidebar_position: 3
---

The following two commands accept :
- `(@player)` : The player's name
- `(*character)` : And/or the character's name

### Display

:::usage
**`/display (@player) (*character)`**
:::

The `display` command allows you to view the statistics and dice of a character recorded in the database. 

![display](/assets/rolls/db/display_ex.png)

### Graph (`/graph`)

:::usage
**`/graph (@player) (*character) (line) (bg) (min) (max)`**
:::

The `/graph` command is a "gimmick" feature that generates a graph from a character's statistics. 
Optionally, you can also specify colors with:
- `line`: For lines (default, `#0e47b2`).
- `background`: For background (default, `#0e47b2`).

Colors can be in hexadecimal or RGB. For example, `#FF0000` or `255,0,0`.

Finally, you can set a minimum and maximum for the axes with `min` and `max`.

Default:
- The minimum is calculated according to the server template (if existing).
- The maximum is determined in different ways:
   - If a maximum is defined by the template, it will be used.
   - Otherwise, it will be based on the critical success value.
   - If neither of the two previous options is available, it will be based on the die value (for example, if `1d20`, the value will be 20).
   - As a last resort, it will be automatically calculated based on the user's statistics.

![graph](/assets/graph.jpg)
