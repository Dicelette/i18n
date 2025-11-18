---
title: FAQ
sidebar_position: 6
---
## Is the bot free?

Yes, and it always will be. **No** command will ever be placed behind a paywall. First, because I can't be bothered, and second, because I firmly believe that role-playing tools should stay accessible to everyone.

## Where is the data stored?

On my personal Raspberry Pi, hosted at my home in France. I use a lightweight SQLite3 database to store only the essential information (message IDs, links between users and characters, server configurations, etc.). No sensitive data is stored.

Some data is stored in cache and regularly cleared to improve performance.

## Is it possible to cheat?

No.

Before version 2.13.0, the bot relied on JavaScript’s native `Math.random()` pseudo-random number generator. However, that generator isn't secure and may become predictable in certain conditions.

Since version 2.13.0, Dicelette uses a [**CSPRNG** (Cryptographically Secure Pseudo-Random Number Generator)](https://en.wikipedia.org/wiki/Cryptographically_secure_pseudorandom_number_generator?useskin=vector) via [Node Crypto](https://nodejs.org/api/crypto.html).

**So, cheating with the bot is not possible.**

:::note
The bot internally uses the [@diceRoller](https://dice-roller.github.io/documentation/) API to handle randomness, which itself relies on [random-js](https://www.npmjs.com/package/random-js).  
The default engine is `crypto`, which uses Node.js’s built-in CSPRNG.  
You can find the source code where the engine is initialized [here](https://github.com/Dicelette/core/blob/c12610ea645ee7c1cda219a821b4a8aff5f95de0/src/dice.ts#L160).
:::