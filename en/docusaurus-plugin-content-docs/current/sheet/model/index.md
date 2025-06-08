---
title: Template
sidebar_position: 1
---

To get started, you need to **create** a new template. Use `/register` followed by the template's name. You can also create an empty template using `/generate` or the form available [here](../form.mdx).

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

## TLDR

1. Create the template using [form](../form.mdx) or the `/generate` command.
2. Save the template with `/register`.
3. Create a player file by clicking on the “Register character” button.
4. Fill in the character information and click on “Validate”.
5. Modify command access rights if necessary.

[^1]: A forum can also be used, automatically creating a post for the character. The player (and admins) will be mentioned in the post.

