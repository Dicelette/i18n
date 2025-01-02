---
title: Behavior
sidebar_position: 2
---

:::info
The [configuration](../config/index.md) allows to edit the bot's behavior. This documents explains the default behavior.
:::

The functioning of this bot relies on the use of threads. Upon its initial launch, it will search for a thread prefixed with `🎲`:

- If no thread is found, the bot will create a new one and direct all future logs there.
- However, if a thread already exists, the bot will select the most recent one and send the logs there.

:::note
In case of multiple threads being found, the bot will use the most recent one and archive the others.
:::


Commands can also be executed within an existing thread. In this case, the bot will simply send the result there, which can then be accessed in channels whose names start with `🎲`.

You can also create a new thread using the command [create a new scene](../usage/index.md#creating-a-new-scene).

:::tip Tip
The bot also functions in forums, but with a few differences:
- Multiple logs can coexist simultaneously (unless they have exactly the same name).
- Logs will be automatically named `🎲 [topic name]`, with the `🪡 Dice Roll` tag added automatically (created if it doesn't exist).
- In this case, it's a message that will be created instead of a thread.
:::

Additionally, via the command `/config result_channel`, you can set a channel where all logs will be sent, rather than using a thread or forum topic.

## Channels

The bot will **also** send the result to the channel where the command was initially sent. This message:

- Will be deleted after 3 minutes (configurable using `/config delete_after`).
- Will contain a link to the message in the log.

## Usage

The bot can be:

- Used with slash commands (see [commands](../usage/index.md#dice-rolling)).
- But also directly on the message.

## Reaction

There are two functions on reactions:
- `📩`: Allows to receive the roll message in DM. In case the result saving is enabled, the message sent will be this save, useful especially in case you have enabled the link to the context!
- Link between reactions: In case the roll saving is enabled, the reactions on the roll message will be linked to the roll save. As long as the bot has access to the emoji, it will be able to react with it on the save message to link it to the roll message. Removing the reaction will also remove it from the roll message.
