---
title: Others
sidebar_position: 3
---
### Display

:::usage
**`/display (@player) (*character)`**
- `@player`: The player whose character you want to display.
- `*character`: The character you want to display, if any.
:::

The `display` command allows you to view the statistics and dice of a character recorded in the database. 

![display](/assets/rolls/db/display_ex.png)

### Graph (`/graph`)

:::usage
**`/graph (@player) (*character) (line) (bg) (min) (max)`**
- `@player`: The player whose character you want to graph.
- `*character`: The character you want to graph, if any.
- `line`: The color of the line (default: `#0e47b2`).
- `bg`: The background color (default: `#0e47b2`).
- `min`: The minimum value for the axes.
- `max`: The maximum value for the axes.
:::

The `/graph` command is a "gimmick" feature that generates a graph from a character's statistics. You can personalize the color of the line and the background using hexadecimal or RGB values (e.g., `#FF0000` or `255,0,0`).


By default:
- The minimum is calculated according to the server template (if existing).
- The maximum is determined in different ways:
   - If a maximum is defined by the template, it will be used.
   - Otherwise, it will be based on the critical success value.
   - If neither of the two previous options is available, it will be based on the die value (for example, if `1d20`, the value will be 20).
   - As a last resort, it will be automatically calculated based on the user's statistics.

![graph](/assets/graph.jpg)

<small>For more information about the commands syntax, see: [the dedicated page](../../introduction/format.mdx).</small>