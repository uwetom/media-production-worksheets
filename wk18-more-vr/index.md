[Back](https://uwetom.github.io/media-production-worksheets)

# VR Interactions

In this worksheet we will interact with objects in our scene and explore creating a user interface.

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

[<img src="https://uwetom.github.io/media-production-worksheets/wk17-vr-introduction/images/xr_simulator_video.jpg">](https://uwe.cloud.panopto.eu/Panopto/Pages/Viewer.aspx?id=8ee3d93f-6a2a-4705-b058-b30000fbf702)

```c#
public void hover(){
	Debug.Log("hover");
	GetComponent<Renderer>().material.SetColor("_BaseColor",Color.red);
}
public void unhover(){
	Debug.Log("unhover");
	
}
public void selected(){
	Debug.Log("selected");
	GetComponent<Renderer>().material.SetColor("_BaseColor",Color.blue);
}
```

## 2. Grab Interactable

Next we can try a **Grab interactable** to allow us to pick up objects in our scene.

[<img src="https://uwetom.github.io/media-production-worksheets/wk17-vr-introduction/images/xr_simulator_video.jpg">](https://uwe.cloud.panopto.eu/Panopto/Pages/Viewer.aspx?id=c037b363-6479-49f1-89ce-b30001106ff9)

We can also add grab an interactable to our own objects

[<img src="https://uwetom.github.io/media-production-worksheets/wk18-more-vr/images/pizza_video.jpg">](https://uwe.cloud.panopto.eu/Panopto/Pages/Viewer.aspx?id=b85003b4-643d-40e1-abdc-b30001142c77)

[Kenney.nl objects](https://uwetom.github.io/media-production-worksheets/wk18-more-vr/assets/kenney_objects.unitypackage)

[sounds](https://uwetom.github.io/media-production-worksheets/wk18-more-vr/assets/sounds.zip)



## 3. User Interface

### Create a UI

A VR User interface (UI) uses the same components as we use in other Unity project, the main difference is that you want to use the XR canvas which is created in **World space**. 

- **Right click** in the Hierarchy and choose **XR > UI CANVAS**

![canvas](https://uwetom.github.io/media-production-worksheets/wk18-more-vr/images/ui_canvas.jpg)

- scale the canvas down to 0.02.

Notice that the render mode is **World Space**.

![canvas sale](https://uwetom.github.io/media-production-worksheets/wk18-more-vr/images/canvas_scale.jpg)

You can now add standard ui elements to the canvas

- Add a **UI Panel, Textbox and Button** to the canvas (HINT: Right click one the canvas in the hierarchy, and choose **UI > panel** etc...  )

- Change the width, height and font size in the **Inspector** to size the appropriately.

![canvas sale](https://uwetom.github.io/media-production-worksheets/wk18-more-vr/images/ui_panel.jpg)

- change the colours of the buttons so the user gets feedback when they interact with them.

![canvas sale](https://uwetom.github.io/media-production-worksheets/wk18-more-vr/images/button_colors.jpg)

### UI events

Now that we have a UI we want the button to do something when it is clicked.

// make script to show debug message when clicked

// make prefab and instantiate it when button clicked.


- build you scene

## Challenge

- Create prefabs from other objects and make random items appear when you press the button.

- hint array




 
### Documentation

[XR Interaction 2.5 documentation](https://docs.unity3d.com/Packages/com.unity.xr.interaction.toolkit@2.5/manual/samples-starter-assets.html)
