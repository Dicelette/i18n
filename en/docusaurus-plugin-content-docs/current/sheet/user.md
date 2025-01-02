---
sidebar_position: 2
title: Registering an user
---
Now that the template is created, you can register users. As we saw earlier, the template embed contains a "Register a Character" button.

Once the button is activated, you will have a series of modals to fill out.

:::info
The username is the actual username, not the display name. The one you may have been forced to change when Discord removed numbers after pseudonyms...
:::

The first modal will always be the same regardless of the template:
- It will ask for the character's name (mandatory or optional, depending on the template settings)
- The user's name, which must be either their ID or their username. This data is mandatory and will be pre-filled by the bot with the username of the person who clicked.
- If you have enabled the use of private sheets (see [here](./model/index.md#next-steps)), you will have a third field to choose whether the sheet should be private or not. If the sheet is private, simply put `x` in the field. Leave it empty otherwise!
- You can provide a link to an image (an avatar) that will serve as the image in the sheet's embed. If left blank, the image used will be the player's avatar.
- Finally, it is possible to send the character sheet to a channel other than those defined in the template by `private_channel` and `public_channel`.[^1] If you don't want to send the form to a specific channel, leave the field empty.

	:::warning
	The form can only be hidden **if** the form is private. Even if the record is sent to a channel inaccessible to other users, they will be able to view it without this option.
	:::


![Page_1](/assets/register/register_user_P1.png)

The second modal will depend on the template: if there are more than 5 saved characteristics, you will have multiple pages to fill out. Each time, you will simply enter the value of the statistic. These values will then be checked (min/max and if they are indeed numbers). Unfortunately, for now, Discord does not allow direct verification of this in the modal, so you will have to wait until the end to see if everything is correct.
![fin embed](/assets/register/fin_stat.png)


Once the registration is complete (meaning all statistics have been filled out), moderators have the option to validate or register dice.

![modal_dice](/assets/register/add_dice.png)

Each die must be registered manually.

![fin](/assets/register/fin_embed.png)

Once all of this is done, simply click "Validate" and the sheet will be reposted in the channel chosen during registration (or in a thread named `📝 • [STATS]` if no channel was chosen during template registration).

[^1]: It is possible to use a forum, which will automatically create a post for the character. The player (and administrators) will be mentioned in the post. 
