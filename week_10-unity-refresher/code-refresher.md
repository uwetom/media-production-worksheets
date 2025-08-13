[Back](https://uwetom.github.io/media-production-worksheets)

# C# Code Refresher

## Setup

This first video introduces the tasks we are going to undertake in this exercise:
To create a series of gameobjects at run time, detect collisions and use the collisions to trigger other events on different gameobjects (turning lights on and off).

<iframe src="https://uwe.cloud.panopto.eu/Panopto/Pages/Embed.aspx?id=8e41e24c-367c-49c7-a7b2-b201015b619c&autoplay=false&offerviewer=true&showtitle=true&showbrand=true&captions=false&interactivity=all" height="405" width="720" style="border: 1px solid #464646;" allowfullscreen allow="autoplay" aria-label="Panopto Embedded Video Player" aria-description="MP code refresher - 1" ></iframe>

Video 2 shows the scene set up:

<iframe src="https://uwe.cloud.panopto.eu/Panopto/Pages/Embed.aspx?id=06912c60-ef61-40a2-84a4-b2010160bdbc&autoplay=false&offerviewer=true&showtitle=true&showbrand=true&captions=false&interactivity=all" height="405" width="720" style="border: 1px solid #464646;" allowfullscreen allow="autoplay" aria-label="Panopto Embedded Video Player" aria-description="MP code refresher -2" ></iframe>

## Prefabs
Video 3 explains how to create a prefab:

<iframe src="https://uwe.cloud.panopto.eu/Panopto/Pages/Embed.aspx?id=ed46776a-1729-447c-8e89-b2010162e642&autoplay=false&offerviewer=true&showtitle=true&showbrand=true&captions=false&interactivity=all" height="405" width="720" style="border: 1px solid #464646;" allowfullscreen allow="autoplay" aria-label="Panopto Embedded Video Player" aria-description="MP code refresher - 3 prefabs" ></iframe>

## Instantiate (add) gameobjects as your scene is running
Video 4 uses the 'instantiate' function to add a gameobject to a scene at run time:

The  'instantiate()' function needs 3 parameters (I think I say 4 in the video below):
They are : 1. the prefab gameobject to create, 2. its xyz position in space (a Vector3), and 3. it's rotation

    Instantiate(gameobject, new Vector3(x,y,z), rotation);

Find the  documentation for Instantiate at [https://docs.unity3d.com/](https://docs.unity3d.com/) 
Watch  video 4 to see how to use it. 

<iframe src="https://uwe.cloud.panopto.eu/Panopto/Pages/Embed.aspx?id=52a65920-4bce-4bb3-aeb0-b20101648a53&autoplay=false&offerviewer=true&showtitle=true&showbrand=true&captions=false&interactivity=all" height="405" width="720" style="border: 1px solid #464646;" allowfullscreen allow="autoplay" aria-label="Panopto Embedded Video Player" aria-description="MP code refresher - 4 -instantiate gameobjects" ></iframe>

## Code Challenge

Once you have instantiated a single gameobject work out how to instantiate 20 of the same objects into your scene:
Watch the full description of the Code Challenge:
<iframe src="https://uwe.cloud.panopto.eu/Panopto/Pages/Embed.aspx?id=ba59dd76-a3d4-4ab5-891d-b2010170eaef&autoplay=false&offerviewer=true&showtitle=true&showbrand=true&captions=false&interactivity=all" height="405" width="720" style="border: 1px solid #464646;" allowfullscreen allow="autoplay" aria-label="Panopto Embedded Video Player" aria-description="MP code refresher - 4 code challenge" ></iframe>

[Need the solution?](https://uwe.cloud.panopto.eu/Panopto/Pages/Viewer.aspx?id=e0bddfca-7769-4715-9b5a-b201016f069d)

## Creating an interaction with collisions

The next task is to use the collision created by the spheres falling to the ground to trigger the spot light to turn on and off.

![enter image description here](https://raw.githubusercontent.com/uwetom/media-production-worksheets/master/wk10-unity-refresher/images/interaction-flow-1.png)

Intro to the next part of the task
<iframe src="https://uwe.cloud.panopto.eu/Panopto/Pages/Embed.aspx?id=7b3a43c7-2e03-4d99-b104-b20201168c30&autoplay=false&offerviewer=true&showtitle=true&showbrand=true&captions=false&interactivity=all" height="405" width="720" style="border: 1px solid #464646;" allowfullscreen allow="autoplay" aria-label="Panopto Embedded Video Player" aria-description="MP code refresher - 5" ></iframe>

## Collision detection challenge

See if you can work out you how to detect collisions in your scene with c#
<iframe src="https://uwe.cloud.panopto.eu/Panopto/Pages/Embed.aspx?id=b0f2ae28-7ff1-4904-9b28-b2020117a4e3&autoplay=false&offerviewer=true&showtitle=true&showbrand=true&captions=false&interactivity=all" height="405" width="720" style="border: 1px solid #464646;" allowfullscreen allow="autoplay" aria-label="Panopto Embedded Video Player" aria-description="MP code refresher - 6 - code challenge" ></iframe>

Tip you'll need to use `OnCollisionEnter` to detect a collision and retrieve information about the collision object.

[Need the solution?](https://uwe.cloud.panopto.eu/Panopto/Pages/Viewer.aspx?id=604c37fc-f50c-4481-abbb-b20201198cf3)

## Turning the light on and off
Video 7 shows you how to turn the light on and off while the scene is running, and also how to detect if the light is on and off.

The rough plan for the script looks like this:

    // create isOn bool variable
    // create ChangeLight() function to turn light on and off
    // if light is on 
    // if isOn == true 
    //		turn off the light
    // if light is off 
    // else if isOn == false 
    //		turn off the light

<iframe src="https://uwe.cloud.panopto.eu/Panopto/Pages/Embed.aspx?id=8d383c54-1f52-44ac-83e7-b20300faba59&autoplay=false&offerviewer=true&showtitle=true&showbrand=true&captions=false&interactivity=all" height="405" width="720" style="border: 1px solid #464646;" allowfullscreen allow="autoplay" aria-label="Panopto Embedded Video Player" aria-description="MP code refresher - 7 turn light on and off" ></iframe>


## Access a function in another script (Turning a light on and off)
The next step is to trigger the `ChangeLight()` function to run when there is a collision.

However  the `ChangeLight()` function is in a different script to the collision detection.
So we need know how to let the scripts communicate with each other. 

Specifically we need the collision detection script to run the `ChangeLight()` function in the light script...  So that's what we're going to do next.

<iframe src="https://uwe.cloud.panopto.eu/Panopto/Pages/Embed.aspx?id=61c114ae-2c23-4ceb-889d-b2030100f505&autoplay=false&offerviewer=true&showtitle=true&showbrand=true&captions=false&interactivity=all" height="405" width="720" style="border: 1px solid #464646;" allowfullscreen allow="autoplay" aria-label="Panopto Embedded Video Player" aria-description="MP code refresher - 8 access a function from another script" ></iframe>


## Add more lights  challenge
You should now have one light flickering on and off when the spheres hit the ground plane.

The last (stretch) code challenge is to add more lights that all flicker on and off when the spheres hit the ground plane.

Hint: you will need to refactor (rewrite) bits of your code. There are a few ways to do this but probably the easiest have the light script check the collision script for collisions on every frame.

<iframe src="https://uwe.cloud.panopto.eu/Panopto/Pages/Embed.aspx?id=ea4b51a1-ec0a-44ee-b6cc-b203011340cb&autoplay=false&offerviewer=true&showtitle=true&showbrand=true&captions=false&interactivity=all" height="405" width="720" style="border: 1px solid #464646;" allowfullscreen allow="autoplay" aria-label="Panopto Embedded Video Player" aria-description="MP code refresher - 8 code challenge" ></iframe>
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE5NDk4MDYzMDAsMTA1MTI3ODgzOCwxMz
UyOTk1NTY2LC04NDI3MjE0OTYsLTEzNDcyMzUyNDksMTMxNTI1
MzY2NywzNDU1NDk5NTQsMTEwNDg4MzE1N119
-->