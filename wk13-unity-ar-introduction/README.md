[Back](https://uwetom.github.io/media-production-worksheets)

# Introduction to Augmented Reality (AR) in Unity

## Unity Installation

If you are using the lab machines or a PC you can skip to the next section **Create a new Project**.

### Install Unity on your own mac

If you are using Unity on your on Mac check that your Unity Editor (6000.1.9f1 ) is installed in inside a parent folder that contains no spaces. EG: **UnityVersions** rather than **Unity Versions**.

![Check unity install location](images/editor-loc.png)

If it is installed in a parent folder with spaces it will not build your AR project to your device.

So you will need to quit the Unity Editor and Unity Hub, rename the folder and then follow the prompts re-add / re locate the Unity editor when you reopen Unity Hub.

Now you are ready to create your AR Unity template.

## Create a new Project

First we want to create a new Unity project, Unity Hub has an AR Core template, but I have found it unreliable on some devices and bloated. It is also useful to know how the template is constructed so you are more able to fix and issues.

In the following video we will:
- Create a new Unity project using the **Universal 3D** template
- Switch to build with Android
- Install AR packages
- Adjust the settings for AR
- Make a blank AR scene

<iframe src="https://uwe.cloud.panopto.eu/Panopto/Pages/Embed.aspx?id=889f2f8a-87c2-4ff2-a202-b21a008f305a&autoplay=false&offerviewer=true&showtitle=false&showbrand=false&captions=false&interactivity=all" height="405" width="720" style="border: 1px solid #464646;" allowfullscreen allow="autoplay" aria-label="Panopto Embedded Video Player" aria-description="unity- ar_template" ></iframe>

## Build to Android Device

Now that we have a basic AR project and scene we want to check that it runs on a real device.

### Android Developer mode
Before we build, we need to turn on **developer mode** on our Android device so that we copy our new app to it.

The menus items may be in different, but the following video shows how to enable developer mode on most Android devices:

<iframe src="https://uwe.cloud.panopto.eu/Panopto/Pages/Embed.aspx?id=f24a7422-8565-43e6-af75-b21e00a0a1b5&autoplay=false&offerviewer=true&showtitle=false&showbrand=false&captions=false&interactivity=all" height="405" width="720" style="border: 1px solid #464646;" allowfullscreen allow="autoplay" aria-label="Panopto Embedded Video Player" aria-description="Android developer mode" ></iframe>

### Build

Now that we have set the device up we can build to it

<iframe src="https://uwe.cloud.panopto.eu/Panopto/Pages/Embed.aspx?id=1c0abd93-e11a-40b9-8d4d-b21e00a3fea0&autoplay=false&offerviewer=true&showtitle=false&showbrand=false&captions=false&interactivity=all" height="405" width="720" style="border: 1px solid #464646;" allowfullscreen allow="autoplay" aria-label="Panopto Embedded Video Player" aria-description="unity-build to android" ></iframe>

### Test

Move the phone around and see if you can see you cube hanging in space, you may need to move backwards as it may have appeared on top of you.

The cube should remain in place in the real world as you move around it.

 The app should open automatically when you unlock you device, if it does not you should be able to find it installed in your app library.

- If you cannot find the cube,
	- Try restarting the app. 
	- If you still cannot find it, check that you build the correct scene in Unity.

## Keep this project
We will use this project as the template for the other AR worksheets, keep it safe or you may have to set it all up again.

## Challenge


1. Try to replace the cube with another object
- Find a free object on the Unity asset store or  sketchfab.com and add it to your scene. or use the prefab is this package:

	- [Nefertiti](https://uwetom.github.io/media-production-worksheets/wk13-unity-ar-introduction/assets/nefertiti.unitypackage)
- Build your scene to the tablet, it should be much quicker the 2nd time.
2. Add an animation to your object that automatically plays.

## References

- [AR foundation](https://docs.unity3d.com/Packages/com.unity.xr.arfoundation@5.1/manual/index.html)
- [Nefertiti bust](https://sketchfab.com/3d-models/nefertitis-bust-like-in-the-museum-ce5b14926e494558ab584375a8d63ca7)
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTc4MzMzNTQ3NSwtNDA3MTg5ODQ2LC0zNz
cyOTUzNDMsLTIwODc5NDc0MjAsLTE3NjEwNTQwMTYsMTIwNTky
NDkwMywtNDYxMDcwMTI0LC0yMDYwODM3NDg2LDc4Mzk1MDAyOS
wtMTIzMDc4ODY3Miw2MTMzNjg0ODcsNTA0MDUyNzU4XX0=
-->