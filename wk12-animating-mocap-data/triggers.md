[Back](https://uwetom.github.io/media-production-worksheets)

# Using Triggers with Animation Controllers and MoCap Animations 

In this tutorial we're going to download a new character from Mixamo.com and we're going to apply a set of animations to it from scratch.

Then we are going to use a trigger function to trigger the motion capture animations to play on a keypress. Like this (the animation changes when I press '1' on my keyboard):

<iframe src="https://uwe.cloud.panopto.eu/Panopto/Pages/Embed.aspx?id=3ac7a880-29b9-43b8-9a92-b2430004b235&autoplay=false&offerviewer=true&showtitle=true&showbrand=true&captions=false&interactivity=all" height="405" width="720" style="border: 1px solid #464646;" allowfullscreen allow="autoplay" aria-label="Panopto Embedded Video Player" aria-description="MP-Mocap-2.0 Intro Wednesday, 11 December 2024 at 00:16:47" ></iframe>

The first step is download a T pose character  import these into Unity and prep it for use 

<iframe src="https://uwe.cloud.panopto.eu/Panopto/Pages/Embed.aspx?id=951a8601-c0d1-4106-8b58-b242017a9a80&autoplay=false&offerviewer=true&showtitle=true&showbrand=true&captions=false&interactivity=all" height="405" width="720" style="border: 1px solid #464646;" allowfullscreen allow="autoplay" aria-label="Panopto Embedded Video Player" aria-description="MP-Mocap-2.1  10 December 2024 at 22:57:11" ></iframe>

Then download an animation, and import it into Unity and prep ready for use.

<iframe src="https://uwe.cloud.panopto.eu/Panopto/Pages/Embed.aspx?id=446e35cb-aa22-41cd-a6f2-b242017e3900&autoplay=false&offerviewer=true&showtitle=true&showbrand=true&captions=false&interactivity=all" height="405" width="720" style="border: 1px solid #464646;" allowfullscreen allow="autoplay" aria-label="Panopto Embedded Video Player" aria-description="MP-Mocap-2.2 Tuesday, 10 December 2024 at 23:10:50" ></iframe>

Then we will build an animation controller to run the animations and animate the character.

<iframe src="https://uwe.cloud.panopto.eu/Panopto/Pages/Embed.aspx?id=a1405d08-aee1-4e63-832d-b2420180121e&autoplay=false&offerviewer=true&showtitle=true&showbrand=true&captions=false&interactivity=all" height="405" width="720" style="border: 1px solid #464646;" allowfullscreen allow="autoplay" aria-label="Panopto Embedded Video Player" aria-description="MP-Mocap-2.2 animation controller 10 December 2024 at 23:18:06" ></iframe>

Next we will add a trigger to one of the transitions / animations.

<iframe src="https://uwe.cloud.panopto.eu/Panopto/Pages/Embed.aspx?id=a978cc3c-a1d8-4c28-874a-b24201836239&autoplay=false&offerviewer=true&showtitle=true&showbrand=true&captions=false&interactivity=all" height="405" width="720" style="border: 1px solid #464646;" allowfullscreen allow="autoplay" aria-label="Panopto Embedded Video Player" aria-description="MP-Mocap-2.3 triggers Tuesday, 10 December 2024 at 23:30:18" ></iframe>

Finally we will create a script that sets the trigger

<iframe src="https://uwe.cloud.panopto.eu/Panopto/Pages/Embed.aspx?id=d35d633d-77ca-4215-9b51-b2420185cde7&autoplay=false&offerviewer=true&showtitle=true&showbrand=true&captions=false&interactivity=all" height="405" width="720" style="border: 1px solid #464646;" allowfullscreen allow="autoplay" aria-label="Panopto Embedded Video Player" aria-description="MP-Mocap-2.4 scripting Tuesday, 10 December 2024 at 23:38:50" ></iframe>

## Adding a bool trigger 

Instead of a 'Trigger' it is possible set a bool to true or false to start and stop an animation.

This maybe more useful, giving you complete control over the animations.

To do this we will add a bool parameter to the animation controller

<iframe src="https://uwe.cloud.panopto.eu/Panopto/Pages/Embed.aspx?id=900f15dc-e08f-48a5-84c0-b2420189d2b9&autoplay=false&offerviewer=true&showtitle=true&showbrand=true&captions=false&interactivity=all" height="405" width="720" style="border: 1px solid #464646;" allowfullscreen allow="autoplay" aria-label="Panopto Embedded Video Player" aria-description="MP-Mocap 2.5 - bools Tuesday, 10 December 2024 at 23:53:44" ></iframe>

Then edit the script to set the bool to true when the Return key is pressed.

<iframe src="https://uwe.cloud.panopto.eu/Panopto/Pages/Embed.aspx?id=2a635d01-05b9-4eb9-8360-b24300006747&autoplay=false&offerviewer=true&showtitle=true&showbrand=true&captions=false&interactivity=all" height="405" width="720" style="border: 1px solid #464646;" allowfullscreen allow="autoplay" aria-label="Panopto Embedded Video Player" aria-description="MP-Mocap-2.6 scripting Wednesday, 11 December 2024 at 00:01:21" ></iframe>
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTAzMTI4MDA3Miw0NDg4OTEzODAsMTE3NT
UyODAwNywtMTcxMTYzNDk3MywtMTgyMzI3Mjk5MSwtMTI3MDk5
MDQyN119
-->