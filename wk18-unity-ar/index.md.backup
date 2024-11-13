## More Unity AR - Planes and faces


## Template

At the start of the last worksheet you created a template AR project.

I have created a GitHub repository with this template project which you can **fork** and **clone**

[https://github.com/uwetom/unity_ar_template](https://github.com/uwetom/unity_ar_template)

![fork button on github.com](https://github.com/uwetom/media-production-worksheets/blob/master/wk18-unity-ar/images/fork.jpg?raw=true)

## New Scene

Duplicate the template scene and rename it to "plane_tracking"

## Turn on the virtual environment

We want to test our new project in a virtual environment so we need to turn it on like we did last week.

- Go to **Edit > Project Settings**
- Under **XR Plug-in Management** turn on XR-Simulation

![turn on XR Simulation](https://github.com/uwetom/media-production-worksheets/blob/master/wk18-unity-ar/images/xr_simulation.jpg?raw=true)


## Interaction toolkit

We want to interact with the objects in our scene by touching the screen.

We could manually create the interactions maps ourselves but instead we will add the interaction toolkit package which contains everything we need.


- go to **Windows > Package Manager**
- In Unity Registry, search for "XR"
- Install the **XR Interaction Toolkit**

---------------ALSO INCLUDE starter assets and AR starter assets?----------


add 3d object

add **xr simple interactable** to object


- create script and add to empty game object

```
    public void CubeSelected(SelectEnterEventArgs data)
    {
        Debug.Log("hello" +  data.interactableObject.transform.name);
    }
    
```



On Xr origin

add input action manager with default input actions
add ar raycast manager
delete controllers on camera offset

add new game object

add interaction group
add xr screen space controller
	- add touchscreen gestures/tap start position
	- add touchscreen gestures/drag current posision

add xray interactor
 - hook up script to select event OR to the cube?
 
 
 TEst and look for console log
 
-------------

add world space ui to shape
animate in ui on click.

done







