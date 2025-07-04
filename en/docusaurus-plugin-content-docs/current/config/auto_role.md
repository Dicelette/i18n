---
title: "Auto Role"
sidebar_position: 3
---

:::usage
**<mark>`/config auto_role dice`</mark> (@role)**  
**<mark>`/config auto_role stats`</mark> (@role)**
- `@role` : The role to assign during the validation of the dice or stats.
:::

These commands allow to automatically add role when:
- A dice is added (with <mark>`/config auto_role dice`</mark>)
- Stats are validated (with <mark>`/config auto_role stats`</mark>)

This allows to restrict the usage of <mark>`/dbd`</mark> and <mark>`/dbroll`</mark> to the user that have the possibility to use it.

If role is not specified, the auto-role will be disabled.