[Back](https://uwetom.github.io/media-production-worksheets)

# Introduction to VR

## Work in Pairs

For this worksheet you should work in pairs, each pair will have one headset and work on one machine.

## VR Headsets

We are using Meta Quest headsets, they can be used as stand alone devices. This allows you to build content directly to the headset without requiring the user to be tethered to a powerful PC. They are also relatively affordable and the best selling.

We will be using Meta Quest 1 and 2 headsets, you can also use the Quest 3 if you have one. All the projects created in these worksheets will work for all 3 headsets.

These headsets require you to create an account and sign in to use. To save time I will do this for you before the in class workshops, but you will need to do yourself if you use them outside class.


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

Accept the pop-up to download the simulator package.

- Finally, in the **Project Validation** Section check for any issues issues in the 
window and Android tabs and press **Fix all**

We are now set up all the VR settings.

## Open Starter assets scene

The VR sample scene should already be open, if not, you can find it in **Scenes > Sample Scenes**

This scene demonstrates basic VR interactions and motion. When you create your own scene, this demo scene is a useful reference to work out how to implement similar functionality.

### Test out the scene

- Within your pair, try out the scene in the simulator and on the VR headset and swap over so you both get to experience both.
- Practice with the controls, moving around the scene and interacting with the objects and UI

### On the headset

We can build the scene to the headset, but as this can take a while, to save time I have pre-installed it for you.

### Simulated environment

To play the scene in the simulator you can just press the play button as normal.

![simulated environment](https://uwetom.github.io/media-production-worksheets/wk17-vr-introduction/images/simulated_environment.jpg)

The guide on the left of screen show you the controls, They are not very intuitive, but are useful to test the functionality of your project without having to do a full build to a real headset.

## Start our own scene

We now want to make our own scene.
 
- Create a new scene in the **Scenes** folder and name it "PracticeScene".
	- (HINT:right click > create)
- Add a plane to make a floor and name it "floor" in hierarchy.
- Add concrete material to it from **Assets > VRTemplateAssets > Materials > Environment**

We could create our own XR Character but we will use the prefab from the demo scene.

- Add **Assets > VRTemplateAssets > Prefab > Setup > Complete XR Orgin Setup Variant**
- Delete the Main Camera

![simulated environment](https://uwetom.github.io/media-production-worksheets/wk17-vr-introduction/images/character_and_floor.jpg)

- Now press play to test your scene and make sure the character moves around.

### Movement

The XR character prefab we have used already contains all the motion components we need.

But for your own projects you may want to limit or alter how the player moves so it is useful to explore the components used.

- In the Hierarchy, open up **Complete XR Origin Set > xr origin > locomotion system** to see all the movement objects.

![Locomotion System](https://uwetom.github.io/media-production-worksheets/wk17-vr-introduction/images/locomotion_system.jpg)

#### Turn

With the Turn object selected you should see 2 components in the Inspector.

**Snap Turn Provider**
Instantly rotate by a set amount pressing the thumb stick, by default this is set to 45 degrees per turn.

**Continuous Turn Provider**
Continuously turns the character, this is set to 60 degrees per second by default.

Although both components are added, they cannot be used simultaneously on the same control. Snap turn is used by default, to switch to continuous motions enable smooth turn on the right controller (inside Camera Offset)

#### Move

**Dynamic Move Provider** lets you use the left stick to move around just like you normally would in a first person controller.

**Grab and Climb providers** Allow you to use objects and handles in the world to pull yourself around.

#### Comfort

Users Can feel motion sickness when in VR, as a creator, it is your responsibility to minimise this as much as you can in your project.

The major cause of sickness is a disconnect between what the user can see and what there body is physically experiencing.

One factor is frame rate, if your add too much to your scene the frame rate will drop. This will cause a delay between moving in the real world and your view in the virtual world. Even a tiny delay will be uncomfortable.

The other factor is motion, although you want to be able to move your character around, if you are standing still in the real world, but your virtual character is running the discrepancy can be uncomfortable.

Meta have come up with useful guidelines that you may want to consider:

[VR Locomotion](https://developers.meta.com/horizon/resources/locomotion-comfort-usability/?locale=en_GB)

### Teleportation

A good solution to motion sickness is to allow the user to move around through teleportation. 

add teleportation area and test
add a teleportation anchor and test


-- build to device


- interactables
- 
worksheet 2


-affordance?

-- grabables
-- buttons
-- ui
-- 


## Documentation

These workshops will get you started, but for your own project you will want to dive more deeply into the detail, the documentation is a great starting point:

[Unity VR Template documentation](https://docs.unity3d.com/Packages/com.unity.template.vr@8.0/manual/index.html)

[Unity Interaction toolkit documentation](https://docs.unity3d.com/Packages/com.unity.xr.interaction.toolkit@2.5/manual/index.html)









