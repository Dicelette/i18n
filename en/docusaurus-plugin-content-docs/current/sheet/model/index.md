---
title: Registering a Template
sidebar_position: 1
---

# Registering a Template

To get started, you need to **create** a new template. Use `/register` followed by the template's name. You can also create an empty template using `/generate` or the form available [here](./form.mdx).

This command allows you to create a `JSON` file with the following (optional) parameters:

- `name`: The names of the stats, separated by commas. If a name contains a space, enclose it in quotes.
- `dice`: The type of dice to roll, which can include a formula.
- `total`: The total number of points players can distribute.
- `character`: Makes entering a character name mandatory.
- `critical_success`: The value considered a critical success.
- `critical_failure`: The value considered a critical failure.
- `skills`: Adds fields for skill or attack dice.

You can check template examples in the `template` files [here](https://github.com/Dicelette/discord-dicelette/tree/main/template).

:::info Note
Stats and dice are optional:
- Without stats, you cannot use the `/dbroll` command.
- Without dice, you cannot use `/dbd`.
:::

## Dice

There are two types of dice:

- The dice used with `dbroll` (the **type dice**).
- The dice saved for `dbd` (the **saved dice**).

Both types follow the [dice-roller](https://dice-roller.github.io/documentation/) syntax and also support various [expressions](../../introduction/expression.mdx).

When targeting a stat, the method differs depending on the dice type:
- For type dice, use the `$` keyword. This symbol will be replaced by the stat value used in `/dbroll`.
- For saved dice, simply use the names of the stats.

:::tip[Example]
- For a type dice: `1d6>$` or `1d6+$`
- For a saved dice: `1d6 > Strength` or `1d6 + Strength`

For dice based on a formula:
- For a type dice: `1d6 + {{ceil($ / 2)}}`
- For a saved dice: `1d6 + {{ceil(Strength / 2)}}`

You can also compare using a formula:
- For a type dice: `1d6 > {{ceil($ / 2)}}`
- For a saved dice: `1d6 > {{ceil(Strength / 2)}}`
:::

### Saved Dice  

You can customize saved dice using different syntaxes:  

- **Custom Critical:** If you use custom critical with `$`, the **dice name** must include the **statistic in parentheses**, like `Animal Instinct (Strength)`. See the [Custom Critical Hits](#custom-criticals) section for more details.  
- **Statistic Name:** Allows referencing a statistic directly in the dice.  

:::example

| Type                    | Dice Name                  | Replaced Value                                       | Syntax           | Example    |
|-------------------------|----------------------------|------------------------------------------------------|------------------|------------|
| **Specific Statistic**  | Strength                   | `Strength=20`                                        | `1d6 > Strength` | `1d6 > 20` |
| **Custom Critical Hit** | Animal Instinct (Strength) | <li>`Strength=20`</li><li>Custom Critical: `>$`</li> | `1d6`            | `1d6>20`   |

:::

## Stats

Each stat has a name, a minimum value (`min`), a maximum value (`max`), and a combination option (`combination`).
- `min` and `max` define the minimum and maximum values the stat can have when recorded.
- `combination` allows combining multiple stats. This field cannot coexist with `min` and `max`, and combined stats will not count toward the total points allocated in the `total` field.

You can exclude stats from dice rolls, preventing them from being rolled. This is useful for stats not used in the game or those only utilized in formulas.

## Criticals

You can define:
- Basic criticals, linked to natural dice rolls, configurable for critical successes and failures.
- Custom criticals, which can apply to natural rolls or total results and support formulas.

By default, criticals are only active for the `/dbroll` command and display a special message based on the result.

### Basic Criticals

These are tied to a natural roll and trigger only on equality. The value is configurable, but the displayed message is not:
- For a critical success: the message will be `Critical Success`.
- For a critical failure: the message will be `Critical Failure`.

### Custom Criticals

Custom criticals allow specific values to display a personalized message. Unlike basic criticals, custom ones can compare totals **or** natural rolls and support formulas. They can also apply to skill dice. Up to 22 custom criticals are allowed.

Custom criticals support the `$` wildcard symbol (used for type dice comparisons) to compare against the active stat. You can also use stat names or combine them with other dice.

:::example[Call of Cthulhu]
*Reference*: [Call of Cthulhu RPG Wiki](https://cthulhuwiki.chaosium.com/rules/combat.html)  
In Call of Cthulhu, successes are based on the stat value. The type dice would be `1D100<=$`.  
Custom criticals:
- "Major Success": `<=round($/2)`
- "Extreme Success": `<=round($/5)`
:::

#### Skill Dice and Custom Criticals
Only dice with a comparator will trigger custom criticals.

When a custom critical uses the `$` symbol, the value must appear in the **name** of the skill dice, enclosed in parentheses.

:::example
For a custom critical with the value `<=$`, if the skill dice is named `Animal Instinct (Strength)`, `$` will be replaced by the Strength stat value if it exists.  
If the name is not found, the comparison will not apply, and the dice will roll normally.
:::

Additionally, you can combine different stats, formulas, or dice rolls in the name of the dice.

:::note
If the name itself includes a dice roll, it will appear in the dice's comment instead of the result.
:::

## Next Steps

Once the template is ready, use `/register [#channel] [file] (#user_channel) (#private_character)`.
- `#channel`: The channel where the template will be sent, later used for creating character sheets.
- `file`: The `JSON` file you created earlier.
- `#user_channel`: The channel where character sheets will be published.[^1]
- `#private_character`: Similar to `#user_channel`, but sheets published here are only visible to the user who created them or those with access to the channel (or users with the `MANAGE_ROLES` permission). If undefined, the private sheet function will be disabled.
- `?update`: Updates all existing character sheets if they exist.
- `?delete_all`: Deletes all existing character sheets if they exist.

:::warning About Private Sheets
If a sheet is not marked private but is published in a restricted channel, users can still view it using the `/show` and `/graph` commands.
:::

The embed will be pinned for easy access.

![embed](/assets/register/embed_template.png)

:::warning Note
You must re-register the template if you want to change the default channel for public and private sheets. However, the registered user does not need to be re-registered since the channel and message ID are saved in the database.  
To move all sheets to another channel, use the [`/export`](../import_export.md) command.
:::

[^1]: A forum can also be used, automatically creating a post for the character. The player (and admins) will be mentioned in the post.

