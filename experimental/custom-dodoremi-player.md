---
description: This page explains how to use a custom dodoremi player
tags: experimental
---

# Custom Dodoremi player

{% hint style="info" %}
To install this you need to know how to launch a terminal and have Crystal installed.
{% endhint %}



Some charts are too big for Jackbox's server to handle properly which brings a lot of issues while playing. Julibox fixes those issues and provides a modding API.

Source: [https://github.com/femboyindustries/julibox.tv](https://github.com/femboyindustries/julibox.tv)

* Install Firefox _(the server breaks when using with Chromium-based browsers)_, [CrystalLang](https://crystal-lang.org/)
* Run `shards install` and `shards build`.
* Run the built application in `bin/julibox` .

This will generate a config.

After that in the config add the path of the song audio like this:

`song = D:/Steam/steamapps/The Jackbox Party Pack 10/games/NopusOpus/songs/chart/backing.ogg`

And then launch the julibox proxy using this command: `bin/julibox mock nopus-opus D:/Steam/steamapps/The Jackbox Party Pack 10/games/NopusOpus/songs/chart/config.json`

Modify this to have your chart of choice and test this out.
