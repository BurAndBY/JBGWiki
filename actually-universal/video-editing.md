---
description: This part of the guide teaches you how to edit the videos in the game
tags: video
---

# Video editing

## Extracting video

First, open up VGMToolbox. After that, navigate to Misc. Tools - Stream Tools - Video Demultiplexer. There, select **USM** as the Format and drop your file.&#x20;

![](/assets/image_(20).png)

This will give you a M2V file which you can convert to MP4/AVI with your converter of choice.

### Power user lifehack

I haven't seen this brought up a lot, but you can also do this using FFMPEG. Open up a terminal of your choice and run:

`ffmpeg -i pickergame.usm pickergame.mp4`



If you do not like using a terminal, you can use a GUI for FFMPEG like QWinFF or FFQueue. **Please note that I have not used any of those apps and cannot say if they are safe.**

## Compiling video

To compile a video back to USM you need to use Scaleform Video Encoder. Convert your video file to AVI and WAV. Add the AVI file into the **Input Name** field, then change the codec to **H.264**. Also add the WAV file to the Other Audio **Mono/Stereo** field. Then press the **Encode** button.&#x20;

{% hint style="info" %}
For some reason this tool breaks when using it with Proton. If you have any idea on how to fix it, please add a change!
{% endhint %}

![](/assets/image_(22).png)

After that you will get a USM file that you can copy into the mod.

As you can see it works:

![](/assets/image_(24).png)
