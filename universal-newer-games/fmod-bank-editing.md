---
description: This page explains how to modify banks for games
tags: audio
---

# FMOD Bank editing

Some sound effects, music and accesibility voice lines are located in BANK files and can be hard to modify.&#x20;

{% hint style="info" %}
Currently it's only possible to do simple audio file modding. To make bigger modifications you need to have a FMOD project, which we currently do not have.
{% endhint %}

First, make sure you have FMOD Bank Tools downloaded and extracted (if no, you can find a link to it in [tools.md](../tools.md "mention")).

After that, open the game folder and in it you will be able to find several bank files, copy them and paste all the files to the bank folder in the tool folder, so then your files will look like this:

![](/assets/image_(4).png)

After that open the EXE in the Fmod\_Bank\_Tools folder and press the **Extract** button.

{% hint style="info" %}
This may take a lot of time depending on the amount of banks you have in the folder. Please be patient!
{% endhint %}

Then, open the **wav** folder, where you will have a folder for each bank you have. You can then edit the audio files in your audio editor of choice.

{% hint style="warning" %}
You should keep the audio the same length as the original or some audio files may get cut off.
{% endhint %}

After that return to the FMOD Bank Tool and press the **Rebuild** button. Then, copy the files in the bank folder back to your game folder and test in game!

