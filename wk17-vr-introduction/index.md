[Back](https://uwetom.github.io/media-production-worksheets)

# Introduction to VR

In This worksheet I will introduce you to VR in Unity, showing you how to create an XR rig and navigate around a scene.

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

### Simulated environment

To play the scene in the simulator you can just press the play button as normal.

![simulated environment](https://uwetom.github.io/media-production-worksheets/wk17-vr-introduction/images/simulated_environment.jpg)

The guide on the left of screen show you the controls, They are not very intuitive, but are useful to test the functionality of your project without having to do a full build to a real headset.

- When the scene starts press # to lock the mouse
- Press **tab** to cycle between controlling the head set and each controller.
- With the right controller selected, press WSAD to move around.
- With the left controller selected, w to teleport.

### On the headset

We can build the scene to the headset, but as this can take a while, to save time I have pre-installed it for you.

## Start our own scene

We now want to make our own scene. We could create a new empty scene and add a floor and XR rig, but this has already been done for us.
 
- Open **BasicScene** in the Scenes folder

![Locomotion System](https://uwetom.github.io/media-production-worksheets/wk17-vr-introduction/images/basicscene.jpg)

To avoid changing this template scene, we now want to save the scene with a different name.

- In the top menu, go to **File > Save as**
- Save the scene in the Scenes folder and call it "PracticeScene"

The Scene has a floor plane and a complete XR rig.

- Press play to make sure the scene plays without any issues and you can move around.

## Tour of the XR rig

----------Video

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

## Teleportation 

Teleportation is turned on by default on our XR rig, It allows users to move around the scene more comfortably then using continuous movement.

### Area

Select the plane and look at the inspector.

You should see it has a **Teleportation Area** component.

- Create a new plane and place it next to the existing one.

- Add a **Teleportation Area** component to it.

- Change the **Interaction Layer Mask** to **Teleport**

![Locomotion System](https://uwetom.github.io/media-production-worksheets/wk17-vr-introduction/images/teleportation_area.jpg)

- Test it out, try to teleport from one plane to the other.

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

## Grab

Next we want to be able to pick up an object.

- Add a cylinder to your scene
- rename it to "staff"
- Scale it so it is long and thin.
- Add a **Rigidbody** component to it.
- Add an **XR Grab Interactable** component to it.

You can now test this in your scene

- In the simulator, tab to the right controller, press g while pointing at the staff to grab it.
- Use the w and s keys to move reel it in.

### Change grab position

By default the object is grabbed at its origin. But normally we want to be able to control where it is grabbed.

- Create an empty game object inside your staff (HINT:right click > create empty)
- Rename it to "grabPosition"
- Move it to the bottom of the staff

![Locomotion System](https://uwetom.github.io/media-production-worksheets/wk17-vr-introduction/images/grab_position.jpg)

- On the **XR Grab Interactable** component on the staff, scroll to the bottom
- Drag the new **grabPosition** object onto the **Attach Transform** slot.

Now, test this out, when you grab the staff you should attach to its base.

## Build to the headset

Building to a Meta Quest headset it just as easy as building to any Android device.

On the headset:

- Plug it into the computer
- Put it on and accept the connection.

In Unity:

- On the top menu, select **File > Build settings**
- Make sure correct scene is ticked at the top
- In **Run Device** Select the headset
- Press **Build and Run**

![build settings](https://uwetom.github.io/media-production-worksheets/wk17-vr-introduction/images/build.jpg)

The first time, it may take quite a while ( it took me 10 minutes) to build but will be much quicker when you make changes and build again.

When finished put the headset on and test your scene.

## Build a mini scene

Download these object or find your own and make a simple scene.

[tools pack](https://uwetom.github.io/media-production-worksheets/wk17-vr-introduction/assets/tools.unitypackage)

- Include multiple teleportation anchors and grabable objects which are grabbed at an appropriate point.
- Hint, grabables need a ridgid body, collider and xr grab interactable components.

## Documentation

These workshops will get you started, but for your own project you will want to dive more deeply into the detail, the documentation is a great starting point:

[Unity VR Template documentation](https://docs.unity3d.com/Packages/com.unity.template.vr@8.0/manual/index.html)

[Unity Interaction toolkit documentation](https://docs.unity3d.com/Packages/com.unity.xr.interaction.toolkit@2.5/manual/index.html)







