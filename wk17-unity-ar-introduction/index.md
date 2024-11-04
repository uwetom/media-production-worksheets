[Back](https://uwetom.github.io/media-production-worksheets)

# Introduction to Augmented Reality (AR) in Unity

## Setup AR Project

First we want to create a new Unity project, Unity Hub has an Ar Core template but I have found it unreliable and bloated so we will set up our own that we can use with all our future AR projects.

In the following video walking through setting up an AR project we will:
- Create a new Unity project using the **Universal 3D** template
- Switch to build with Android
- Install AR packages
- Adjust the settings for AR
- Make a blank AR scene


<iframe src="https://uwe.cloud.panopto.eu/Panopto/Pages/Embed.aspx?id=889f2f8a-87c2-4ff2-a202-b21a008f305a&autoplay=false&offerviewer=true&showtitle=false&showbrand=false&captions=false&interactivity=all" height="405" width="720" style="border: 1px solid #464646;" allowfullscreen allow="autoplay" aria-label="Panopto Embedded Video Player" aria-description="unity- ar_template" ></iframe>

## Template

Now that we have a template AR project we can save it so that we can use it for all future AR projects.

I have created a GitHub repository with this template project which you can **fork** if you cant find your own template.

[https://github.com/uwetom/unity_ar_template](https://github.com/uwetom/unity_ar_template)

![fork button on github.com](images/fork.jpg)

## Build to Android Device

Now that we have a basic AR project and scene we want to check that it actually runs on a device.

### Android Developer mode
First we have to turn on **developer** mode on our Android device so that we copy our new app to it.

Most Android devices will have the following procedure, but the menu items may be in different locations.

<iframe src="https://uwe.cloud.panopto.eu/Panopto/Pages/Embed.aspx?id=f24a7422-8565-43e6-af75-b21e00a0a1b5&autoplay=false&offerviewer=true&showtitle=false&showbrand=false&captions=false&interactivity=all" height="405" width="720" style="border: 1px solid #464646;" allowfullscreen allow="autoplay" aria-label="Panopto Embedded Video Player" aria-description="Android developer mode" ></iframe>

### Build

Now that we have set the device up we can build to it

<iframe src="https://uwe.cloud.panopto.eu/Panopto/Pages/Embed.aspx?id=1c0abd93-e11a-40b9-8d4d-b21e00a3fea0&autoplay=false&offerviewer=true&showtitle=false&showbrand=false&captions=false&interactivity=all" height="405" width="720" style="border: 1px solid #464646;" allowfullscreen allow="autoplay" aria-label="Panopto Embedded Video Player" aria-description="unity-build to android" ></iframe>

### Test

This is a very simple project but move the phone around and see if you can see you cube hanging in space. It should open automatically when you unlock you device, if it does not you should be able to find it installed in your app library just like any other app.

## Position Virtual Object

In our template, the cube is located at the origin or our scene. This does not correspond to anything specifically in the real world, so when the app opens it arbitrarily decides where this is.

We want to be able to decide exactly where object will appear in the real world.

## Tracked Image

The first way we will do this is with a tracked image.

This allows us to link virtual 3D objects to real images.

This image can be anything we want, but for accurate tracking Unity recommends:

- Size must be at least 300 x 300 pixels.
- Format must be PNG or JPG.
- Image can be black and white or colour but must have strong contrast.
- Image should avoid repeated patterns.

I have created a Unity package with some simple assets in it to get us started. 

[unity ship package download](assets/ship.unitypackage)

- Download it and drag it into the assets panel in Unity to include it in your project
- Save the template scene with a new name in the scenes folder ("tracked_image_scene")
- Delete the cube from the scene

The following video shows you how to add an image manager to your scene and tell which image you want to track

<iframe src="https://uwe.cloud.panopto.eu/Panopto/Pages/Embed.aspx?id=b04ae597-ee18-43d5-b702-b21e00aa3994&autoplay=false&offerviewer=true&showtitle=false&showbrand=false&captions=false&interactivity=all" height="405" width="720" style="border: 1px solid #464646;" allowfullscreen allow="autoplay" aria-label="Panopto Embedded Video Player" aria-description="unity-add image manager" ></iframe>

Now we can create a script to instantiate our prefab on the image.



------------ add simple script video---------------------

<details>
<summary>Finished Script</summary>

```
using System.Collections;
using System.Collections.Generic;
using UnityEngine;
using UnityEngine.XR.ARFoundation; // include xr library

public class TrackImage : MonoBehaviour
{
    [SerializeField]
    ARTrackedImageManager m_TrackedImageManager; 
    public GameObject prefab; //Prefab you want to appear on marker image
    
    void OnEnable() => m_TrackedImageManager.trackedImagesChanged += OnChanged;

    void OnDisable() => m_TrackedImageManager.trackedImagesChanged -= OnChanged;

    void OnChanged(ARTrackedImagesChangedEventArgs eventArgs)
    {
    	// When the camera picks up a new image marker Unity adds a game object to it called newImage, this will stick to maker.
        foreach (ARTrackedImage newImage in eventArgs.added)
        {
       	  // Create new copy of your prefab
          GameObject newObj = GameObject.Instantiate(prefab);
          // parent prefab to the newImage so that they stick together.
          newObj.transform.parent = newImage.transform;
        }
    }
}

```

<details>

## Build and Test the Scene

We can now build and test the scene again on our device.

- First, on your Android device delete the previous build buy holding down on it and dragging it to delete.
- Go to **File > Build Settings** and add the current scene, untick the old template scene.
- Check You **run device** is still connected and selected and press build and run.
- Name the build something different than before.

If you point your camera at your image the model should appear.

-------------video of working tracked image--------------

## Add Extras

Now we have a basic tracked image system working we can think about adding more to this scene

--- adding sound video--

## Challenges

- Add extra marker images with extra models

- Add particle effect when maker found

