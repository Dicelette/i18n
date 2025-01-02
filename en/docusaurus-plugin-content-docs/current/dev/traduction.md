---
sidebar_position: 3
title: Translation
---

The bot is fully available in French and English. Slash commands will be automatically translated into the language of the client being used.

:::tip
For example, a user whose client is in French will receive responses in French, while a user whose client is in English will receive responses in English.
:::

However, for "direct" messages (i.e., messages that are not slash commands), the bot cannot determine which language to use. Therefore, it will use the server's language, which can only be selected for Community Servers.


To add a new language, you need to copy and translate the [`en.json`](https://github.com/Dicelette/discord-dicelette/blob/main/src/localizations/locales/en.json) file.

:::important
The name must follow the format of [discord.js locales](https://github.com/discordjs/discord-api-types/blob/main/rest/common.ts#L300). For example, `ChineseCN` for Chinese (China) and `ChineseTW` for Chinese (Taiwan).
:::

Next, you need to add the language to the [`i18next.ts`](https://github.com/Dicelette/discord-dicelette/blob/main/src/localizations/i18next.ts) file as follows:
```ts
import NewTranslation from "./locales/newTranslation.json";

export const resources = {
	// ...
	discordLocale: { // e.g. fr, en-US, etc.
		translation: NewTranslation,
	},
};
```