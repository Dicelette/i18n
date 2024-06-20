---
title: Limitation
---

Here are the limitations to consider when registering and editing models and sheets:

- A maximum of 25 statistics and dice are supported (because of the embed fields limitation).
- It is not possible to modify statistics if they do not exist in the original model.
- Sometimes, it is necessary to manually update sheets if the model is modified. Additionally, in some cases, sheets must be entirely re-registered. If you want to modify the locations of sheets and private sheets, you will need to do `/export` then `/import` to update them. For more information, [consult the documentation](../../commands/administration.md#import-and-export-data).
- When editing a sheet, statistics are not checked against the total or a maximum. Moreover, it is impossible to control the number of points spent per statistic in systems where spending 1 point in a statistic is not equivalent to 1 statistic point.