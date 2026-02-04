---
title: Snippets
sidebar_position: 2
credit: neantderthals
---
The ==snippets== are reusable dices that aren’t tied to a specific character or model.
They can be created and used by the users to simply frequents dice roll without needing to configure a model.

:::important
The statistics aren’t taken into account in the snippets as they aren’t tied to a character. However, the [attributes](attributes.md) are.
:::

:::danger
The [attributs](./attributes.md) can be used in a snippet as long as the snippet has been already saved.
:::

# Snippets creation

:::usage
**`/user_config snippets create [name] [dice]`**
- `name` : name of the snippet
- `dice` : Dice roll expression (ex : `1d20+5`)
:::

If the snippet already exist, it’ll be updated to it’s new value

![create_snippet](../../assets/snippets/create.png)

# Suppression

:::usage
**`/user_config snippets delete [*name]`**
- `*name` : name of the snippet to delete
:::

Allow to delete a snippet off the list.

![delete_snippet](../../assets/snippets/delete.png)

# Snippet list

:::usage
**`/user_config snippets lister`**
:::

Show the list of snippets for the user

![list_snippet](../../assets/snippets/list.png)

# Export snippets

:::usage
**`/user_config snippets export`**
:::

Allows to export all the snippets from the user in a JSON file to save or share them.

![export_snippet](../../assets/snippets/export.png)

# Import snippets

Importe des snippets depuis un fichier JSON. Cela permet de transférer ou partager facilement des données entre différents serveurs ou comptes.
Import snippets from a JSON file. This allows easy sharing or transfer of data between servers or accounts.

:::usage
**`/user_config snippets import [file] (?erase)`**
- `file` : Data JSON of the snippets to import.
- `?erase` : Replace the existing data instead of fusing them.
:::

The data will be fused by default. If two snippets have the same name, the new imported snippet with the name will replace the previous one.

During import, snippets will be verified and only the conforms ones will be added.

![import_snippet](../../assets/snippets/import_cmd.png)
![import_snippet_2](../../assets/snippets/import.png)
