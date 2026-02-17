---
title: The 14/02/2026 catastrophe
description: The shutdown of Saturday 14/02/2026 and some thoughts about it
tags: ["maintenance"]
hide_table_of_contents: false
authors:
  - name: Mara-Li
    image_url: https://avatars.githubusercontent.com/u/30244939?s=64&v=4
    url: https://github.com/Mara-Li
    socials:
      github: Mara-Li
      bluesky: Mara-Li.fr
---

To be honest, I would have liked to find another way to integrate an "announcements" category on the site other than through this info.

As some of you may have seen, on Saturday 14/02/2026, the bot was * for a large part of the day. I will now explain the catastrophe that this day was and the reasons for this shutdown.

<!--truncate-->

First of all, you should know that the bot is hosted at my place (in France) on a Raspberry Pi 5. It's a small computer that consumes very little energy and is perfect for running a Discord bot 24/7 (among other things). However, it has its limits, related to my internet connection and electricity (that is to say that in case of network/electricity outage, the bot is down, but that's not the case here... Even if it has already happened 🥲).


On Saturday 14/02/2026, around 9am, I wanted to update the server (firmware update) because it hadn't been done for a while. Unfortunately, the update failed and corrupted the operating system that was on an M2 hard drive (remember the information, it's important).

I tried to repair the system using an SD card via an SD reader, but... It also decided to die. So I had to disassemble my computer to remove the M2 hard drive (which, **fortunately** does not contain the OS of my PC otherwise...) to place the one from the Raspberry. I was therefore able to recover the data from the M2 hard drive (and therefore from the bot and the others) and transfer it to the pc.

Not finding a way to repair the operating system of the Raspberry, I decided to reinstall a new image on the hard drive, but it failed **several times**. Fortunately, I managed to repair it through a large formatting and repairs of defective sectors (once by windows, once by linux and once totally failed which forced me to reinstall the OS). I THEN finally managed to reinstall a stable image of the system and start the second restoration (since the first one, around 7pm, had failed).

Since it takes time (especially since I had to copy the data to my desktop and I tried to make an image of a 120gb disk), I decided to host the bot on my own PC in the meantime. Except that to connect the M2, I have to restart the computer every time, which... Made the bot rather unstable. Especially since some data from my computer was on the other M2, forcing me to do restarts to be able to access this data (and therefore the bot).

Anyway, after a day of struggle, I managed to get the bot back online around 10pm. I'm really sorry for this day of shutdown. I shouldn't have done this firmware update without making a real back-up, even if I admit that I didn't think the SD reader was going to die the same day.
At least, no data was lost!

But in fact, I had to:
- Buy a new 32gb SD card (because a 4gb one is not at all sufficient, even for back-up).
- AND buy a new SD card reader.

Not having *still not received* (long story short) my salary, and even if it's not much, I lost 30€ because of this shutdown, which is not fun for someone who has NO income at all.

I clearly don't like to beg, since the bot is meant to be **FREE** for **EVER**, if you like the bot and want to support me, I have a KO-FI: [https://ko-fi.com/mara__li](https://ko-fi.com/mara__li) (even 1€ is a big support for me, and I would be very grateful to you).
