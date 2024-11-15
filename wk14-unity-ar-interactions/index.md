## More Unity AR - Interactions

In this worksheet we will look at adding interactions in our AR project.

## Starting project

This worksheet continues on from last weeks marker tracking project. 

If you have a finished working version of this project open that and skip to **Duplicate Scene** 

If you do not have a completed marker tracking project you can fork and clone my template project from github.

[Github repository](https://github.com/uwetom/Unity-Worksheet-1-finished)

![fork button on github.com](https://github.com/uwetom/media-production-worksheets/blob/master/wk14-unity-ar/images/fork.jpg?raw=true)

The following video will show you how to do this if you are unsure.

<iframe src="https://uwe.cloud.panopto.eu/Panopto/Pages/Embed.aspx?id=45ab7838-4187-448d-8f39-b229010e266e&autoplay=false&offerviewer=true&showtitle=false&showbrand=false&captions=false&interactivity=all" height="405" width="720" style="border: 1px solid #464646;" allowfullscreen allow="autoplay" aria-label="Panopto Embedded Video Player" aria-description="fork and clone repo" ></iframe>

## Duplicate Scene

In the **Scenes** folder, duplicate and rename your tracked image scene (it should be called **AR_tracked_image** ) and name it "AR_Interaction".

## Test the new scene

Open your new scene and press play to test it, you should see a ship appear on your marker in the virtual environment.

You will also want to test that the correct build platform is selected, 

- In the top menu, go to **File > Build Settings** and check that the current Platform is Android ( if not switch to it)

## XR Interaction toolkit

We want to interact with the objects in our scene by touching the screen.

We could manually setup and program the inputs ourselves but helpfully Unity has made an interaction toolkit package which contains everything we need.

We will be using it for AR, but as the name suggests, the XR toolkit also also works with VR projects and we will use it again later in the course.

- go to **Windows > Package Manager**
- In Unity Registry, search for "XR"
- Install the **XR Interaction Toolkit**

![turn on XR Simulation](https://github.com/uwetom/media-production-worksheets/blob/master/wk14-unity-ar/images/interaction_toolkit.jpg?raw=true)

As XR technology is rapidly evolving, Unity frequently updates this package with major changes. We will be using version 2.5 as it is the latest stable release for Unity 2023.

WARNING: Tutorials you find online may be using other versions of Unity and the toolkit which may not be compatible with what is covered in this worksheet

If in doubt, as always, check the documentation:

[XR Interaction toolkit 2.5](https://docs.unity3d.com/Packages/com.unity.xr.interaction.toolkit@2.5/manual/index.html)

We will also add the starter assets samples which will give us some assets.

- In the **XR Interation Toolkit** open the **Samples** tab and import the **Starter Assets**

![toolkit samples](https://github.com/uwetom/media-production-worksheets/blob/master/wk14-unity-ar/images/toolkit_samples.jpg?raw=true)

## Interaction Toolkit Components

There are three main **components** we need to add to our scene when using the toolkit for AR.

1. Interactables
	- These are added to individual objects in our scene, marking them as interactable so they can be selected and manipulated by the user.
2. Interactor
	- This is placed on the camera or controller which will select the interactables.
3. Interaction manager - This Contects the interactables to the interactors.

### 1. Interactable

We just want to be able to select our object, so we just need a simple interactable, 

- In the ship folder, double click to open the ship prefab.
- go into the **Ship-large** object
- AddPlanes and faces


## Template

At the start of the last worksheet you created a template AR project.

I have created a GitHub repository with this template project which you can **fork** and **XR Simple Interactable** component to it.

The object will also need a collider, we don't need it to match the shape of the ship so will just use a box.

- Add a **Box Collider** component 

![toolkit samples](https://github.com/uwetom/media-production-worksheets/blob/master/wk14-unity-ar/images/ship_collider.jpg?raw=true)

You can now save and go back to the scene

### 2. Interactor

We want to select our object by touching the screen on our device. Do do this we need to setup 2 things

1. specify user interactions, this needs to register clicks in the simulated environment and touches on the phone.
2. link those interactions to actions in unity
3. when the action is triggered send out a ray from where the user touches and check if it hits an object

<iframe src="https://uwe.cloud.panopto.eu/Panopto/Pages/Embed.aspx?id=981498de-a32c-4e12-981b-b22901135358&autoplay=false&offerviewer=true&showtitle=false&showbrand=false&captions=false&interactivity=all" height="405" width="720" style="border: 1px solid #464646;" allowfullscreen allow="autoplay" aria-label="Panopto Embedded Video Player" aria-description="unity ar - interactor" ></iframe>
	
### 3. Interaction Manager

We can now add our manager

- In the scene hierachy, **right click** and select **XR > XR Interaction Manager**

![toolkit samples](https://github.com/uwetom/media-production-worksheets/blob/master/wk14-unity-ar/images/interaction_manger.jpg?raw=true)

We now have everything set up, you can now select the object by clicking on it.  But, we can't test it yet as we haven't told Unity to do anything when the object is selected.

We will make a script with a function that we can call when the object is selected.

#### Challenge

Make a new script with a **public** function which shows a simple message on the console when called.

<details>
<summary>HINT</summary>
Debug.Log("my message");
</details>

<details>
<summary>Solution</summary>
- Create a new script in the script folder by right clicking and selecting **create > c# Script**
- Delete the update and start methods
- Create a new public function logging out a message

```
using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class Interactions : MonoBehaviour
{
   public void selected()
   {
        Debug.Log("ship selected");
   }
}
```
</details>

### Add the script to your object	

We can now add this script to our Object

- Open your Ship prefab
- Open the Ship-large object
- Drag your new script on the object. ( you may need to lock the inspector panel in the top right)

![toolkit samples](https://github.com/uwetom/media-production-worksheets/blob/master/wk14-unity-ar/images/add_script.jpg?raw=true)

### Connect the interactor to the script

<iframe src="https://uwe.cloud.panopto.eu/Panopto/Pages/Embed.aspx?id=60315a18-282a-424f-afe6-b2290117a99c&autoplay=false&offerviewer=true&showtitle=false&showbrand=false&captions=false&interactivity=all" height="405" width="720" style="border: 1px solid #464646;" allowfullscreen allow="autoplay" aria-label="Panopto Embedded Video Player" aria-description="ar - connect script to event" ></iframe>

You can now press play and test your scene in the simulated environment, the ship should appear on the marker image, and when you click on it you should get a message in your console.

![toolkit samples](https://github.com/uwetom/media-production-worksheets/blob/master/wk14-unity-ar/images/console.jpg?raw=true)

Now that we have a script hooked up to the interaction we fire off any other code we want, we could play a sound, instantiate another object, play an animation, all three or anything else we can think of.

## Annotation

We will add some annotations to the ship which appear when its touched.

<iframe src="https://uwe.cloud.panopto.eu/Panopto/Pages/Embed.aspx?id=db94a496-57f2-48e7-baa3-b2290119d8a1&autoplay=false&offerviewer=true&showtitle=false&showbrand=false&captions=false&interactivity=all" height="405" width="720" style="border: 1px solid #464646;" allowfullscreen allow="autoplay" aria-label="Panopto Embedded Video Player" aria-description="unity ar - extra functionality" ></iframe>


We now want to alter our interaction script to show and hide the annotation.

- Add a new boolean variable to hold the current visibility of the ship, set it to false
- Add a public GameObject variable to hold the annotation object.
- Add an if statement to your selected function to toggle the SetActive() property of your annotation object.

Try to write this yourself before looking at the solution bellow

<details>
<summary>finished Script</summary>
```
using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class Interactions : MonoBehaviour
{

    bool annotationVisible = false; //current visibility of ship
    public GameObject annotation; // annotation object

    public void selected()
    {

        Debug.Log("show annotation");
        //toggle visibility of the annotation
        if (annotationVisible)
        {
            annotation.SetActive(false);
            annotationVisible = false;
        }else {
            annotation.SetActive(true);
            annotationVisible = true;
        }

    }
}
```
</details>

In my script I have set the visibility of the annotation to be false at the start, so I want to turn it off in Unity

![toolkit samples](https://github.com/uwetom/media-production-worksheets/blob/master/wk14-unity-ar/images/turn_off_anotation.jpg?raw=true)

Lastly, I need to drag my annotation object into the new slot I just created on my script.

![toolkit samples](https://github.com/uwetom/media-production-worksheets/blob/master/wk18-unity-ar/images/drag_anotation.jpg?raw=true)

## Test

Now we can test our project. press play, then click the ship to see the text appearing and disappearing.

## Test on a device

We have done quite a lot of work, so its now important to test on a real device to make sure it works on a touch screen.

Build your project to an Android device, if you cannot remember how go back to last weeks worksheet

## Challenges

Now that We have the basic functionality working try to use your Unity skills to take this project further. Try to do one of the following:

- Animate the ship when selected, you could make the sails or ship rock
- Make a sound when the ship is selected
- Create a second ship with different text.

