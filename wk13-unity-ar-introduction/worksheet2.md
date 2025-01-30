
[Back](https://uwetom.github.io/media-production-worksheets)

## Starting Project

This worksheet continues on from the template project you created last week.

If you do not have your project you can clone this one:

[https://github.com/uwetom/ar_template](https://github.com/uwetom/ar_template)

# Position Virtual Object

Last week we made a simple application with a cube, If you placed the cube at the origin of your scene. Normally the origin corresponds to the, but does not correspond to anything specifically in the real world.

We want to be able to decide exactly where object will appear in the real world.


## Tracked Image

The first way we will do this is with a tracked image.

This allows us to link virtual 3D objects to real images.

This image can be anything we want, but for accurate tracking Unity recommends:

- Size must be at least 300 x 300 pixels.
- Format must be PNG or JPG.
- Image can be black and white or colour but must have strong contrast.
- Image should avoid repeated patterns.

I have created a Unity package with some simple assets in it to get us started. 

[unity ship package download](https://github.com/uwetom/media-production-worksheets/raw/refs/heads/master/wk13-unity-ar-introduction/assets/ship.unitypackage)

- Download it and drag it into the assets panel in Unity to include it in your project
- Save the template scene with a new name in the scenes folder ("tracked_image_scene")
- Delete the cube from the scene

### Tracked image manager

The tracked image manager component manages all the images we want to track.

<iframe src="https://uwe.cloud.panopto.eu/Panopto/Pages/Embed.aspx?id=67d369cb-c479-4dc7-8732-b21f00951b6a&autoplay=false&offerviewer=true&showtitle=false&showbrand=false&captions=false&interactivity=all" height="405" width="720" style="border: 1px solid #464646;" allowfullscreen allow="autoplay" aria-label="Panopto Embedded Video Player" aria-description="unity - tracked image manager" ></iframe>

### Instantiate a prefab

Now we can create a script to instantiate our prefab on the image.

<iframe src="https://uwe.cloud.panopto.eu/Panopto/Pages/Embed.aspx?id=09532d13-dd25-4ab8-8bb5-b21f0096e46c&autoplay=false&offerviewer=true&showtitle=false&showbrand=false&captions=false&interactivity=all" height="405" width="720" style="border: 1px solid #464646;" allowfullscreen allow="autoplay" aria-label="Panopto Embedded Video Player" aria-description="Unity - add virtual object" ></iframe>

#### Finished Script
```
using System.Collections;
using System.Collections.Generic;
using UnityEngine;
using UnityEngine.XR.ARFoundation; // include xr library

public class TrackImage : MonoBehaviour
{
    [SerializeField]
    ARTrackedImageManager m_TrackedImageManager; 
    public GameObject shipPrefab; //Prefab you want to appear on marker image
    
    void OnEnable() => m_TrackedImageManager.trackedImagesChanged += OnChanged;

    void OnDisable() => m_TrackedImageManager.trackedImagesChanged -= OnChanged;

    void OnChanged(ARTrackedImagesChangedEventArgs eventArgs)
    {
    	// When the camera picks up a new image marker Unity adds a game object to it called newImage, this will stick to maker.
        foreach (ARTrackedImage newImage in eventArgs.added)
        {
        	// Create new copy of your prefab
        	GameObject newObject = GameObject.Instantiate(shipPrefab);
        	// parent prefab to the newImage so that they stick together.
			newObject.transform.SetParent(newImage.transform, false);
        }
    }
}

```

## Build and Test the Scene

We can now build and test the scene again on our device.

- First, on your Android device delete the previous build buy holding down on it and dragging it to delete.
- Go to **File > Build Settings** and add the current scene, untick the old template scene.
- Check You **run device** is still connected and selected and press build and run.
- Name the build something different than before.

If you point your camera at your image the model should appear.

<iframe src="https://uwe.cloud.panopto.eu/Panopto/Pages/Embed.aspx?id=e3e42657-f347-4b16-909d-b21e00b86980&autoplay=false&offerviewer=true&showtitle=false&showbrand=false&captions=false&interactivity=all" height="405" width="720" style="border: 1px solid #464646;" allowfullscreen allow="autoplay" aria-label="Panopto Embedded Video Player" aria-description="android ship demo" ></iframe>

## Virtual Environment

You may not always have an Android device available for testing and as your project expands it can take a while to do a full build each time you need to test.

To get around this you can create a virtual environment in Unity.

<iframe src="https://uwe.cloud.panopto.eu/Panopto/Pages/Embed.aspx?id=94c4dac7-3a89-45f1-a3fe-b21f00b95897&autoplay=false&offerviewer=true&showtitle=false&showbrand=false&captions=false&interactivity=all" height="405" width="720" style="border: 1px solid #464646;" allowfullscreen allow="autoplay" aria-label="Panopto Embedded Video Player" aria-description="unity-xr simulation" ></iframe>


## Challenges

### Add sound

Now that we have a simple image marker scene working we can think about taking it further. In the script, after you instantiate the new prefab you can play a sounds, start an animation or a particle effect.

In the ship folder you can find a sound file, try to make this play when the ship is instantiated.

#### Solution
1. Add an audio source component to the xr origin.	
2. Add a public AudioClip variable to your script to hold your splash sound
	```public AudioClip sound;```
3 In your script, find the Audio source component
	```AudioSource source = GetComponent<AudioSource>();```
4 Use it to play your sound
	```source.PlayOneShot(sound);```

### Add multiple markers

In the ship folder you can find two boats and 2 images. Add both images to your image reference library and add to your script to a different boat for each image.

#### Solution
1. Add the second image to your image library and give it a different name.
2. In your script add another public gameObject variable to hold  a different prefab.
3. In your script, you can access the name of image, use this in an if statement to check if the name matches an image in your library.
	```newImage.referenceImage.name```
4. If it matches, instantiate the correct prefab.

<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE3MDYzNjc3MDcsMTA2NjQ0OTQwNywtMj
YyNDQ1MTMsLTIyOTg2MDIwMl19
-->