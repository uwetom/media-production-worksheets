[Back](https://uwetom.github.io/media-production-worksheets)


# Introduction to VR

This worksheet will show you how to create a VR project in Unity and how to move around using an XR rig.

We will be using Unity version **6** 

## 1. VR Headsets

We are using Meta Quest headsets, they can be used as stand alone devices. This allows you to build content directly to the headset without requiring the user to be tethered to a powerful PC.

We will be using Meta Quest 1,2 and 3s headsets, you can also use the Quest 3 if you have one. 

The headsets require you to create an account and sign in to use. To save time I will do this for you before the in class workshops, but you will need to do yourself if you book them from the project room for use outside class.

[How to setup your own headset](https://uwetom.github.io/media-production-worksheets/wk18b-setup-headset/)

Please reset the headset to wipe any personal data before you return it to the project room.

## 2. Create a Unity Project

Open Unity and create a new project, we will use the built in VR template.

![VR core template in unity hub](https://uwetom.github.io/media-production-worksheets/wk17-vr-introduction/images/new_project_6.jpg)

This will set up our project with all the packages we need and also include some helpful starter assets.

## 3. Set up

The template will work with many different brands of headset so we have to tell it which one we are using. We will do this later but a helpful message reminds us.

- Close the message.

![Vr proejct popupR core template](https://uwetom.github.io/media-production-worksheets/wk17-vr-introduction/images/popup.jpg)

### Android

The Meta Quest runs on **Android** we could choose this as our platform, but Unity also gives us a specific **Meta Quest** option to configure android for VR.

- In the top menu, select **File > Build Profiles** and change the Platform to **Meta Quest**
- Press **Switch Platform**

![VR core template](https://uwetom.github.io/media-production-worksheets/wk17-vr-introduction/images/switch_platform_6.jpg)

After it has finished you will see that the Active platform has been set to **Android**, but this is fine for us.

### Device Simulation

It is important to test in a real headset to know that you project works as intended, but during development we also want to be able to quickly test our project in Unity.

- Go into **Edit > Project Settings**

- At the bottom, in **XR Plug-in Management**, under **XR Interaction Toolkit**  turn on **Use XR Device Simulator in Scene**

![uwe xr device simulator button](https://uwetom.github.io/media-production-worksheets/wk17-vr-introduction/images/use_simulation.jpg)

Accept the pop-up to download the simulator package.

- In the **XR Plug-in management** section, in the left tab
 change the **Plug-in Providers** from **OpenXR** to **Mock HMD Loader**. IMPORTANT, only do this for the left tab, **NOT** the android tab or it wont work in the headset.

![uwe xr device simulator button](https://uwetom.github.io/media-production-worksheets/wk17-vr-introduction/images/hmd.png)

We are now setup and ready to try out a VR scene.

## 4. Sample scene

The VR sample scene should already be open, if not, you can find it in **Scenes > Sample Scenes**

![uwe xr device simulator button](https://uwetom.github.io/media-production-worksheets/wk17-vr-introduction/images/sample.jpg)

This scene demonstrates basic VR interactions and motion. It is also a useful reference to work out how to implement similar functionality in your own project.

### Test out the scene

- Try out the scene in the simulator (A) **and** on the VR headset (B).
- Practice with the controls, moving around the scene and interacting with the objects and UI

### A. Simulated environment

This video shows you how to use the simulated environment.

[<img src="https://uwetom.github.io/media-production-worksheets/wk17-vr-introduction/images/xr_simulator_video.jpg">](https://uwe.cloud.panopto.eu/Panopto/Pages/Viewer.aspx?id=d11c7102-37ff-454f-a4bd-b2fe00e91a5b)

### B. On the headset

Before you use the headset read the following:

#### Safety - Be aware of your environment

When using a VR headset you may not be able to see the world around you, it is therefore very important that you clear your space to ensure you don't injure yourself, others or the equipment.

Please watch the following Meta Video shows you how to safely use the headset.

[Safely use the Meta Quest](https://www.youtube.com/watch?v=Ke4MefpmRmc)

When asking others to test your scene, it is your responsibility to create a safe environment.

#### Play the sample scene

We can build a scene to the headset, but as this can take a while, to save time I have pre-installed the sample scene for you. I will show you how to do it yourself later in the worksheet.

-  Clear the space around you then put the headset on,
- Follow the instructions on the headset  to create a guardian boundary, I recommend the stationary boundary when working in the busy classroom.
- You should see a black unity logo on the menu bar, this is the pre-installed sample scene:
- Click on it to open.

![app](https://uwetom.github.io/media-production-worksheets/wk17-vr-introduction/images/vr_app.png)

- try to move around and pick up object to get familiar with a VR environment.

## 5. Complete VR rig
 
For this tutorial we will use the pre-made rig provided in the template. 

- Open **BasicScene** in the Scenes folder

![Locomotion System](https://uwetom.github.io/media-production-worksheets/wk17-vr-introduction/images/basicscene.jpg)

We may want this template scene again, so to avoid saving it over it we want to save the scene with a different name.

- In the top menu, go to **File > Save as**
- Save the scene in the Scenes folder and call it "PracticeScene"

The Scene already includes a floor plane and an XR Origin (XR Rig)

- Press play to make sure the scene plays without any issues and you can move around in the simulator just as you did in the sample scene.

We recomend you use this scene for your project.

You may notice that this rig doesn't have the helper labels, if you need these you can swap the **Complete XR Origin Set Up** for the **Complete XR Origin Set Up Variant** found in **Assets > VRTemplateAssets > Prefabs > Setup**

## 6. User Comfort - Cybersickness

Many users Can feel motion sickness when in VR, as a creator, it is your responsibility to minimise this as much as you can in your project.

The major cause of sickness is a disconnect between what the user can see and what there body is physically experiencing.

One factor is frame rate, if your add too much to your scene the frame rate will drop. This will cause a delay between moving in the real world and your view in the virtual world. Even a tiny delay will be uncomfortable. Test your scene often to ensure it runs smoothly.

The other factor is motion, although you want to be able to move your character around, if you are standing still in the real world, but your virtual character is running or riding in a roller coaster the discrepancy can be uncomfortable.

Meta have come up with useful locomotion guidelines that you may want to consider:

[VR Locomotion](https://developers.meta.com/horizon/resources/locomotion-comfort-usability/?locale=en_GB)


## 7. Teleportation 

Teleportation is turned on by default on our XR rig, It allows users to move around the scene more comfortably then using continuous movement provided by the left thumb stick.

### Area

- Select the plane and look at the inspector.

You should see it has a **Teleportation Area** component. This allows the player to teleport anywhere on this surface.

- Scale it down to 1 

- Create a new plane and place it next to the existing one.
- Give it a new material, you can find some in **Assets\VRTemplateAssets\Materials\Environment**

- Add a **teleportation Area** component to it.

- Change the **Interaction Layer Mask** to **Teleport**

![Locomotion System](https://uwetom.github.io/media-production-worksheets/wk17-vr-introduction/images/teleportation_area.jpg)

- Test it out in the simulator, try to teleport from one plane to the other.

Remember In the simulator, you need to press tab to select the controllers, then press the **i** key to simulate pressing up on the thumb stick and producing a teleport beam.

### Anchor

You can also use a teleportation anchor. These allow you to pick specific spots for the player to teleport to.

- Add a cube to the scene
- scale it down so it's flatter
- move it next to one of the planes
- Add a **Teleportation Anchor** component to it
- Change the **Interaction layer mask** to Teleport

![Locomotion System](https://uwetom.github.io/media-production-worksheets/wk17-vr-introduction/images/anchor.jpg)

- Test it out

Notice that although you can select anywhere on the cube, as soon as you teleport it locks you to the centre.

## 9. Build to the headset

Once the headset is setup, building to it is just as easy as building to any Android device.

In the lab, I have already turned on developer mode for you, if you have your own headset or book one out of the project room you will need to set them up yourself

[How to setup your own headset](https://uwetom.github.io/media-production-worksheets/wk18b-setup-headset/)

- Connect the headset to the computer via the USB C cable in the VR box.

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