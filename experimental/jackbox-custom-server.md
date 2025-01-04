---
description: This page shows how to launch custom Jackbox server.
tags: experimental
---

# Jackbox custom server

For some testing purposes you may need a custom server. Here are some ways you can launch one

## Smpial's Jackbox Server

This is the most recent server currently available.

Source: [https://github.com/smpial/jackbox-private-server](https://github.com/smpial/jackbox-private-server)

{% hint style="info" %}
To install this server you need to have Node.JS installed and know how to launch a terminal
{% endhint %}

Rename config.example.json to config.json

In config.json you need to change:

* `serverUrl` - Your server address (Please note that `serverUrl` is also found in the configs of the games Quiplash3, Everyday, WorldChampions, JackboxTalks and BlankyBlank)
* `polly:accessKeyId` and `secretAccessKey` -  AWS keys (Needed for voice generation)
* `polly:uploadUrl`  - Upload URL, which accepts `multipart/form-data` with 'file' and the name of this file, uploads it to the server and returns a link to the file or changes a status code if an error occurs
* `internalToken` - Your token (used in debug, external requests and polly responses upload)
* `allowedOrigins` - list of your urls for `Access-Control-Allow-Origin` header
* `license` - A hard key used to force room code.

To boot a game using this server, add the `serverUrl` to `jbg.config.jet` in your game of choice, or add `-jbg.config serverUrl=localhost` to launch parameters.

***

## InvoxiPlayGames' custom server

This is an old but gold server made by InvoxiPlayGames (Emma). It only supports one room at a time and most basic features.

Source: [https://github.com/InvoxiPlayGames/johnbox](https://github.com/InvoxiPlayGames/johnbox/)

* `npm install ws` to install the WebSockets NodeJS module.
* Generate a TLS certificate for the web server to use.
* Edit the top of `johnbox.js` to change accessibleHost to a host accessible by all players (e.g. public IP)
  * This host must have a valid identity in the TLS certificate generated above
* `node johnbox` to start the server.
* Redirect the game to connect to your server. `jbg.config.jet` in each minigame folder has a `serverUrl` parameter.

_Based on the README provided by the developer_&#x20;

***

## StratusFearMe's custom server

{% hint style="info" %}
I have not yet tested this server, please use with caution!
{% endhint %}

Based on the InvoxiPlayGames' server, this project support Party Pack 2 - 10 with TTS and other features.

Source: [https://github.com/StratusFearMe21/jonahbox](https://github.com/StratusFearMe21/jonahbox)



_Based on the README provided by the developer ↓_

#### Configuration

The configuration file is located in `config.toml`, and an example configuration is already in that file. Make sure you edit this before you run the server.

You should also edit the `jbg.config.jet` file in each minigame folder. and set the `serverUrl` parameter to the accessible host you set in `config.toml` (set the `joinUrl` parameter to change the URL displayed by the game to something different)

#### Running

Building and running is relatively simple. Just install Rust and run

```
cargo run --release
```

Or look in [releases](https://github.com/StratusFearMe21/jonahbox/blob/master/releases) for a binary.

#### TTS

Mad Verse City and FixyText require a tts endpoint in order to generate the audio for the raps/the text messages. In native mode, this can be done using the [piper](https://github.com/rhasspy/piper) project. First set that up, then go [here](https://github.com/rhasspy/piper/blob/master/VOICES.md) and download the voices and their associated config files to the `voices_path` (Note that the expected name for config files is {voice}.onnx.json, and that it's not named that already). Voices are chosen at random from the `voices_path`, but they will be consistent for each player. You will also need [ffmpeg](https://ffmpeg.org/) installed.

#### Caching games

There are shell scripts in this project that serve to cache game assets in the server's cache that can't be retrieved in one playthrough.

You can run each script with your `steam/steamapps/common` directory, and the server's accessible host (HTTPS required) as arguments.

The server should be running when you run these scripts.

```
sh update_dodoremi.sh "$HOME/.steam/steam/steamapps/common" "192.168.1.10"
```

* `update_dodoremi.sh`
  * Dependencies:
    * find
    * jq
    * parallel
    * curl
  * Caches the sounds for every instrument that can be loaded in the game
* `update_junktopia.sh`
  * Dependencies:
    * find
    * parallel
    * curl
  * Caches every item that can be bought in the game
* `update_timejinx.sh`
  * Dependencies:
    * find
    * parallel
    * curl
  * Caches every impostor image in the game
