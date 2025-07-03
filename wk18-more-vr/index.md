[Back](https://uwetom.github.io/media-production-worksheets)

# VR Interactions

In this worksheet we will learn how to interact with 3D objects in our scene.

## Open a project

- Open last weeks Unity Project, or create a new VR Core project

![vr core template](https://uwetom.github.io/media-production-worksheets/wk17-vr-introduction/images/new_project_6.jpg)

If you created a new VR core project you will need to set it up like last week. You can go back and look at [section 3 in last weeks workshop](https://uwetom.github.io/media-production-worksheets/wk17-vr-introduction/) 

## Create new Scene

- Open the **Basic Scene** inside the Scenes folder.

![Basic scene](https://uwetom.github.io/media-production-worksheets/wk17-vr-introduction/images/basicscene.jpg)

- Save it back into the Scene folder and name it "Interactions".
- Press the play button to make sure your scene plays in the simulator and you can move around.


## 1. Teleportation

Many users Can feel motion sickness when in VR, as a creator, it is your responsibility to minimise this as much as you can in your project and consider the VR experience of your Users.

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

Notice that although you can select a




## 2. Simple Interactable

To allow the XR rig to interact with objects in the scene we need two parts, an **Interactor** component on the XR rig, and an **Interactable** component on the object.

The most basic type of interactable is a **simple interactable**, this will allow us to detect when a user hovers over and selects an object with the controller.

- Create a cube and move it away from the origin so it's not on to of the rig.
- Add a **XR Simple Interactable** component to the cube

![vr core template](https://uwetom.github.io/media-production-worksheets/wk17-vr-introduction/images/xr_simple_interactable.jpg)

The cube will now be able to detect if the user interacts with it but we have to add a script and tell it what we want to do.

- Create a new Script and add 2 public functions which we can call when the user hovers and selects the cube

```c#
public void hoverEnter()
{
    Debug.Log("hover entered");
}

public void selected()
{
    Debug.Log("selected");
}

```

- Go back to unity and fix any errors that appear in the console.

### Connect the script to the Simple Interactable component






// video showing how to connect the script to the component






- Test your project on the simulator to see if you get the correct console logs.

### Challenge 1

- When the user hovers over the cube, change its colour

Hint:

```c#
GetComponent<Renderer>().material.SetColor("_BaseColor",Color.red);
```

- Make the cube disappear when activated

Hint:
```c#
DestroyObject(gameObject);
```

## 3. Grab Interactable

Next we can try a **Grab interactable** to allow us to pick up objects in our scene.

First we need some objects, we could use another cube, but a real 3D model is more interesting.

- Download the following unity package and drag it into your assets panel

[Kenney.nl objects](https://uwetom.github.io/media-production-worksheets/wk18-more-vr/assets/kenney_objects.unitypackage) 

The package contains assets from the free resourse kenney.nl

- Drag the pizza cutter into your scene and move it in front of the cube.

![vr core template](https://uwetom.github.io/media-production-worksheets/wk17-vr-introduction/images/pizza_cutter.jpg)

We can now turn it into an interactable

- Add an **XR Grab Interactable** component to the object

Notice that it also added a **Rigidbody** component automatically.

The cube already had a collider on it, but if you use your own object it will not have one.

- Add a **Mesh Collider** component to the pizza cutter and set it to **convex** ( you see a green mesh around the object)

![vr core template](https://uwetom.github.io/media-production-worksheets/wk17-vr-introduction/images/mesh_collider.jpg)

You can now try this out in the simulator. You should be able to pick up the pizza cutter using grab.

### Grab properties

Grab interactable have a few useful properties we can change to impove the experience.

#### Near attach

We want the pizza cutter to stick the controller when picked up

- On the **XR Grab Interactable** component, change the **far attach mode** to **near**

![vr core template](https://uwetom.github.io/media-production-worksheets/wk17-vr-introduction/images/far_attach.jpg)

#### Attach position

Currently, the pizza cutter will be picked up at its center. But we can move it to somewhere more appropriate.

- **Right click** on the object and choose **Create empty**
- Rename the new object to **attachPoint**

![vr core template](https://uwetom.github.io/media-production-worksheets/wk17-vr-introduction/images/attach_point.jpg)

- Move the attach point to the middle of the handle, we can also rotate it, but this may take a few tries to get get right.

- lastly, we need to drag the attach point object onto the **attach_transform** field on the **XR Grab Interactable** component.

![vr core template](https://uwetom.github.io/media-production-worksheets/wk17-vr-introduction/images/attach_transform_field.jpg)

#### Attach a script



[<img src="https://uwetom.github.io/media-production-worksheets/wk17-vr-introduction/images/xr_simulator_video.jpg">](https://uwe.cloud.panopto.eu/Panopto/Pages/Viewer.aspx?id=c037b363-6479-49f1-89ce-b30001106ff9)





[<img src="https://uwetom.github.io/media-production-worksheets/wk18-more-vr/images/pizza_video.jpg">](https://uwe.cloud.panopto.eu/Panopto/Pages/Viewer.aspx?id=b85003b4-643d-40e1-abdc-b30001142c77)

[Kenney.nl objects](https://uwetom.github.io/media-production-worksheets/wk18-more-vr/assets/kenney_objects.unitypackage)

[sounds](https://uwetom.github.io/media-production-worksheets/wk18-more-vr/assets/sounds.zip)


## 4. Extra - More interactions

If you are interested in exploring other VR interactions you can find another demo scene in your project

- Open **DemoScene** in **Assets\Samples\XR Interaction Toolkit\3.1.1\Starter Assets**

- Explore the demo

Unity has also created an extensive demo scene containing lots of examples of interactions you can use

[https://github.com/Unity-Technologies/XR-Interaction-Toolkit-Examples](https://github.com/Unity-Technologies/XR-Interaction-Toolkit-Examples)

At the time of writing this worksheet the project only worked with Unity 2022, here is a version which works with Unity 6

[https://github.com/uwetom/XR-Interaction-Toolkit-Examples](https://github.com/uwetom/XR-Interaction-Toolkit-Examples)
 
### Documentation

[3D interactions](https://docs.unity3d.com/Packages/com.unity.xr.interaction.toolkit@3.2/manual/object-interaction.html)

[Affordance documentation](https://docs.unity3d.com/Packages/com.unity.xr.interaction.toolkit@3.2/manual/affordance-system.html)