# VR UI, 2D interactions and lighting

In this worksheet we will export UI and lighting in VR

## Open a Project

- Open last weeks Unity project or create a new VR project.

## 1. User Interface

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

- Change the colours of the buttons so the user gets feedback when they interact with them.

![canvas sale](https://uwetom.github.io/media-production-worksheets/wk18-more-vr/images/button_colors.jpg)

### UI events

Now that we have a UI we want the button to do something when it is clicked.

- Make a new Script and call it **UiInteractions**
- Create a new public function on the script we can call from the button
- Make the function log a Debug message so we can test it works.

```c#
using UnityEngine;

public class UIiInteraction : MonoBehaviour
{
    public void buttonPressed() {
        Debug.Log("button Pressed !");    
    }
    
}
```

- Now drag the script onto the button
- Link the script up to the buttons On Click event

![canvas sale](https://uwetom.github.io/media-production-worksheets/wk18-more-vr/images/button_script.jpg)

- Test the scene to see if you get a console message when press the trigger when hovering over the button.

## 2. Lights

- Add a new **Point Light** to the scene

![canvas sale](https://uwetom.github.io/media-production-worksheets/wk18-more-vr/images/point_light.jpg)

 You should notice that it does not seem to cast any light. If you disable the **directional light** the scene will be dark.
 
 To enable the light we need to change some settings.
 
 [<img src="https://uwetom.github.io/media-production-worksheets/wk18-more-vr/images/additional_lights_video.jpg">](https://uwe.cloud.panopto.eu/Panopto/Pages/Viewer.aspx?id=7baeea87-0e5a-4c29-8307-b31400fbc72d)
 

 ## Challenge
 
 - Turn the light on and off when you click the button on the ui.
 
Solution:

 [<img src="https://uwetom.github.io/media-production-worksheets/wk18-more-vr/images/turn_light_on_video.jpg">](https://uwe.cloud.panopto.eu/Panopto/Pages/Viewer.aspx?id=04711d78-bd53-45e4-9c69-b314010c9669)
 
 













