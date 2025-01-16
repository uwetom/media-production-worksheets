[Back](https://uwetom.github.io/media-production-worksheets)

# VR Interactions

We want to be able to interact with our environment, triggering sounds, animations and scripts.

## Open a project

- Open last weeks Unity Project, or create a new VR Core project.

![vr core template](https://uwetom.github.io/media-production-worksheets/wk17-vr-introduction/images/vr_core.jpg)

- Open the **Basic Scene** inside the Scenes folder.

![Basic scene](https://uwetom.github.io/media-production-worksheets/wk17-vr-introduction/images/basicscene.jpg)

- Save it back into the Scene folder and name it "interactions".

## Simple Interactable

To allow the xr rig to interact with objects in the scene we need two parts, and **Interactor** component on the rig, and an **Interactable** component on the object.

<iframe src="https://uwe.cloud.panopto.eu/Panopto/Pages/Embed.aspx?id=44ca29a5-e698-41cd-9e8c-b26600e01254&autoplay=false&offerviewer=true&showtitle=false&showbrand=false&captions=false&interactivity=all" height="405" width="720" style="border: 1px solid #464646;" allowfullscreen allow="autoplay" aria-label="Panopto Embedded Video Player" aria-description="Unity vr - simple interactable" ></iframe>
 
'''
	public void Hovered()
    {
        Debug.Log("hovered");
    }

    public void Selected()
    {
        Debug.Log("Selected");
        GetComponent<Renderer>().material.SetColor("_BaseColor", Color.red);
    }
    public void Activated()
    {
        Debug.Log("activated");
    }
'''

## Grab

A more advance interaction is a grab, this allows you to pick up objects in your scene.

- Add a cylinder to your scene
- rename it to "staff"
- Scale it so it is long and thin.
- Add a **Rigidbody** component to it so that it is effected by gravity.
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

### Poke and Affordance

In the demo template there are more advanced version of the simple interactable

- Search for "push" in the assets
- Drag the **Push Button** prefab into your scene.

If you select the button in the **Hierarchy** you can see it has a **Simple Interactable** component, you can use the events just like you did on the cube.

It also has a **poke Filter** components which allow it to be 'physically' pressed down with the controller.

Lastly, it has an **poke Affordance** object and components. Affordance components give the player feedback, here **Color Material Propery Affordance** changes the color of the button when it is selected and pushed down.

- Download the following sound file and add it to your project.

[honk sound](https://uwetom.github.io/media-production-worksheets/wk18-more-vr/assets/honk.mp3)

- Add an **Audio Source** component to the button
- Add the sound to the **Audio Resource** input on the **Audio Source**

![honk sound](https://uwetom.github.io/media-production-worksheets/wk18-more-vr/images/audio_source.jpg)

- On the **XR Simple Interactable** component of the button, play the audio source when it is selected.

 ![play audio](https://uwetom.github.io/media-production-worksheets/wk18-more-vr/images/play_audio.jpg)

Now play the scene, the sound should play when you it the button.

### UI

UI works broadly in the same way as it does with the first person controller, the main difference is that you want the canvas to be in **World space**

- **Right click** in the Hierarchy and choose **XR > UI CANVAS**

 ![canvas](https://uwetom.github.io/media-production-worksheets/wk18-more-vr/images/ui_canvas.jpg)

-On the canvas component, scale the canvas down to 0.02.

Notice that the render mode is **World Space**

 ![canvas sale](https://uwetom.github.io/media-production-worksheets/wk18-more-vr/images/canvas_scale.jpg)
 
- Add a **UI Panel, Textbox and Button** to the canvas and scale and position appropriately.

 ![canvas sale](https://uwetom.github.io/media-production-worksheets/wk18-more-vr/images/ui_panel.jpg)




### Build

Build your scene to a headset and test it out.

### Challenge - Interactive scene

Create a simple interactive scene including

- Objects to pick up, make sure you 



### Documentation

[XR Interaction 2.5 documentation](https://docs.unity3d.com/Packages/com.unity.xr.interaction.toolkit@2.5/manual/samples-starter-assets.html)