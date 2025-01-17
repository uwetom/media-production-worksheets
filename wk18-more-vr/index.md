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

```
public void Hovered(){
	Debug.Log("hovered");
}
public void Selected(){
	Debug.Log("Selected");
	GetComponent<Renderer>().material.SetColor("_BaseColor",Color.red);
}

public void Activated(){
	Debug.Log("activated");
}
```

## Grab

A more advance interaction is a grab, this allows you to pick up objects in your scene.

### Make a simple torch

- Add a cylinder to your scene.
- Rename it to "torch".
- Scale it to 0.15
- Add a **Rigidbody** component to it so that it is effected by gravity.
- Add an **XR Grab Interactable** component to it.

![torch object](https://uwetom.github.io/media-production-worksheets/wk18-more-vr/images/torch1.jpg)

We can now test the scene, We should be able to pick up the torch.

<iframe src="https://uwe.cloud.panopto.eu/Panopto/Pages/Embed.aspx?id=99a84900-005e-4a34-ba3b-b26800dd5b26&autoplay=false&offerviewer=true&showtitle=false&showbrand=false&captions=false&interactivity=all" height="405" width="720" style="border: 1px solid #464646;" allowfullscreen allow="autoplay" aria-label="Panopto Embedded Video Player" aria-description="unity vr - test light 1" ></iframe>

### Add a Light

A torch is not functional without a light.

- **Right Click** on the torch and add a child object, rename it "Light"
- Add a **Light** component to it and change it to a spotlight.
- Rotate the light and move it to the front of the torch.

![torch object](https://uwetom.github.io/media-production-worksheets/wk17-vr-introduction/images/spotlight.jpg)

  

We now have a torch, but if you rotate the whole torch round, you should see it doesn't seem to create any light.

  

### Change Quality settings

  

The VR template we are using has helpfully setup our project to maximise performance. lighting and shadows can be computationally expensive so the template has limited the number and quality of our lighting.

  

We need to carefully adjust the settings to allow us to render our light.

  

<iframe src="https://uwe.cloud.panopto.eu/Panopto/Pages/Embed.aspx?id=e192d413-27fb-4b03-84d0-b26800d715d9&autoplay=false&offerviewer=true&showtitle=false&showbrand=false&captions=false&interactivity=all" height="405" width="720" style="border: 1px solid #464646;" allowfullscreen allow="autoplay" aria-label="Panopto Embedded Video Player" aria-description="unity vr - quality settings" ></iframe>

  

- To see the light more clearly, reduce the **intensity** of the **Directional Light** to 0.1.

  

![torch object](https://uwetom.github.io/media-production-worksheets/wk17-vr-introduction/images/directional_light.jpg)

  

- Test the scene again.

  

### Change grab position

  

By default the object is grabbed at its origin, for the torch it means it is pointing upward. We want to be able to control where it is grabbed.

  

<iframe src="https://uwe.cloud.panopto.eu/Panopto/Pages/Embed.aspx?id=56285cfa-1dd6-4aa8-b61b-b26800defa70&autoplay=false&offerviewer=true&showtitle=false&showbrand=false&captions=false&interactivity=all" height="405" width="720" style="border: 1px solid #464646;" allowfullscreen allow="autoplay" aria-label="Panopto Embedded Video Player" aria-description="unity vr - grab position" ></iframe>

  

### Toggle the light

  

Grabbing the torch uses the **Select** action. Now that it has been selected we can utilise its **Activate** action to turn the torch on and off.

  

- Create a new Script in the **Scripts** folder and call it "TorchController".

- Drag the new script on the **Torch** in the **Hierarchy**

  

Open the new script and try to do the following, the completed script is shown bellow if you get stuck.

  

- Make a new **Public** function and call it "ToggleLight"

- Create a Light variable and store the Light component in

  

```

Light torchLight = GetComponentInChildren<Light>();

```

  

- Create an if statement to turn the light on if it is off and off if it is on.

  

- We can find out if the light is on using:

  

```

torchLight.isActiveAndEnabled

```

- We can turn the component off using:

```

torchLight.enabled = false;

```

  

Solution

  

This is one possible solution:

  

```

using System.Collections;

using System.Collections.Generic;

using UnityEngine;

  

public class TorchController : MonoBehaviour

{

public void ToggleLight()

{

Light torchLight = GetComponentInChildren<Light>();

  

if (torchLight.isActiveAndEnabled)

{

torchLight.enabled = false;

}

else

{

torchLight.enabled = true;

}

}

}

```

  

We can now hook this script up to the torch **activate** state.

  

<iframe src="https://uwe.cloud.panopto.eu/Panopto/Pages/Embed.aspx?id=ceefc0e5-75a1-46f2-9e5e-b26800e2bb44&autoplay=false&offerviewer=true&showtitle=false&showbrand=false&captions=false&interactivity=all" height="405" width="720" style="border: 1px solid #464646;" allowfullscreen allow="autoplay" aria-label="Panopto Embedded Video Player" aria-description="unity vr - add script to torch" ></iframe>

  

## Affordance ([documentation](https://docs.unity3d.com/Packages/com.unity.xr.interaction.toolkit@2.5/manual/affordance-system.html))

  

The Affordance system allows you to create audio and visual feedback to the user about the current state of the object.

  

We will use it to play a sound when the user picks up and turns the light on and off.

  

- First download the following sounds (or find your own) and add them to your assets.

  

[pickup sound](https://uwetom.github.io/media-production-worksheets/wk18-more-vr/assets/click.wav)

  

[turn on sound](https://uwetom.github.io/media-production-worksheets/wk18-more-vr/assets/bubbleClick.wav)

  

<iframe src="https://uwe.cloud.panopto.eu/Panopto/Pages/Embed.aspx?id=c9b3d362-8cb0-467d-b3ce-b26800e59a19&autoplay=false&offerviewer=true&showtitle=false&showbrand=false&captions=false&interactivity=all" height="405" width="720" style="border: 1px solid #464646;" allowfullscreen allow="autoplay" aria-label="Panopto Embedded Video Player" aria-description="Unity VR - affordance" ></iframe>

  

### UI

  

UI works broadly in the same way as it does with the first person controller, the main difference is that you want the canvas to be in **World space**

  

- **Right click** in the Hierarchy and choose **XR > UI CANVAS**

  

![canvas](https://uwetom.github.io/media-production-worksheets/wk18-more-vr/images/ui_canvas.jpg)

  

-On the canvas component, scale the canvas down to 0.02.

  

Notice that the render mode is **World Space**

  

![canvas sale](https://uwetom.github.io/media-production-worksheets/wk18-more-vr/images/canvas_scale.jpg)

- Add a **UI Panel, Textbox and Button** to the canvas (HINT: Right click one the canvas in the hierarchy, and choose )

- Change the width, height and font size in the **Instpector** to size the appropriately.

  

![canvas sale](https://uwetom.github.io/media-production-worksheets/wk18-more-vr/images/ui_panel.jpg)

  

We could use affordance to change the color or the button when it is highlighted, but its easier to just use the build in options.

  

![canvas sale](https://uwetom.github.io/media-production-worksheets/wk18-more-vr/images/button_colors.jpg)

Finally, we want to do something when the button is pressed.

  

### Challenge

  

Create a new torch when the button is clicked.

  

Hints

  

- Create a new script with a public function on it and drag it onto the canvas button

- Turn the torch into a prefab ([Create prefab](https://docs.unity3d.com/Manual/CreatingPrefabs.html))

- Instantiate a new torch in the script ([Instantiate documentation](https://docs.unity3d.com/6000.0/Documentation/ScriptReference/Object.Instantiate.html))

- Use the **on Click** box on the **Button** to call the function

  

Solution

  

<iframe src="https://uwe.cloud.panopto.eu/Panopto/Pages/Embed.aspx?id=95b1a9f7-3aac-444c-add8-b26800edfc1b&autoplay=false&offerviewer=true&showtitle=false&showbrand=false&captions=false&interactivity=all" height="405" width="720" style="border: 1px solid #464646;" allowfullscreen allow="autoplay" aria-label="Panopto Embedded Video Player" aria-description="unity vr - create torch" ></iframe>

  

### Documentation

  

[XR Interaction 2.5 documentation](https://docs.unity3d.com/Packages/com.unity.xr.interaction.toolkit@2.5/manual/samples-starter-assets.html)
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTExNjgzMjQ4NDIsMjA5MDkwNDMwOF19
-->