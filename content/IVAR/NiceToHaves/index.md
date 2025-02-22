---
title: Making it Pretty
subtitle: "Of Snow and Snowflakes"
summary: What don't we do to make things pretty?
date: 2025-02-04
cardimage: SnowyLandscape.jpg
featureimage: SnowyLandscape.jpg
caption: The parkour covered in snow
authors:
- Henri: author.jpeg
---
Finally, it was time to make my game look like an actual game.
Since my locomotion remotely resembles ice skating I went with a winter theme.

## Snow Shader
Naturally, my first association with winter is snow.
So I added a snow shader.
I found a nice [tutorial](https://github.com/daniel-ilett/shaders-snow-layers) and followed it to build the appropriate shader graph.
![You can see the URP shader graph of the snow shader](./images/ShaderGraph.png "The snow's shader graph")

However, to do this I had to upgrade the project to Unity's Universal Render Pipeline.
Fortunately, Unity provided a guide on how to do this.
Nonetheless, I had to reimport TextMeshPro (which to be honest happened more than once over the course of the project).
Also, this shader is not a post-processing shader and therefore has to be applied to each material individually it is supposed to affect.

Because the shader allows to set the snow amount, I added a little script to shift the landscape to snow over the first few seconds the player is on the parkour.
![You can see the snowy parkour](./images/SnowyLandscape.jpg "The parkour covered in snow")

## Snowflake Coins
Next, I replaced the coins with snowflakes, which seemed more appropriate to me.
To do this, I created a CAD model of a snowflake in SketchUp and converted it to a `.obj`.
Then it was rather simple to change the coin prefab to a snowflake, automatically replacing all the coins with snowflakes at once.
![You can see a snowflake coin](./images/SnowflakeCoins.jpg "The snowflake coins")

## Winter Soundscape
To make it feel even more like winter, I changed the soundscape as well.
The first thing was to replace the background music - a soundtrack I've grown to feel annoyed at over the project.
Instead, I opted for a free [winter loop](https://freesound.org/people/AudioCoffee/sounds/770696/).
This already felt significantly more festive.

But the other thing I changed was the coin collection sound.
Since the coins weren't coins anymore but snowflakes, I chose a short sample of [ice cracking](https://freesound.org/people/wwstudioswastaken/sounds/624163/).
Together, the parkour instantly felt way more like a winter experience.

## App Icons & Splash Screens
Finally, to complete my winter attire, I designed fitting app icons and a loading splash screen.+
I started with the splash screen and christened the project *VR-Redirected-Winter*.
I also added a little snowflake as the part of the design
![The splash screen with a little snowflake and the phrase "VR-Redirected-Winter"](./images/VRSplashTitle.png "The splash screen")

For the app icons I chose to only use the little snowflake and had the individual resolutions required for an app icon [generated](https://romannurik.github.io/AndroidAssetStudio/icons-launcher.html).
![An android app icon with a little snowflake](./images/VRAppIcon.png "The app icon")