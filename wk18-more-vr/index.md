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

This basic component will let us detect if the user has interacted with an object.

- Add a cube to the scene
- Add a **Simple Interactable** component to it.

Create a new script

add the following code to it

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

On the Simple interactable, find the Interactable events and add the function

test it out,

the hover is obvious
selected works on grab (g) 
activated works on trigger after the object has been selected.

You can access the events on all interactables, including the grab interactable you used last week work in the same way.

### Button

There are more advanced examples in the template.

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
    private void OnTriggerEnter(collider other)
    {
        Debug.Log(other.gameObject.name);
    }
'''

### UI






-- build optimisation

