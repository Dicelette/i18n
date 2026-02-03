---
title: Snippets
sidebar_position: 7
---

==Snippets== are reusable dice that are not tied to any character or specific model. They can be created and used by users to simplify frequent dice rolls without needing to configure a model.

:::important
Stats are not supported in snippets because they are not linked to a character.
:::

:::danger
[Attributes](attributes.md) can be used in a snippet if one has been previously saved.
:::

# Creating snippets

:::usage
**`/user_config snippets create [name] [dice]`**
- `name`: Name of the snippet
- `dice`: Dice to be rolled (e.g. `1d20+5`)
:::



If the snippet already exists, its dice value will be updated.

![create_snippet](../../assets/snippets/create.png)

# Deletion

:::usage
**`/user_config snippets delete [*name]`**
- `*name`: Name of the snippet to delete
:::

Allows you to delete an existing snippet from the list.

![delete_snippet](../../assets/snippets/delete.png)

# Listing snippets

:::usage
**`/user_config snippets list`**
:::

Displays the list of existing snippets for the user.

![list_snippet](../../assets/snippets/list.png)

# Exporting snippets

:::usage
**`/user_config snippets export`**
:::

Export all snippets in JSON format, for backup or sharing elsewhere.

![export_snippet](../../assets/snippets/export.png)

# Importing snippets

Allows you to import snippets from a JSON file, enabling users to easily transfer or share their snippets across different servers or accounts.

:::usage
**`/user_config snippets import [file] (?overwrite)`**
- `file`: JSON data of snippets to import
- `?overwrite`: Overwrite existing data instead of merging them.
:::

By default, the data will be merged, but if two snippets share the same name, the new one will overwrite the old one.
The snippets will be checked during import, and only valid ones will be added.

![import_cmd](../../assets/snippets/import_cmd.png)
![import_snippet](../../assets/snippets/import.png)
