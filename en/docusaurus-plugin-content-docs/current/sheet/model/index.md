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

Once the template is ready, register it with this [command](./ref.md#template-registration).

## TLDR
1. Create the template using [form](../form.mdx) or the <mark>`/generate`</mark> command.
2. Save the template with <mark>`/template register`</mark>.
3. Create a player file by clicking on the "Register character" button.
4. Fill in the character information and click on "Validate".
5. Modify command access rights if necessary.

For more information on field syntax: [see dedicated page](../../introduction/format.mdx).

[^1]: It is possible to use a forum, which will automatically create a post for the character. The player (and administrators) will be mentioned in the post.