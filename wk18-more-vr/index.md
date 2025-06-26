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

## 1. Simple Interactable

To allow the XR rig to interact with objects in the scene we need two parts, an **Interactor** component on the XR rig, and an **Interactable** component on the object.

The most basic type of interactable is a **simple interactable**, this will allow us to detect when a user hovers over and selects an object with the controller.

- Create a cube and move it away from the origin so it's not on to of the rig.
- Add a **XR Simple Interactable** component to the cube

![vr core template](https://uwetom.github.io/media-production-worksheets/wk17-vr-introduction/images/xr_simple_interactable.jpg)

The cube will now be able to detect if the user interacts with it but we have to add a script and tell it what we want to do.

- Create a new Script and add 3 public functions which we can call when the user hovers, selects activate the cube.

```c#
public void hoverEnter()
{
    Debug.Log("hover entered");
}

public void selected()
{
    Debug.Log("selected");
}

public void activated()
{
    Debug.Log("activated");
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

## 2. Grab Interactable

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











[<img src="https://uwetom.github.io/media-production-worksheets/wk17-vr-introduction/images/xr_simulator_video.jpg">](https://uwe.cloud.panopto.eu/Panopto/Pages/Viewer.aspx?id=c037b363-6479-49f1-89ce-b30001106ff9)

We can also add grab an interactable to our own objects

[<img src="https://uwetom.github.io/media-production-worksheets/wk18-more-vr/images/pizza_video.jpg">](https://uwe.cloud.panopto.eu/Panopto/Pages/Viewer.aspx?id=b85003b4-643d-40e1-abdc-b30001142c77)

[Kenney.nl objects](https://uwetom.github.io/media-production-worksheets/wk18-more-vr/assets/kenney_objects.unitypackage)

[sounds](https://uwetom.github.io/media-production-worksheets/wk18-more-vr/assets/sounds.zip)

## 3. Affordance

It is useful to know how to call a script when interacting with an object, however, if we only want to provide audio or visual feedback to the user that an object is interactable Unity has a better solution.

Adding an Affordance component to an object allows you to provide consistent feedback to a user.


// add another object
// add audio and visual affordance to it


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