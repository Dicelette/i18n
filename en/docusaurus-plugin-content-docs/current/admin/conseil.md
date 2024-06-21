---
title: Advice
sidebar_position: 5
---

- Avoid saving all dice in the server template, especially if their number is significant. In fact, you can have only 25 registered dice in total per user. It's preferable to specifically save, per player, only the dice they have access to, such as the weapons they use or their skills. For example, it's not necessary for an archer to have access to all combat dice, but only to those related to their bow.

- Sheets are not designed to receive temporary bonuses and penalties or equipment, which should instead be used directly in the `/dbroll` command. The bot does not yet support equipment, and you cannot create "bonus" or "penalty" columns for each statistic. However, it is possible to modify the values of the saved statistics as needed, especially in the case of point distribution after gaining a level.

- While the bot aims to be as universal as possible, certain [limitations](./model/limitation.md) may mean that the bot may not suit your needs, particularly if you use a system based on numerous skills or specific dice. That being said, you are not required to register ALL special dice.

- Statistical verification is minimal (checking only numerical values, minimum and maximum if applicable): prior verification by the GM is mandatory. Given that character sheet editing is very flexible (no checks against total points, maximums, etc.), GMs must perform verification. If you have configured logs (with `/logs`), you will receive a message in case of modifications, along with a list of the changes made. [See here for more information about journalization](./config/index.md#administration-logs).