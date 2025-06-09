---
title: Statistics
sidebar_position: 1
---

Each statistic has :
- a **name**,
- a **minimum value** (`min`),
- a **maximum value** (`max`)
- and possibly a **combination** (`combination`) of several other statistics.

The `combination` cannot coexist with `min` and `max`, and combined statistics are not deducted from the total points allocated in the `total` field.

You can exclude certain statistics from the selection when rolling dice, thus preventing their use in commands.  
This is useful for statistics only used in formulas or not intended for rolls.

### Example configuration

| Name | min | max | combination | Exclude from roll |
|-----------|-----|-----|-------------------|:--------------:|
| Strength | 1 | 10 | |
| PV | | Constitution+Endu | ✅ |
| Dexterity | 1 | 12 | | |

<small>For more information about the commands syntax, see: [the dedicated page](../../introduction/format.md).</small>