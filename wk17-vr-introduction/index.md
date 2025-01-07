[Back](https://uwetom.github.io/media-production-worksheets)

# Introduction to VR

## VR Headsets

There are many headsets available, we are using the Meta Quest as they can be used as stand alone devices. This allows you to build content directly to the headset without requiring the user to be  tethered to a powerful PC. They are also relatively affordable and the most popular.

We will be using Meta Quest 1 and 2 headsets, you can also use the Quest 3 if you have one. All the projects created in these worksheets will work for all 3 headsets.

These headsets require you to create an account and sign in to use. To save time I will do this for you before the in class workshops, but you will need to do yourself if you use them outside class.


## Documentation

These workshops will get you started, but for your own project you will want to dive more deeply into the detail, the documention is a great starting point:

[Unity VR Template documentation](https://docs.unity3d.com/Packages/com.unity.template.vr@8.0/manual/index.html)

[Unity Interaction toolkit documentation](https://docs.unity3d.com/Packages/com.unity.xr.interaction.toolkit@2.5/manual/index.html)

## Be aware of your environment

When using a VR headset you may not be able to see the world around you, it is therefore very important that you setup your space to ensure you don't injure yourself, others or the equipment.

Please watch the following Meta Video shows you how to safely use the headset.

[Safely use the Meta Quest](https://www.youtube.com/watch?v=Ke4MefpmRmc)

The video show the creation of a large guardian boundary, but you are also able to create a stationary boundary for seated experiences.

## Create a Unity project

First we want to create a new project, we will use the VR template for this.

![VR core template in unity hub](https://uwetom.github.io/media-production-worksheets/wk17-vr-introduction/images/vr_core.jpg)

This will set up our project with all the packages we need and also include some helpful starter assets.

## Set up

The template does not know which headset we are using, so we have to tell it. A helpful message telling us this should pop up

- Close the message.

![Vr proejct popup](https://uwetom.github.io/media-production-worksheets/wk17-vr-introduction/images/popup.jpg)

### Android

The Meta Quest runs on Android so we need to switch the platform.

- In the top menu, select **File > Build Settings** and change the Platform to **Android** 
- Press **Switch Platform**

![Select Android build](https://uwetom.github.io/media-production-worksheets/wk17-vr-introduction/images/switch_platform.jpg)

### Device Simulation

We also want to be able to test our device in Unity without having to build to the headset.

- Go into **File > Project Settings** and open **Player Settings...**

![Player Settings button](https://uwetom.github.io/media-production-worksheets/wk17-vr-introduction/images/player_settings.jpg)

- At the bottom, in **XR Plug-in Management**, under **XR Interaction Toolkit**  turn on **Use XR Device Simulator in Scene**

![uwe xr device simulator button](https://uwetom.github.io/media-production-worksheets/wk17-vr-introduction/images/use_simulation.jpg)

Accept the popup to download the simulator package.

- Finally, in the **Project Validation** Section check for any issues issues in the 
window and Android tabs and press **Fix all**

We are now set up all the VR settings.

## Open Starter assets scene

The VR sample scene should already be open, if not, you can find it in **Scenes > Sample Scenes**

- Press play and experiment with the Simulated controllers.

![v](https://uwetom.github.io/media-production-worksheets/wk17-vr-introduction/images/simulated_environment.jpg)

The guide on the left of screen show you the controls, They are not very intuitive or simple to use, but are very useful to test the functionality of your project without having to do a full build to a real headset.

We can also build this scene to our VR headset  but as this can take quite a long time we will do it later.

## Start our own scene

- Create a new scene
- save it to the scenes folder
- add a cube and scale it up to make a floor ( name it floor in hieracty)
- add Assets > VRTemplateAssets > Prefab > Setup > Complete XR Orgin Setup Variant

### Movement

look at  xr origin > locomotion system to see all the components

- turn > continuous turn provider
- turn > snap turn provider
	be careful of user comfort
	- xr origin > camera offset > main camera > 

- move > dynamic move provider

- grab move
- climb

#### Comfort

Users Can feel motion sickness when in VR, as a creator, it is your responsibility to minimise this as much as you can in your project.

The major cause of sickness is a disconnect between what the user can see and what there body is physically experiencing.

One factor is frame rate, if your add too much to your scene the frame rate will drop. This will cause a delay between moving in the real world and your view in the virtual world. Even a tiny delay will be uncomfortable.

The other factor is motion, although you want to be able to move your character around, if you are standing still in the real world, but your virutal character is running the discrepency can be uncomfortable.

Meta have come up with useful guidelines that you may want to consider:

[VR Locomotion](https://developers.meta.com/horizon/resources/locomotion-comfort-usability/?locale=en_GB)

### Teleportation

One way to 

add teleportation area and test
add a teleportation anchor and test





-- build to device

-- hands?

-affordance?
- interactables
-- grabables
-- buttons
-- ui
-- 












