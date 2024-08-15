---
title: Editing an user sheet
sidebar_position: 3
---

Once the user is validated, their character sheet will be automatically published in a thread or in the chosen channel. All character sheets will follow this format:

![user embed](/assets/edit/user_embed.png)

Only the template and the user will always be present, unless no die type and no critical success/failure have been recorded in the template.

If all information is saved, you will have access to three buttons:
- Edit user data : avatar (embed thumbnail), character name or move to another user,
- Edit Statistics
- Edit Saved Dice (which allows saving multiple new dice, but shh...)
- Add a New Die.

## Edit user data

![](/assets/edit/french/user.png)
Each tree commands will open a modal to edit the corresponding data.

If you are using a old version of the bot, you will have to use the following commands:
- [`/edit avatar`](../Usage/model.mdx#edit-avatar-edit_avatar)
- [`/edit rename`](../Usage/model.mdx#rename)
- [`/edit user`](../Usage/model.mdx#user)

To add the new button.

### Editing the avatar image

![edit image](/assets/edit/image.png)

:::warning
Images stored on Discord cannot be used as their links change regularly. It is therefore mandatory to use external links, for example, by using [imgur](https://imgur.com/).
[See here for more information](https://www.bleepingcomputer.com/news/security/discord-will-switch-to-temporary-file-links-to-block-malware-delivery/).
:::

### Rename a character
![rename](/assets/edit/french/rename.png)

As the command, it doesn't allow duplicate character name. Each character must have different name, or error will be throw.

### Move to another user

![move](/assets/edit/french/move.png)

It will **move** the character to another user, deleting the one on the old user. An error will be throw in case of duplicate, and action will be undone.

## Editing Statistics

![edit stats](/assets/edit/stats.png)

The modal will be pre-filled with a list as follows:
```md
- NAME: value
- NAME: value
- NAME: COMBINATION
```

:::warning
It is imperative to keep this list as is so that the bot can correctly read the statistics.
:::

You can remove values by using `X` or leaving it blank, like this:
```md
- NAME: X
```

If statistics have been removed from the template, they will be automatically removed from the list. Additionally, they will be automatically added back when added to the template, with a default value of "0".

It is possible to modify combinations.

Finally, values will not be checked against the total initially recorded in the template. Game masters must therefore verify the values during editing.

:::note
If statistics are edited and logs are enabled, a modification message will be sent to the channel configured in the logs.
:::

## Editing Dice

Just like with statistics, the modal will be pre-filled with a list as follows:
```md
- NAME: dice
```

Just like during recording, dice will be evaluated to verify their validity. Additionally, you can add as many dice as you like!

As with statistics, it is essential to adhere to the list and its syntax. You can delete fields by replacing the value with "X" or "0".

![edit dice](/assets/edit/dice.png)

## Adding a new dice

Adding a die works exactly like when recording a character.
