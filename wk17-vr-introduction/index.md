[Back](https://uwetom.github.io/media-production-worksheets)


# Introduction to VR

This worksheet will show you how to create a VR project in Unity and how to move around using an XR rig.

We will be using Unity version **2023.2.20f1** 

## 1. VR Headsets

We are using Meta Quest headsets, they can be used as stand alone devices. This allows you to build content directly to the headset without requiring the user to be tethered to a powerful PC.

We will be using Meta Quest 1 and 2 headsets, you can also use the Quest 3 if you have one. 

The headsets require you to create an account and sign in to use. To save time I will do this for you before the in class workshops, but you will need to do yourself if you book them from the project room for use outside class.

[How to setup your own headset](https://uwetom.github.io/media-production-worksheets/wk18b-setup-headset/)

Please make sure you reset them using the guide in the kit before returning them to the project room.

## 2.  Create a Unity Project

Open Unity and create a new project, we will use the built in VR template.

![VR core template in unity hub](https://uwetom.github.io/media-production-worksheets/wk17-vr-introduction/images/vr_core.jpg)

This will set up our project with all the packages we need and also include some helpful starter assets.

## 3. Set up

The template works with many different brands of headset, so we have to tell it which one we are using. We will do this later but a helpful message reminds us.

- Close the message.

![Vr proejct popupR core template](https://uwetom.github.io/media-production-worksheets/wk17-vr-introduction/images/popup.jpg)

### Android

The Meta Quest runs on Android so we need to switch the platform.

- In the top menu, select **File > Build Settings** and change the Platform to **Android** 
- Press **Switch Platform**

![Select Android build

![VR core template](https://uwetom.github.io/media-production-worksheets/wk17-vr-introduction/images/switch_platform.jpg)

### Device Simulation

We also want to be able to test our project in Unity on without having to build to the headset.

- Go into **File > Project Settings** and open **Player Settings...**

![Player Settings button](https://uwetom.github.io/media-production-worksheets/wk17-vr-introduction/images/player_settings.jpg)

- At the bottom, in **XR Plug-in Management**, under **XR Interaction Toolkit**  turn on **Use XR Device Simulator in Scene**

![uwe xr device simulator button](https://uwetom.github.io/media-production-worksheets/wk17-vr-introduction/images/use_simulation.jpg)

Accept the pop-up to download the simulator package.

#### Mac
nity oc  oaIf you are on a Mac, particularly in the lab you also need to change the plugin in manager from **penXR** to **Mock HMD Loader**. IMPORTANT, only do this for the left tab, NOT the android tab.

![uwe xr device simulator button](https://uwetom.github.io/media-production-worksheets/wk17-vr-introduction/images/hmd.png)

- Finally, in the **Project Validation** Section check for any issues in the window and Android tabs and press **Fix all**. It make take a few minutes to reload the scripts.

We are now set up all the VR settings.

## 4. Sample scene

The VR sample scene should already be open, if not, you can find it in **Scenes > Sample Scenes**

![uwe xr device simulator button](https://uwetom.github.io/media-production-worksheets/wk17-vr-introduction/images/sample.jpg)

This scene demonstrates basic VR interactions and motion. This demo scene is a useful reference to work out how to implement similar functionality in your own project.

### Test out the scene

- Try out the scene in the simulator (A) **and** on the VR headset (B).
- Practice with the controls, moving around the scene and interacting with the objects and UI

### A. Simulated environment

This video shows you how to use the simulated environment.

![simulated environment](https://uwetom.github.io/media-production-worksheets/wk17-vr-introduction/images/simulated_environment.jpg)

<iframe src="https://uwe.cloud.panopto.eu/Panopto/Pages/Embed.aspx?id=77afc393-1244-453f-82a7-b26100a887f6&autoplay=false&offerviewer=true&showtitle=false&showbrand=false&captions=false&interactivity=all" height="405" width="720" style="border: 1px solid #464646;" allowfullscreen allow="autoplay" aria-label="Panopto Embedded Video Player" aria-description="Unity VR - Simulator" ></iframe>

### B. On the headset

Before you use the headset read the following:

#### Safety - Be aware of your environment

When using a VR headset you may not be able to see the world around you, it is therefore very important that you clear the space around your space to ensure you don't injure yourself, others or the equipment.

Please watch the following Meta Video shows you how to safely use the headset.

[Safely use the Meta Quest](https://www.youtube.com/watch?v=Ke4MefpmRmc)

#### Play the sample scene

We can build the scene to the headset, but as this can take a while, to save time I have pre-installed it for you. I will show you how to do it yourself later in the worksheet.

-  Clear the space around you then put the headset on,
- Follow the instructions on the headset  to create a guardian boundary, I recommend the stationary boundary when working in the busy classroom.
- You should see a unity log on the menu bar, this is the pre-installed sample scene:
- Click on it to open.

![app](https://uwetom.github.io/media-production-worksheets/wk17-vr-introduction/images/vr_app.png)

## 5. Basic VR rig

We now want to make our own scene. You don't need to follow along with this video, but you may find it useful to know who to make your own rig:

<iframe src="https://uwe.cloud.panopto.eu/Panopto/Pages/Embed.aspx?id=b3a6d9c3-e639-43fb-ac8d-b26600a323fb&autoplay=false&offerviewer=true&showtitle=false&showbrand=false&captions=false&interactivity=all" height="405" width="720" style="border: 1px solid #464646;" allowfullscreen allow="autoplay" aria-label="Panopto Embedded Video Player" aria-description="unity vr - basic rig" ></iframe> 

## 6. Complete VR rig
 
We don't want to made a complex rig from scratch so will use the complete rig.

- Open **BasicScene** in the Scenes folder

![Locomotion System](https://uwetom.github.io/media-production-worksheets/wk17-vr-introduction/images/basicscene.jpg)

To avoid changing this template scene, we now want to save the scene with a different name.

- In the top menu, go to **File > Save as**
- Save the scene in the Scenes folder and call it "PracticeScene"

The Scene has a floor plane and a complete XR rig.

- Press play to make sure the scene plays without any issues and you can move around in the simulator.

You may notice that this rig doesn't have the helper labels, if you need these you can swap the **Complete XR Origin Set Up** for the **Complete XR Origin Set Up Variant** found in **Assets > VRTemplateAssets > Prefabs > Setup**

## 7. Change the controllers

Now that we have a rig, we can customise it, changing the appearance and altering the controls.

<iframe src="https://uwe.cloud.panopto.eu/Panopto/Pages/Embed.aspx?id=5521f875-99ec-4074-952b-b26100bf24dd&autoplay=false&offerviewer=true&showtitle=false&showbrand=false&captions=false&interactivity=all" height="405" width="720" style="border: 1px solid #464646;" allowfullscreen allow="autoplay" aria-label="Panopto Embedded Video Player" aria-description="Unity VR -XR rig" ></iframe>


## 8.  User Comfort - Cybersickness

Users Can feel motion sickness when in VR, as a creator, it is your responsibility to minimise this as much as you can in your project.

The major cause of sickness is a disconnect between what the user can see and what there body is physically experiencing.

One factor is frame rate, if your add too much to your scene the frame rate will drop. This will cause a delay between moving in the real world and your view in the virtual world. Even a tiny delay will be uncomfortable. Test your scene often to ensure it runs smoothly.

The other factor is motion, although you want to be able to move your character around, if you are standing still in the real world, but your virtual character is running or riding in a roller coaster  the discrepancy can be uncomfortable.

Meta have come up with useful locomotion guidelines that you may want to consider:

[VR Locomotion](https://developers.meta.com/horizon/resources/locomotion-comfort-usability/?locale=en_GB)

## 9. Motion 

### Turning

<iframe src="https://uwe.cloud.panopto.eu/Panopto/Pages/Embed.aspx?id=3fb895a5-2840-4774-abb1-b26100c1000a&autoplay=false&offerviewer=true&showtitle=false&showbrand=false&captions=false&interactivity=all" height="405" width="720" style="border: 1px solid #464646;" allowfullscreen allow="autoplay" aria-label="Panopto Embedded Video Player" aria-description="unity vr - turning" ></iframe>

### Movement

<iframe src="https://uwe.cloud.panopto.eu/Panopto/Pages/Embed.aspx?id=c28280c2-e9d2-437d-a58a-b26100c39c0a&autoplay=false&offerviewer=true&showtitle=false&showbrand=false&captions=false&interactivity=all" height="405" width="720" style="border: 1px solid #464646;" allowfullscreen allow="autoplay" aria-label="Panopto Embedded Video Player" aria-description="Unity VR - Motion" ></iframe>

### Other movement

You should also see **Grab and Climb providers** these allow you to use objects and handles in the world to pull yourself around.

If you are interested in these for your project, there is a demo scene in **Assets\Samples\XR Interaction Toolkit\2.5.2\Starter Assets**

## 10. Teleportation 

Teleportation is turned on by default on our XR rig, It allows users to move around the scene more comfortably then using continuous movement.

### Area

- Select the plane and look at the inspector.

You should see it has a **Teleportation Area** component.

- Create a new plane and place it next to the existing one.

- Add a **teleportation Area** component to it.

- Change the **Interaction Layer Mask** to **Teleport**

![Locomotion System](https://uwetom.github.io/media-production-worksheets/wk17-vr-introduction/images/teleportation_area.jpg)

- Test it out, try to teleport from one plane to the other.

In the simulator, you need to tab until you are controlling the right controllers, then press the **w** key to simulate pressing up on the thumb stick. 

### Anchor

You can also use a teleportation anchor. These allow you to pick specific spots for the player to teleport to. 

- Add a cube to the scene
- scale it down so its flatter
- move it next to one of the planes
- Add a **Teleportation Anchor** component to it
- Change the **Interaction layer mask** to Teleport

![Locomotion System](https://uwetom.github.io/media-production-worksheets/wk17-vr-introduction/images/anchor.jpg)

- Test it out

Notice that although you can select anywhere on the cube, as soon as you teleport it locks you to the center.

## 11. Build to the headset

Once the headset is setup, building to it is just as easy as building to any Android device.

Connect the headset to the computer via the USBc cable in the VR box.

**On the headset:**
- Put it on and accept the debug connection. Always allow.

**In Unity:**
- On the top menu, select **File > Build settings**
- Make sure the correct scene is ticked in the top box.
- Press **Refresh** under **Run Device** and select your headset.
- In **Run Device** Select the headset
- Press **Build and Run**

![build settings](https://uwetom.github.io/media-production-worksheets/wk17-vr-introduction/images/build.jpg)

The first time, it may take quite a while ( it took me 10 minutes! ) to build but it will be much quicker when you make changes and build again.

When finished put the headset on and try out your scene.

## Challenge - Build a mini scene

Find some assets on the asset store or download and import these into your project:

[left hand](https://uwetom.github.io/media-production-worksheets/wk17-vr-introduction/assets/left_hand.fbx)

[right hand](https://uwetom.github.io/media-production-worksheets/wk17-vr-introduction/assets/right_hand.fbx)

Kenney create some useful free assets for prototyping

[kenney.nl](https://kenney.nl/assets/prototype-kit)

Try to Include
- Multiple teleportation anchors and areas
- Change the controllers.
- Try it out on the simulator and build it to the device.

## Documentation

These workshops will get you started, but for your own project you will want to dive more deeply into the detail, the documentation is a great starting point:

[Unity VR Template documentation](https://docs.unity3d.com/Packages/com.unity.template.vr@8.0/manual/index.html)

[Unity Interaction toolkit documentation](https://docs.unity3d.com/Packages/com.unity.xr.interaction.toolkit@2.5/manual/index.html)



<!--stackedit_data:
eyJoaXN0b3J5IjpbLTQ2NzMyNzExLDM0MDEyMDQ2NywxNTg5NT
QzMCw5OTcyMzg4NzcsMTA4ODA5MTMzMiwtMTEwOTU3NjQzNiwt
Njk1MjEzMTg1LDEwMzY4Nzc4NTksLTcxODc0OTI0MywzOTc3ND
c1MjMsMjU2NDcxMjE5LDE3MzAzNDkzMDQsMTgzMTYxNDQ4Miwt
MTkxMzMyNjE0NSwxNjU0NjQxNTQ5LC00Mjg2NzM3NjYsMTE1MT
c5NTU0XX0=
-->