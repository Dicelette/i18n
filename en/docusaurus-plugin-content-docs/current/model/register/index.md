---
title: Registering
sidebar_position: 1
---
First, you need to **generate** a new template. To do this, use the command `/register`, followed by the name of the template. More over, you can generate a server template with the following command: `/generate`.

This command will allow you to create a new `JSON` file, with the following (optional) parameters:
- `name`: The name of the statistics to be separated by a space or a comma. If any of the statistics contain a space, you must surround it with quotation marks. For example: `"Intelligence Logic", Strength, Dexterity`.
- `die`: The type of dice to roll, which can contain a formula (see [#dice](#dice)).
- `total`: If, when creating, your players have a number of points to distribute. Unfortunately, it is not possible to set conditions for this total (for example, depending on the character's age, they will have only 60 points, while an older character will have 70). In these cases, it is better to choose the highest value and check manually.
- `character`: You can make entering a character name mandatory with this option.
- `critical_success`: In natural dice rolls, if a die falls on this value, it is considered a critical success.
- `critical_failure`: In natural dice rolls, if a die falls on this value, it is considered a critical failure.
- `skill`: Allows defining (when the template is edited before saving) the addition of fields for skill (or attack) dice. Like the name, you must separate the values with a comma.

For template examples, you can consult the `template` files [here](https://github.com/Dicelette/discord-dicelette/tree/main/template) or [here](register/template).

:::info
Statistics and dice are optional:
- The absence of statistics will prevent the use of the `/dbroll` command, and you will not be able to save statistics on the sheets. If you save statistics after creating users, you will need to recreate the sheets.
- The absence of dice (either in templates or sheets) will prevent the use of `/dbd`.
:::

## Dice

There are two types of dice:
- The die that will be rolled by the `dbroll` command, which we will call **die type**.
- The dice saved for the `dbd` command, which we will call **saved dice**.

Both types of dice must follow the syntax of the [dice-roller API](https://dice-roller.github.io/documentation/), and can support various mathematical formulas.

In both cases, you can use the syntax `{{` and `}}` to write complex mathematical formulas, such as `ceil`, `floor`, `round`, etc. However, if you want to "target" a statistic, the syntax will be different depending on what you are using:
- Die types target only the syntax used in the `dbroll` command. The sign to indicate a statistic is `$`.
- Saved dice target the syntax used in the `dbd` command. Since you have access to all statistics, you can target them directly with their name.

:::tip[Example]
- For a die type: `1d6>$` or `1d6+$`
- For a saved die: `1d6 > Strength` or `1d6 + Strength`

For a die based on a formula:
- For a die type: `1d6 + {{ceil($ / 2)}}`
- For a saved die: `1d6 + {{ceil(Strength / 2)}}`

It is also possible to compare with a formula:
- For a die type: `1d6 > {{ceil($ / 2)}}`
- For a saved die: `1d6 > {{ceil(Strength / 2)}}`
:::

## Statistics

Statistics are based on a name, but you will notice that after generating the file, each statistic will have three fields:
- `min`: The minimum value the statistic can have.
- `max`: The maximum value the statistic can have.
- `combination`: If the statistic is a combination of several other statistics, you can indicate it here. For example, if the `Dodge` statistic is the sum of `Strength` and `Dexterity`, you can indicate it here. Using a combination automatically cancels out the `min` and `max` values. Additionally, combined statistics will not be calculated in the total sum.

<details>
  <summary>Empty Template</summary>
  ```json
  {
  "charName": false,
  "statistics": {
    "NAME": {
      "min": 1,
	  "max": 20,
	  "combination": ""
    },
	"COMBINATION": {
	  "combination": "NAME*2"
    },
  },
  "diceType": "",
  "critical": {
    "failure": 0,
    "success": 0
  },
  "total": 0,
  "damage": {
    "NAME": ""
  }
}
```
</details> 

## What's Next?

Once the template is ready, use `/register [#channel] [file] (#user_chan) (#private_character)`.
- `#channel` is the channel where the template will be sent. It will then be used for sheet creation.
- `file` is the previously created `JSON` file.
- `#user_chan` is the channel where the sheets will be published.
- `#private_character` works similarly to `#user_chan`, but the sheets published in this channel will only be visible to the user who registered the sheet or to those who have access to this channel (as well as people with the `MANAGE ROLES` permission). If this channel is not defined, the private sheet function will be disabled.
The embed will be pinned for easy access.

:::Warning About private sheet
If the sheet is not marked as private but is published in a channel that users do not normally have access to, they will still be able to see the sheet with the `/display` and `/graph` commands.
:::


![embed](/assets/register/embed_template.png)

:::warning Caution
The `#user_chan` and `#private_character` channels cannot be changed after registration, as they are saved globally in the database.
:::