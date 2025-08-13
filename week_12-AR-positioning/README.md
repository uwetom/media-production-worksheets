
# Track an image

Last week we learnt how to create a simple AR scene, how to test it in the simulator and build it to a real device.

This week we will look into how to position our 3D object at specific locations in the real world.

## 1. Create new scene

You can carry on from last weeks worksheet, or make a new AR project like you did last week.

- Create a new empty scene.

- Like last week, add an **XR Origin** and **AR Session** (hint: right click in the hierarchy and choose XR)

![Add xr and ar session](images/xr_ar_session.jpg)

- Save the scene.

## 2. Tracked image

Last week we made a simple application with a cube, If you placed the cube at the origin of your scene. Normally the origin corresponds to the position of your camera when the scene opens. It does not correspond to anything specifically in the real world.

But we want to create an experience in a specific location, so want to be able to decide exactly where object will appear in the real world.

One way we can control where our objects appear is by using tracked images.

This allows us to link virtual 3D objects to real images.

This image can be anything we want, but for accurate tracking Unity recommends:

- Size must be at least 300 x 300 pixels
- Format must be PNG or JPG.
- Image should avoid repeated patterns.
- Avoid images with that contain a large number of geometric features, or very few features (e.g. barcodes, QR codes, logos and other line art)

> [!NOTE]
> You can find more detailed recomendations here [ARCore tracked image recomendations](https://developers.google.com/ar/develop/augmented-images)

> [!TIP]
> Google has a tool that you can use to see the quality of your image [arcoreimg tool](https://developers.google.com/ar/develop/augmented-images/arcoreimg#macos)

- Download this image and drag it into your assets folder

[sea10x10.jpg](assets/sea10x10cm.jpg)

## 3. Tracked image manager

The tracked image manager component manages all the images we want to track.

- Add a tracked image manager component to your Rig

[<img src="images/tracked_imag_manager_video.jpg"](https://uwe.cloud.panopto.eu/Panopto/Pages/Viewer.aspx?id=9d6bb1d7-8616-40bb-9069-b32b00c41f36)

### 4. Import a 3d model

We want a 3D object to appear on our tracked image.

- Download this fbx file and add it to your assets

[wind turbine model](assets/turbine.fbx)

We can now create a script to instantiate our 3d model onto the tracked image when it is found

[<img src="images/tracked-image-script-video.jpg">](https://uwe.cloud.panopto.eu/Panopto/Pages/Viewer.aspx?id=a9c04acb-d421-4cdb-9c88-b32b00cc1ba9)

[AR foundation Documentation](https://docs.unity3d.com/Packages/com.unity.xr.arfoundation@6.1/manual/features/image-tracking/artrackedimagemanager.html)

#### Finished Script

This is the finished script from the video, try to only use this if you get stuck.
```
using UnityEngine;
using UnityEngine.XR.ARFoundation;
using System.Collections.Generic;
using UnityEngine.XR.ARSubsystems;


public class ImageTracker : MonoBehaviour
{

    [SerializeField]
    ARTrackedImageManager m_ImageManager;
    public GameObject turbinePrefab;

void OnEnable() => m_ImageManager.trackablesChanged.AddListener(OnChanged);

void OnDisable() => m_ImageManager.trackablesChanged.RemoveListener(OnChanged);

void OnChanged(ARTrackablesChangedEventArgs<ARTrackedImage> eventArgs)
{
        foreach (var newImage in eventArgs.added)
        {
            GameObject newObject = Instantiate(turbinePrefab);
            newObject.transform.SetParent(newImage.transform, false);

        // Handle added event
        }

    foreach (var updatedImage in eventArgs.updated)
    {
        // Handle updated event
    }

    foreach (var removed in eventArgs.removed)
    {
        // Handle removed event
        TrackableId removedImageTrackableId = removed.Key;
        ARTrackedImage removedImage = removed.Value;
    }
}

}

```


## 5. Test in the simulator

You can now press play to test the scene in the simulator

Helpfully the simulator has a simulated image, move aroud the scene until you see you turbine.

![simulator with turbine](images/simulator_with_turbine.jpg)

## Adjust simulator

You may notice that the turbine is on its side.

You can adjust the angle of the simulated image plane by editing the environment.

[<img src="images/adjust_simulator.jpg">](https://uwe.cloud.panopto.eu/Panopto/Pages/Viewer.aspx?id=fe6c7413-df5e-4795-a889-b32b00e708e1)


## 6. Build

We can now build and test the scene on our device just like we did last week and try it with a real image.

- Build the scene to an device.

If you point your camera at your image the model should appear.

Make sure this works for you before you carry on to the next step.


## 7. Optional Challenges 1

These challenges are optional, but will help you with your final project.

### Play a sound when the prefab is instantiated

- Add an Audio source to the xr Origin and attach a sound to it.

- Use your existing script to play the sound when the tracked image is found.

### Animate the turbine

If you open up the turbine in the assets panel you can see it has an animation on it. 

- Try to make the animation play in the scene.

## 8. More complex objects.

We have just instantiated one prefab onto our tracked image, but that prefab can be as complex as we like.

- **Right click in the Hierarchy to create a new empty game object
- Rename it "Turbine Environment"
- Add multiple turbines, and maybe other shapes and objects to the new object.
- Drag the object into the Assets panel to turn it into a prefab
- Delete the object from the hierarchy
- drag the new prefab onto the turbine prefab slot on your script
- test the scene in the simulator

## 9. Optional Challenges 2

### multiple markers

You can track multiple markers at the same time

- Find and add another image to the library just like you did at the start of this worksheet. When you add them you can see they have a name.

In your existing script you can use that name to instantiate different prefabs

e.g.

```
 void OnChanged(ARTrackedImagesChangedEventArgs eventArgs)
    {
       
        foreach (ARTrackedImage newImage in eventArgs.added)
        {
            if(newImage.referenceImage.name == "sea") {
            	GameObject newObject = GameObject.Instantiate(turbinePrefab);
            newObject.transform.SetParent(newImage.transform, false);
            
            } else if(newImage.referenceImage.name == "beach") {
                	GameObject newObject = GameObject.Instantiate(otherPrefab);
            newObject.transform.SetParent(newImage.transform, false);
            }
            
        }
                
       }         

-

## References


["Wind Turbine" (https://skfb.ly/6QZUA) by iedalton is licensed under Creative Commons Attribution (http://creativecommons.org/licenses/by/4.0/).](https://skfb.ly/6QZUA)

[AR foundation Documentation](https://docs.unity3d.com/Packages/com.unity.xr.arfoundation@6.1/manual/index.html)
