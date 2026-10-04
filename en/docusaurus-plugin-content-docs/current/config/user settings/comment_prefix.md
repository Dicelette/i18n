---
title: Comment prefix
sidebar_position: 4
---
By default, you can edit the comment of a roll by replying to the result message with a comment prefixed by `///`. Each user can customize this prefix.

:::usage
**`/settings prefix_edit_comment configure (prefix)`**
- `prefix`: The prefix to use to edit comments. It can be any string of characters. Regex are supported.
:::

When the `prefix` option is left empty, the comment edit prefix is reset to the default value (`///`).

Regex are supported with the following syntax: `$/regex/flags$`.

:::example[ `$/\({2}(.*)\){2}/$` which will match `((comment))` and replace the comment with `comment` ]
:::

If you use a regex, there are two possibilities:
- If you capture a group (`(.*)` in the example), the comment is replaced by the content of the captured group.
- If you don't capture a group, the comment is replaced by the text matched by the regex, including the text of the regex itself. For example, with the regex `$/\({2}.*\){2}/$`, the comment is replaced by `((comment))` and not by `comment`.

## Display

To display the comment edit prefix, you can use the command `/settings prefix_edit_comment display`.

:::tip
To simplify the display, the regex is shown without its detection delimiters (`$` and `$`). For example, the regex `$/\({2}(.*)\){2}/gm$` is displayed as `/\({2}(.*)\){2}/gm`.
:::
