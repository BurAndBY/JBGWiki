---
description: This page explains how to edit subtitles for any game in the Jackbox series
tags: text
---

# Editing subtitles

After changing audio files in the game, I recommend adding subtitles for accesibility.

To do this, we will use [Juli3's SWF Tool](https://www.juli3.net/swf).

First, open the `games/{gamename}/TalkshowExport/project/data` folder. Then drag and drop the `start.swf` into the website.

![](/assets/image_(35).png)

This will give you a JSON, that you can edit using your editor of choice:

![](/assets/image_(36).png)

Make your modifications then recompile it back to swf by dropping the JSON back into the tool.

Then drop the SWF back into the folder and check in game!
