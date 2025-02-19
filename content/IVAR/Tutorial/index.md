---
title: In-Game Tutorial
subtitle: "Of Floating Videos and Screen Captures"
summary: How I implemented tutorial messages to show users the 'right' way to play.
date: 2025-02-14
cardimage: [comment] <> TODO add image
featureimage: [comment] <> TODO add image
caption: [comment] <> TODO add caption for image
authors:
- Henri: author.jpeg
---
After our presentations I realized, that my control scheme isn't as intuitive as I thought it would be.
During the short period everyone had to try the game, many got stuck on the first phase of setting up the play area - despite me having explained it in detail verbally.
And even after that it didn't seem obvious to most, how my locomotion actually works.
I don't think anyone even made it till the interaction part.

Therefore, I decided to implement a tutorial.

## Floating Screens
To do so, I took inspiration from Meta's `PoseExample Scene`, which is part of their Interaction SDK.
[comment] ADD image of meta scene

I went ahead and replicated their design.
It consists of a floating screen, similar in design to a larger version of the buttons on the player's left wrist.
It is split into two areas.
The upper part is a screen for a video to play.
The lower part is to display texts.
Both are constrained by a vertical layout group.

[comment] ADD image of unity hierarchy

Interestingly, the screen consists of both a flat image and a video playback.
As far as I've understood, the image acts as a placeholder for the texture, the video is projected onto.
For some reason unknown to me, the video screen started out with a fixed width of 100px.
In the reference implementation by Meta, the video screen automatically fit itself to the available space.
I think, I most likely missed a setting somewhere, but was able to bypass this by manually adjusting the width of the video.
I also added some padding around the screen and the text, to make it more pleasing to the eye.

The lower text section is divided into two vertical slices again.
The upper of those two contains a title, while the lower contains text instructions.

Overall, I placed three floating tutorial screens around the parkour.
The first one is displayed in the play area selection phase and vanishes, once the area has been confirmed.
The second one is right to the left of the player at the start of the parkour and instructs him or her on how to move.
The third and last one is placed at the first interaction.
It shows how to interact with the T-shapes.

## Video Capture
To enrich the tutorial messages with video playbacks, I had to record the appropriate sections of the game.
At the start I was worried, that the passthrough might capture my surroundings, as it had before.
However, run standalone on the Meta Quest and using the built-in capture capabilities, I was worried about nothing. 
The passthrough appeared normal to me but was plain black in the recording.
Which means, I moved around the furniture in the kitchen for nothing ... oh well.

The videos still contained parts such as starting and stopping the recordings.
Since I wanted them to be as short and precise as possible I reduced them to the relevant sections.
For this I used VLC's build-in function of creating clips from videos.

After adding them to Unity, I'm satisfied with the final result.

[Comment] ADD video of tutorial screen
