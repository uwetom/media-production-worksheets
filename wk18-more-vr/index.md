[Back](https://uwetom.github.io/media-production-worksheets)


# VR Interactions

We want to be able to interact with our environment, triggering sounds, animations and scripts.

## Open a project

- Open last weeks Unity Project, or create a new VR Core project.

![Locomotion System](https://uwetom.github.io/media-production-worksheets/wk17-vr-introduction/images/vr_core.jpg)

- Open the **Basic Scene** inside the Scenes folder.

![Locomotion System](https://uwetom.github.io/media-production-worksheets/wk17-vr-introduction/images/basic_scene.jpg)

- Save it back into the Scene folder with a new name

## Simple Interactable

- VIDEO

We can add an **Interactable** component to an object in our scene to allow the rig to interact with it.

This most basic **Interactable** component is a **Simple Interactable** which we can use to work out if our user has interacted.

- Add a cube to your scene.
- Add a **Simple Interactable** component to it.

By giving an object an interactable we can detect some events

**Hover** - When the users controller or its ray hovers collides with our object
**Select** - When the user presses the grab button while hovering
**Activate** - When the user presses the trigger button while the object is selected.


- Add the following code to your script

'''
public void Hovered()
    {
        Debug.Log("hovered");
    }

    public void Selected()
    {
        Debug.Log("Selected");
    }
    public void Activated()
    {
        Debug.Log("activated");

    }
'''

- On the Simple interactable, find the Interactable events and add the functions.


test it out on the simulator.

You can access the events on all interactables, including the grab interactable you used last week work in the same way.


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



### Button

There are more advanced interactable examples in the template.

- Search for "push" in the assets
- Drag the **Push Button** prefab into your scene.

If you select the button in the **Hierarchy** you can see it has a **Simple Interactable** component, you use the events just like you did on the cube.

It also has a couple of **poke** components which allow it to be 'physically' pressed down.

Lastly, it has an **Affordance** object and components. Affordance components give the player feedback, here **Color Material Propery Affordance** changes the color of the button when it is selected and pushed down.

### Trigger

OnTriggerEnter works the same way as it does with the first person controller.

- add another cube
- change its box collider to **is trigger**
- add this to your script

'''
     private void OnTriggerEnter(Collider other)
  {
      Debug.Log(other.gameObject.name);
      if (other.gameObject.name == "XR Origin (XR Rig)")
      {
         GetComponent<Renderer>().material.SetColor("_BaseColor", Color.red);
      }
    
  }
'''

### UI

UI works broadly in the same way as it does with the first person controller, the main difference is that you want the canvas to be in **World space**








### Challenge



### Documentation

[XR Interaction 2.5 documentation](https://docs.unity3d.com/Packages/com.unity.xr.interaction.toolkit@2.5/manual/samples-starter-assets.html)

- interactables
- 
worksheet 2


-affordance?

-- grabables
-- buttons
-- ui
-- 
<!--stackedit_data:
eyJoaXN0b3J5IjpbMjA5MjY2NTU0XX0=
-->