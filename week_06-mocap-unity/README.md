# Animating with MoCap data 

To start using MoCap data you'll need a new project set up and have downloaded a Mixamo character with an animation attached from https://www.mixamo.com/

This is a free website with 1000s of animations amd 100s of characters that you can download and use in your project.

[<img src="images/mocap-1.jpg">](https://uwe.cloud.panopto.eu/Panopto/Pages/Viewer.aspx?id=4e0bdacd-1bdb-4381-ada0-b21400bfa205&start=0)


Change your Unity scene name to 'Main'. Add a cube in the scene and scale it to make a ground plane.

You'll also need to import your motion capture data / .fbx file into your Unity project. Make an Animations folder for everything. I've imported two call tom-001 and tom-002.

![enter image description here](images/folders.jpg)

Now there are several steps that you need to follow to use your mocap data in a character animation in your scene:

 - Set up the character
 - Create an Animation Controller and add animations to the character
 - Add MoCap animations to the Animation Controller
 - Looping and chaining animations in the Animation Controller

## Set up the character

Next we'll set up our character. Changing the rig to humanoid and attaching textures and materials.

[<img src="images/mocap-2.jpg">](https://uwe.cloud.panopto.eu/Panopto/Pages/Viewer.aspx?id=8ab30e50-8e4e-4751-bdf5-b21800de5863&start=0)

## Create an Animation Controller and add animations to the character

This video steps through setting up an  Animation Controller and adding a basic animation to it.

[<img src="images/mocap-3.1.jpg">](https://uwe.cloud.panopto.eu/Panopto/Pages/Viewer.aspx?id=1c8d5b05-a3b1-4b81-a585-b21800f1141d&start=0)

## Add a MoCap animation to the Animation Controller

This video steps through adding MoCap animations to an Animation Controller to use the MoCap animations with the character.
[<img src="images/mocap-3.2.jpg">](https://uwe.cloud.panopto.eu/Panopto/Pages/Viewer.aspx?id=5b75fd48-de63-49ea-951b-b21800f6c60d&start=0)

## Looping and chaining more MoCap animations in the Animation Controller.

In this video I add further animations to the animation controller and create multiple transitions.

[<img src="images/mocap-3.3.jpg">](https://uwe.cloud.panopto.eu/Panopto/Pages/Viewer.aspx?id=85987f50-48b4-4734-b74e-b21800faae87&start=0)

## Add Triggers

In the next worksheet we will use a trigger function to trigger specific animations on a keypress [next](triggers.md)

