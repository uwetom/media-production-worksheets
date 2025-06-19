# VR Extras

This worksheet will cover some more advanced VR topics which may be useful for your projects

## Lighting

The VR template we are using has helpfully setup our project to maximise performance. lighting and shadows can be computationally expensive so the template has limited the number and quality of our lighting.

If you want to use more than one light you 


## Affordance


## Changing the controllers

- hands
- limit or change the functionality

## meta package - AR

## Designing a VR experience



### Add a Light

A torch is not functional without a light.

- **Right Click** on the torch and add a child object, rename it "Light"
- Add a **Light** component to it and change it to a spotlight.
- Rotate the light and move it to the front of the torch.

![torch object](https://uwetom.github.io/media-production-worksheets/wk18-more-vr/images/spotlight.jpg)

We now have a torch, but if you rotate the whole torch round, you should see it doesn't actually seem to create any light.
 
### Change Quality settings

The VR template we are using has helpfully setup our project to maximise performance. lighting and shadows can be computationally expensive so the template has limited the number and quality of our lighting.

We need to carefully adjust the settings to allow us to render our light.

<iframe src="https://uwe.cloud.panopto.eu/Panopto/Pages/Embed.aspx?id=e192d413-27fb-4b03-84d0-b26800d715d9&autoplay=false&offerviewer=true&showtitle=false&showbrand=false&captions=false&interactivity=all" height="405" width="720" style="border: 1px solid #464646;" allowfullscreen allow="autoplay" aria-label="Panopto Embedded Video Player" aria-description="unity vr - quality settings" ></iframe>

- To see the light more clearly, reduce the **intensity** of the **Directional Light** to 0.1.

![torch object](https://uwetom.github.io/media-production-worksheets/wk18-more-vr/images/directional_light.jpg)

- Test the scene again.

### Change grab position - Optional

By default the object is grabbed at its origin, for the torch it means it is pointing upward. We want to be able to control where it is grabbed.

<iframe src="https://uwe.cloud.panopto.eu/Panopto/Pages/Embed.aspx?id=56285cfa-1dd6-4aa8-b61b-b26800defa70&autoplay=false&offerviewer=true&showtitle=false&showbrand=false&captions=false&interactivity=all" height="405" width="720" style="border: 1px solid #464646;" allowfullscreen allow="autoplay" aria-label="Panopto Embedded Video Player" aria-description="unity vr - grab position" ></iframe>

### Toggle the light

Grabbing the torch uses the **Select** action. Now that it has been selected we can utilise its **Activate** action to turn the torch on and off. 

- Create a new Script in the **Scripts** folder and call it "TorchController".
- Drag the new script on the **Torch** in the **Hierarchy**

### Challlenge

Open the new script and add code to toggle the light on and off

#### Hints
- Make a new **Public** function and call it "ToggleLight"
- Create a Light variable and store the Light component in
	```c#
	Light torchLight = GetComponentInChildren<Light>();
	```
- Create an if statement to turn the light on if it is off and off if it is on.
- We can find out if the light is on using:
	```c#
	torchLight.isActiveAndEnabled
	```
- We can turn the component off using:
	```c#
	torchLight.enabled = false;
	```

### Solution


This is one possible solution:

```c#
	using System.Collections;
	using System.Collections.Generic;
	using UnityEngine;
		
	public class TorchController : MonoBehaviour{
		public void ToggleLight(){
			Light torchLight = GetComponentInChildren<Light>();
			if (torchLight.isActiveAndEnabled){
				torchLight.enabled = false;
			}else{
				torchLight.enabled = true;
			}
		}
	}
```


We can now hook this script up to the torch **activate** state.

<iframe src="https://uwe.cloud.panopto.eu/Panopto/Pages/Embed.aspx?id=ceefc0e5-75a1-46f2-9e5e-b26800e2bb44&autoplay=false&offerviewer=true&showtitle=false&showbrand=false&captions=false&interactivity=all" height="405" width="720" style="border: 1px solid #464646;" allowfullscreen allow="autoplay" aria-label="Panopto Embedded Video Player" aria-description="unity vr - add script to torch" ></iframe>

Think about other objects you could add which may be useful to activate.

## 3. Affordance - Optional

The Affordance system ([documentation](https://docs.unity3d.com/Packages/com.unity.xr.interaction.toolkit@2.5/manual/affordance-system.html)) allows you to create audio and visual feedback to the user about the current state of the object.

We will use it to play a sound when the user picks up and turns the light on and off.

- First download the following sounds (or find your own) and add them to your assets.

	[pickup sound](https://uwetom.github.io/media-production-worksheets/wk18-more-vr/assets/click.wav)
	[turn on sound](https://uwetom.github.io/media-production-worksheets/wk18-more-vr/assets/bubbleclick.wav)

<iframe src="https://uwe.cloud.panopto.eu/Panopto/Pages/Embed.aspx?id=c9b3d362-8cb0-467d-b3ce-b26800e59a19&autoplay=false&offerviewer=true&showtitle=false&showbrand=false&captions=false&interactivity=all" height="405" width="720" style="border: 1px solid #464646;" allowfullscreen allow="autoplay" aria-label="Panopto Embedded Video Player" aria-description="Unity VR - affordance" ></iframe>



### Challenge

Generate a new object in the scene when the button is clicked.

#### Hints

- Create a new script with a **public** function on it and drag it onto the canvas button.
- Turn your torch or cube into a prefab ([Create prefab](https://docs.unity3d.com/Manual/CreatingPrefabs.html)), (add a ridgidbody component to the cube to allow it to fall)
- Instantiate a new prefab in the script ([Instantiate documentation](https://docs.unity3d.com/6000.0/Documentation/ScriptReference/Object.Instantiate.html))
- Use the **on Click** box on the **Button** to call the function

 
<details>
<summary>Solution</summary>
<iframe src="https://uwe.cloud.panopto.eu/Panopto/Pages/Embed.aspx?id=95b1a9f7-3aac-444c-add8-b26800edfc1b&autoplay=false&offerviewer=true&showtitle=false&showbrand=false&captions=false&interactivity=all" height="405" width="720" style="border: 1px solid #464646;" allowfullscreen allow="autoplay" aria-label="Panopto Embedded Video Player" aria-description="unity vr - create torch" ></iframe>
</details>
