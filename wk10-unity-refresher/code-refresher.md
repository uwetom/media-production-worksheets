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

## Instantiate (create) gameobjects as your scene is running
Video 4 uses the 'instantiate' function to add a gameobject to a scene at run time:

The  'instantiate()' function needs 3 parameters (I think I say 4 in the video below):
the prefab gameobject to create, its xyz position in space (a Vector3), and it's rotation

    Instantiate(gameobject, xyz position, rotation);

Watch  video 4 to see how to use it.

<iframe src="https://uwe.cloud.panopto.eu/Panopto/Pages/Embed.aspx?id=52a65920-4bce-4bb3-aeb0-b20101648a53&autoplay=false&offerviewer=true&showtitle=true&showbrand=true&captions=false&interactivity=all" height="405" width="720" style="border: 1px solid #464646;" allowfullscreen allow="autoplay" aria-label="Panopto Embedded Video Player" aria-description="MP code refresher - 4 -instantiate gameobjects" ></iframe>

## Code Challenge

Once you have instantiated a single gameobject work out how to instantiate 20 of the same objects into your scene:
Watch the full description of the Code Challenge:
<iframe src="https://uwe.cloud.panopto.eu/Panopto/Pages/Embed.aspx?id=ba59dd76-a3d4-4ab5-891d-b2010170eaef&autoplay=false&offerviewer=true&showtitle=true&showbrand=true&captions=false&interactivity=all" height="405" width="720" style="border: 1px solid #464646;" allowfullscreen allow="autoplay" aria-label="Panopto Embedded Video Player" aria-description="MP code refresher - 4 code challenge" ></iframe>

Need the solution?

## Creating an interaction with collisions

The next task is to use the collision created by the spheres falling to the ground to trigger the spot light to turn on and off.

![enter image description here](https://raw.githubusercontent.com/uwetom/media-production-worksheets/master/wk10-unity-refresher/images/interaction-flow-1.png)
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTgwNTM4MzA5MiwtMTM0NzIzNTI0OSwxMz
E1MjUzNjY3LDM0NTU0OTk1NCwxMTA0ODgzMTU3XX0=
-->