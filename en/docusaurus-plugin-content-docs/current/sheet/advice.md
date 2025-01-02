---
title: Limitation & Advice
sidebar_position: 5
---

## Limitations
Here are the limitations to consider when registering and editing models and sheets:

- A maximum of 25 statistics and dice are supported (because of the embed fields limitation).
- It is not possible to modify statistics if they do not exist in the original model.
- Sometimes, it is necessary to manually update sheets if the model is modified. Additionally, in some cases, sheets must be entirely re-registered. If you want to modify the locations of sheets and private sheets, you will need to do `/export` then `/import` to update them. For more information, [consult the documentation](./import_export.md).
- When editing a sheet, statistics are not checked against the total or a maximum. Moreover, it is impossible to control the number of points spent per statistic in systems where spending 1 point in a statistic is not equivalent to 1 statistic point.

## Advice
- Avoid saving all dice in the server template, especially if their number is significant. In fact, you can have only 25 registered dice in total per user. It's preferable to specifically save, per player, only the dice they have access to, such as the weapons they use or their skills. For example, it's not necessary for an archer to have access to all combat dice, but only to those related to their bow.

- Sheets are not designed to receive temporary bonuses and penalties or equipment, which should instead be used directly in the `/dbroll` command. The bot does not yet support equipment, and you cannot create "bonus" or "penalty" columns for each statistic. However, it is possible to modify the values of the saved statistics as needed, especially in the case of point distribution after gaining a level.

- While the bot aims to be as universal as possible, certain limitations may mean that the bot may not suit your needs, particularly if you use a system based on numerous skills or specific dice. That being said, you are not required to register ALL special dice.

- Statistical verification is minimal (checking only numerical values, minimum and maximum if applicable): prior verification by the GM is mandatory. Given that character sheet editing is very flexible (no checks against total points, maximums, etc.), GMs must perform verification. If you have configured logs (with `/logs`), you will receive a message in case of modifications, along with a list of the changes made. [See here for more information about journalization](../config/logs.md#edits-logs-and-errors-config-logs).
