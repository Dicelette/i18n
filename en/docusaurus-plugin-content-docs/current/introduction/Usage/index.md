---
title: Usage
sidebar_position: 2
---

The functioning of this bot relies on the use of threads. Upon its initial launch, it will search for a thread prefixed with `🎲`:

- If no thread is found, the bot will create a new one and direct all future logs there.
- However, if a thread already exists, the bot will select the most recent one and send the logs there.

:::note Note
In case of multiple threads being found, the bot will use the most recent one and archive the others.
:::

Commands can also be executed within an existing thread. In this case, the bot will simply send the result there, which can then be accessed in channels whose names start with `🎲`.

You can also create a new thread using the command [create a new scene](../../commands/roll.md#creating-a-new-scene).

:::tip Tip
The bot also functions in forums, but with a few differences:
- Multiple logs can coexist simultaneously (unless they have exactly the same name).
- Logs will be automatically named `🎲 [topic name]`, with the `🪡 Dice Roll` tag added automatically (created if it doesn't exist).
- In this case, it's a message that will be created instead of a thread.
:::

Additionally, via the command `/result_channel`, you can set a channel where all logs will be sent, rather than using a thread or forum topic.

## Channels

The bot will also send the result to the channel where the command was initially sent. This message:

- Will be deleted after 3 minutes.
- Will contain a link to the message in the log.

## Usage

The bot can be:

- Used with slash commands (see [commands](../../commands/roll.md)).
- But also directly on the message.