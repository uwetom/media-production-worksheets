[Back](https://uwetom.github.io/media-production-worksheets)


# Introduction to VR


## Be aware of your environment

When using a VR headset you may not be able to see the world around you, it is therefore very important that you setup your space to ensure you don't injure yourself, others or the equipment.

Following Meta Video shows you how to safely use the headset.

[Safely use the Meta Quest](https://www.youtube.com/watch?v=Ke4MefpmRmc)

The video show the creation of a large guardian boundary, but you are also able to create a stationary boundary for seated experiences.

## Create Project

First we want to create a new project, we will use the VR template for this.

![VR core template](https://uwetom.github.io/media-production-worksheets/wk17-vr-introduction/images/vr_core.jpg)

This will set up our project with all the packages we need and also include some helpful starter assets.

## Set up

The template does not know which headset we are using, so we have to tell it. A helpful message telling us this should pop up

- Close the message.

![VR core template](https://uwetom.github.io/media-production-worksheets/wk17-vr-introduction/images/popup.jpg)

### Android

The Meta Quest runs on Android so we need to switch the platform

- In the top menu, select **File > Build Settings** and change the Plantform to **Android**

![VR core template](https://uwetom.github.io/media-production-worksheets/wk17-vr-introduction/images/switch_platform.jpg)

### Device Simulation

We also want to be able to test our device in Unity without having to build to the headset.

- In the top menu, Select **Window > Package Manager**

- Search for the **Xr Interactions Tookit**
- Import **XR Device Simulator** in the Samples tab.

![VR core template](https://uwetom.github.io/media-production-worksheets/wk17-vr-introduction/images/device_simulation.jpg)

- Close the **Package Manager**

 We now  need to tell Unity to use the Simulation when playing the scene in Unity.

- Go back into **File > Project Settings** and open **Player Settings...**

![VR core template](https://uwetom.github.io/media-production-worksheets/wk17-vr-introduction/images/player_settings.jpg)

- At the bottom, in **XR Plug-in Management**, in the windows tab, change the plugin to **XR Simulation**

![VR core template](https://uwetom.github.io/media-production-worksheets/wk17-vr-introduction/images/xr_settings.jpg)

- Finally, in the **Project Validation** Section check for any issues issues in the 
window and Android tabs and press **Fix all**


## Open Starter assets scene




