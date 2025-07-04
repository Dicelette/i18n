n ---
title: Template
sidebar_position: 1
---

To begin with, you need to **generate** a new template. You can create one by using the form available [right here](../form.mdx).

See the template examples in the `template` files [here](https://github.com/Dicelette/discord-dicelette/tree/main/template).

:::info Note
Statistics and dice are optional:
- <mark>`/dbroll`</mark> will only be available if you **don't** specify a die type with `$`. Otherwise, you will need to register statistics to be able to use it.
- Without dice, you won't be able to use <mark>`/dbd`</mark>. 
:::


## Next steps

Once the template is ready, register it with :

:::usage
**<mark>`/register`</mark> [#channel] [file] (#user_chan) (#personality_private) (?update) (?delete_everything)**
- `#channel`: Channel in which the template will be sent (used for file creation).
- `[file]` : <mark>JSON</mark> file created previously.
- `#user_chan`: Channel where the files will be published.
- `#personality_private`: Channel for private files (see box below).
- <mark>`?update`</mark>: Updates all old character files, if any.
- <mark>`?delete_everything`</mark>: Deletes all old character files, if any.
:::

:::danger About private files
If the sheet is not marked as <mark>private</mark> but is published in a room to which users do not normally have access, they will still be able to view the sheet with the <mark>`/display`</mark> and <mark>`/graph`</mark> commands.
:::

L'embed sera épinglé pour faciliter l'accès.

![embed](/assets/register/embed_template.png)

:::danger
You need to re-register the template if you want to change the default channel for private and public sheets.  
But the registered user doesn't need to be re-registered, as the channel and message ID are saved in the database.

To move all sheets to another channel, use the [<mark>`/export`</mark>](../import_export.md) command.
:::

## TLDR
1. Create the template using [form](../form.mdx) or the <mark>`/generate`</mark> command.
2. Save the template with <mark>`/register`</mark>.
3. Create a player file by clicking on the "Register character" button.
4. Fill in the character information and click on "Validate".
5. Modify command access rights if necessary.

For more information on field syntax: [see dedicated page](../../introduction/format.mdx).

[^1]: It is possible to use a forum, which will automatically create a post for the character. The player (and administrators) will be mentioned in the post.