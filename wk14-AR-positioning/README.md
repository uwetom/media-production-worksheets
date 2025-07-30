

## Tracking an image

Last week we learnt how to create a simple AR scene, how to test it in the simulator and build it to a real device.

This week we will look into how to position our 3D object at specific locations in the real world.

### Create new scene

You can carry on from last weeks worksheet, or make a new AR project like you did last week.



- Create a new empty scene.

- Like last week, add an **XR Origin** and **AR Session** (hint: right click in the hierarchy and choose XR)

![Add xr and ar session](https://uwetom.github.io/media-production-worksheets/wk13-unity-ar-introduction/images/xr_ar_session.jpg)

- Save the scene.

# Position Virtual Object

Last week we made a simple application with a cube, If you placed the cube at the origin of your scene. Normally the origin corresponds to the position of your camera when the scene opens. It does not correspond to anything specifically in the real world.

But we want to be able to decide exactly where object will appear in the real world.

## Tracked Image
One way we can control where our objects appear is by using tracked images.

This allows us to link virtual 3D objects to real images.

This image can be anything we want, but for accurate tracking Unity recommends:

- Size must be at least 300 x 300 pixels.
- Format must be PNG or JPG.
- Image can be black and white or colour but must have strong contrast.
- Image should avoid repeated patterns.

I have created a Unity package with some simple assets in it to get us started. 

[unity ship package download](https://github.com/uwetom/media-production-worksheets/raw/refs/heads/master/wk13-unity-ar-introduction/assets/ship.unitypackage)

- Download it and drag it into the assets panel in Unity to include it in your project.
![Add ship package](https://uwetom.github.io/media-production-worksheets/wk13-unity-ar-introduction/images/add_ship_to_assets.jpg)

### Tracked image manager

The tracked image manager component manages all the images we want to track.

<iframe src="https://uwe.cloud.panopto.eu/Panopto/Pages/Embed.aspx?id=67d369cb-c479-4dc7-8732-b21f00951b6a&autoplay=false&offerviewer=true&showtitle=false&showbrand=false&captions=false&interactivity=all" height="405" width="720" style="border: 1px solid #464646;" allowfullscreen allow="autoplay" aria-label="Panopto Embedded Video Player" aria-description="unity - tracked image manager" ></iframe>

### Instantiate a prefab

Now we can create a script to instantiate our prefab on the image.

Follow along with this video.

[AR foundation Documentation](https://docs.unity3d.com/Packages/com.unity.xr.arfoundation@5.1/manual/index.html)

<iframe src="https://uwe.cloud.panopto.eu/Panopto/Pages/Embed.aspx?id=09532d13-dd25-4ab8-8bb5-b21f0096e46c&autoplay=false&offerviewer=true&showtitle=false&showbrand=false&captions=false&interactivity=all" height="405" width="720" style="border: 1px solid #464646;" allowfullscreen allow="autoplay" aria-label="Panopto Embedded Video Player" aria-description="Unity - add virtual object" ></iframe>



#### Finished Script

This is the finished script from the video, try to only use this if you get stuck.
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

We can now build and test the scene on our device just like we did last week.

- Save the current scene.
- Go to **File > Build Settings** and add the current scene, untick any other scenes.
- Plug your tablet in and approve the connection.
- Check **run device** is displays your device
- Press **build and run**

![Build](https://uwetom.github.io/media-production-worksheets/wk13-unity-ar-introduction/images/build.jpg)

- Create a folder called "Build" and save your build into it.

If you point your camera at your image the model should appear.

<iframe src="https://uwe.cloud.panopto.eu/Panopto/Pages/Embed.aspx?id=e3e42657-f347-4b16-909d-b21e00b86980&autoplay=false&offerviewer=true&showtitle=false&showbrand=false&captions=false&interactivity=all" height="405" width="720" style="border: 1px solid #464646;" allowfullscreen allow="autoplay" aria-label="Panopto Embedded Video Player" aria-description="android ship demo" ></iframe>

Make sure this works for you before you carry on to the next step.

## Virtual Environment

You may not always have an Android device available for testing and as your project expands it can take a while to do a full build each time you need to test.

To get around this you can create a virtual environment in Unity.

- Setup your virtual environment using this video:

<iframe src="https://uwe.cloud.panopto.eu/Panopto/Pages/Embed.aspx?id=94c4dac7-3a89-45f1-a3fe-b21f00b95897&autoplay=false&offerviewer=true&showtitle=false&showbrand=false&captions=false&interactivity=all" height="405" width="720" style="border: 1px solid #464646;" allowfullscreen allow="autoplay" aria-label="Panopto Embedded Video Player" aria-description="unity-xr simulation" ></iframe>

### Add sound

Now that we have a simple image marker scene working we can think about taking it further. In the script, after you instantiate the new prefab you can play a sounds, start an animation or a particle effect.

You can find a sound file in the ship folder.

- Add an **audio source** component to the xr origin object
- Drag the sound file onto it.
- Turn off **Play on Awake**

![Audio source](https://uwetom.github.io/media-production-worksheets/wk13-unity-ar-introduction/images/audio_source.jpg)

- In your script, at the top of the **OnChanged** function add a line  to find the Audio source component:
	```AudioSource source = GetComponent<AudioSource>();```
- Use it to play your sound when the prefab is instantiated. 
	```source.Play();```
- Test out the scene in your Simulated Environment

Your finished script should look like this
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
        AudioSource source = GetComponent<AudioSource>();

        // When the camera picks up a new image marker Unity adds a game object to it called newImage, this will stick to maker.
        foreach (ARTrackedImage newImage in eventArgs.added)
        {
            // Create new copy of your prefab
            GameObject newObject = GameObject.Instantiate(shipPrefab);
            // parent prefab to the newImage so that they stick together.
            newObject.transform.SetParent(newImage.transform, false);
            source.Play();
        }
    }
}
```

## More complex objects

We used a simple prefab of a ship in the last example, but your prefab can be as complex as you need it to be.

- Create an empty object in the **Hierarchy** and rename it "Ship Environment"
- Add multiple ships and other objects as children, you can find other objects in the ship folder.

![Multiple Objects](https://uwetom.github.io/media-production-worksheets/wk13-unity-ar-introduction/images/multiple_objects.jpg)

- Drag the "Ship Environment" object into the assets panel to turn it into a prefab ( it should turn blue in the hierarchy)

![Make prefab](https://uwetom.github.io/media-production-worksheets/wk13-unity-ar-introduction/images/Make_prefab.jpg)

- Delete the object from the hierarchy to remove it from the scene, the prefab should still be in your assets.
- Replace the Ship prefab in your script with the new prefab.

![Updateprefab](https://uwetom.github.io/media-production-worksheets/wk13-unity-ar-introduction/images/update_prefab.jpg)

- Build to your device to test.

## Challenge

### Add multiple markers

In the ship folder you can find another image in addition to the puddle image. 

- Add the second image to your image library and give it a different name.
- In your script add another public gameObject variable to hold  a different prefab.
- In your script, you can access the name of the  image, use this in an if statement to check if the name matches an image in your library.
	```newImage.referenceImage.name```
- If it matches, instantiate the correct prefab.

#### Finished script
Here is my finished script for reference, try to do it yourself first before checking it.
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
    public GameObject shipEnvironmentPrefab; //Prefab you want to appear on marker image

    void Start()
    {
        // Disable screen dimming
        Screen.sleepTimeout = SleepTimeout.NeverSleep;
    }

    void OnEnable() => m_TrackedImageManager.trackedImagesChanged += OnChanged;

    void OnDisable() => m_TrackedImageManager.trackedImagesChanged -= OnChanged;

    void OnChanged(ARTrackedImagesChangedEventArgs eventArgs)
    {
        AudioSource source = GetComponent<AudioSource>();

        // When the camera picks up a new image marker Unity adds a game object to it called newImage, this will stick to maker.
        foreach (ARTrackedImage newImage in eventArgs.added)
        {
            if(newImage.referenceImage.name == "puddle") {
                // Create new copy of your prefab
                GameObject newObject = GameObject.Instantiate(shipPrefab);
                // parent prefab to the newImage so that they stick together.
                newObject.transform.SetParent(newImage.transform, false);
            }else if(newImage.referenceImage.name == "boat")
            {
                GameObject newObject = GameObject.Instantiate(shipEnvironmentPrefab);
                newObject.transform.SetParent(newImage.transform, false);
            }
            source.Play();
        }
    }
}
```
## Challenge 2

Try to track images around the room
 I have take photos of some objects and posters in 2q25 for you to try

[2q25 images](https://uwetom.github.io/media-production-worksheets/wk13-unity-ar-introduction/assets/2q25_images.zip)

## Challenge 3

### Animation

- Animate one of the objects in the ship environment

## References

Ship assets
[https://kenney.nl/assets/pirate-kit](https://kenney.nl/assets/pirate-kit)
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTEyMTQ1MDg1NSwtODIyMjYzNzY5LC0xND
AxNjQ2MjQ3LC0yMTIzNjE3NTcyLC04MDgzOTM5MzgsMTU0NDg4
Mjg1MiwtNDgzNDAxMDIxLDE3NjY5MDI0ODUsMTA5NzY0OTQyLC
0xMDExNDQzMzM5LDU3NzQzODM4Myw2MTA4MTM0OTAsLTE3ODE3
MTExNjUsNzc1ODc4NzIyLC00ODg1NzEwMDUsNDk0NTUyNTUsLT
IwMzM4NDg5NDEsNjI3NTM0MTcxLC0yMDU4MjAxNzI5LDE1OTg1
OTMzMDNdfQ==
-->