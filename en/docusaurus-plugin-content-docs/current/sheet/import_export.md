---
title: Import & Export
sidebar_position: 4
---
## Import and Export Data

The following commands allow you to import and export data from and to a CSV file.

:::tip About Dice
It is entirely possible to import specific dice for the command [`/dbd`](../usage/model/dice.mdx#dbd-dbd), but you need to fill in the `dice` column as follows:
```md
- [dice]: [value]
```
For example:
```md
'- Athletics: 1d20+Strength
- Stealth: 1d20+Dexterity
```
:::

:::important About Excel
- Excel does not handle cells starting with `-` well and may interpret them as formulas. If this happens, you need to add `'` before the `-`.
- Excel may have issues reading and exporting text with accents. It is recommended to save the file in UTF-8-BOM format, using tools like Notepad++ or VSCode.
- Player `id`s may be recognized as numbers and altered. It is advised to save them as text by adding `'` before the `id`, like `'123456789012345678`.

It is highly recommended to disable Excel's automatic conversions:
![Excel](/assets/csv/EXCEL_EN_disable.png)

And to disable the error checking rule "Numbers formatted as text or preceded by an apostrophe" in the error checking options (Formulas > Error Checking Rules):
![](/assets/csv/EN_disable_nb.png)
:::

![Example](/assets/csv/example.png)


### Import

:::usage
**`/import [csv] (delete)`**
- `csv`: The CSV file to import. It must be in UTF-8-BOM format.
- `delete`: If a character already exists, this option allows you to delete the old character message before importing. If this option is omitted, the data will be overwritten without deleting the old message.
:::

The `/import` command allows you to import data from a CSV file. You can download the template using the `/csv` command and fill it with the characters and statistics you wish to import.

:::important
- Imported data will overwrite existing data, but won't delete characters that are not in the CSV file. 
- The minimum, maximum, and total points are not verified (to allow the import of characters who have gained experience or differ from others, such as monsters).
- Combinations should not be entered as is but should be directly calculated. For example, if the HP column is a combination of `Constitution` and `Endurance`, you must enter the result of these columns directly. There is no issue using formulas in a CSV, as the file export will only include the result!
:::

The following columns are necessary for the import:
- `user`: The Discord ID of the player or their username (without the `@`).
- `charName`: Depending on your template, this might be required. It is the character's name.
- `isPrivate`: `true` or `false` to specify if the sheet is private or not. If your template does not use private sheets, you can leave this column empty.
- The following columns must be the statistics of your template.

These columns are optional:
- `avatar` : The link to the character's avatar. If you don't use an avatar, you can leave this column empty. The avatar used in the display will be the player's.
- `channel` : Allows you to set a channel (also supporting thread and forum[^1]) to send the sheet to, rather than using the default channels set when registering the template.
- `dice` : Specific dice for the `/dbd` command. If you don't use this command, you can leave this column empty (or delete it).


### Export Data

:::usage
**`/export (private_sheet_only)`**
- `private_sheet_only`:
  - If `false`, it will include **only** characters whose sheets are **public**.
  - If `true`, it will include **only** characters whose sheets are **private**.
  - If omitted, it will include **all** characters, regardless of the sheet status.
:::

This command allows you to export the list of characters and statistics into a CSV file. 

The exported CSV file uses a semicolon as the separator.

[^1]: It is possible to use a forum, which will automatically create a post for the character. The player (and administrators) will be mentioned in the post. 
