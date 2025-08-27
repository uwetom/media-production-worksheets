[Back](README.md)

# Using Triggers with Animation Controllers and MoCap Animations 

In this tutorial we're going to download a new character from Mixamo.com and we're going to apply a set of animations to it from scratch.

Then we are going to use a trigger function to trigger the motion capture animations to play on a keypress. Like this (the animation changes when I press '1' on my keyboard):

[<img src="images/mocap2.0.jpg">](https://uwe.cloud.panopto.eu/Panopto/Pages/Viewer.aspx?id=3ac7a880-29b9-43b8-9a92-b2430004b235&start=0)


## Download and prep a character and animation
The first step is download a T pose character  import it into Unity and prep it for use.
You need to make sure your character is in a T Pose (and not animated).

[<img src="images/mocap2.1.jpg">](https://uwe.cloud.panopto.eu/Panopto/Pages/Viewer.aspx?id=951a8601-c0d1-4106-8b58-b242017a9a80&start=0)  

Then download an animation (just the animation, not the character), and import it into Unity and prep ready for use.

[<img src="images/mocap2.2.jpg">](https://uwe.cloud.panopto.eu/Panopto/Pages/Viewer.aspx?id=446e35cb-aa22-41cd-a6f2-b242017e3900&start=0)

## Create an animation controller
Then we will build an animation controller to run the animations and animate the character.

[<img src="images/mocap2.2.2.jpg">](https://uwe.cloud.panopto.eu/Panopto/Pages/Viewer.aspx?id=a1405d08-aee1-4e63-832d-b2420180121e&start=0)

You may find that you want to edit / delete animations from your animation controller.
To do this right click on the animation node in the animation controller.   
![delete animations](images/delete-node.png)


If you just want to remove / delete a transition select it and click the minus sign in the inspector.
![delete a transition](images/delete-transition.png)


## Add a Trigger to an animation controller
Next we will add a trigger to one of the transitions / animations.

[<img src="images/mocap2.3.jpg">](https://uwe.cloud.panopto.eu/Panopto/Pages/Viewer.aspx?id=a978cc3c-a1d8-4c28-874a-b24201836239&start=0)


## Scripting for the animation controller Trigger 
Finally we will create a script that sets the trigger

[<img src="images/mocap2.4.jpg">](https://uwe.cloud.panopto.eu/Panopto/Pages/Viewer.aspx?id=d35d633d-77ca-4215-9b51-b2420185cde7&start=0)


## Adding a bool trigger 

Instead of a 'Trigger' it is possible set a bool to true or false to start and stop an animation.

This maybe more useful, giving you complete control over the animations.

To do this we will add a bool parameter to the animation controller
[<img src="images/mocap2.5.jpg">](https://uwe.cloud.panopto.eu/Panopto/Pages/Viewer.aspx?id=900f15dc-e08f-48a5-84c0-b2420189d2b9&start=0)


Then edit the script to set the bool to true when the Return key is pressed.
[<img src="images/mocap2.6.jpg">](https://uwe.cloud.panopto.eu/Panopto/Pages/Viewer.aspx?id=2a635d01-05b9-4eb9-8360-b24300006747&start=0)

