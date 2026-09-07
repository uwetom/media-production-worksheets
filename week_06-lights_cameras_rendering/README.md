# Exporting a Sequence

This worksheet will cover how to setup your camera and render out an image sequence of your animation.

## Lights

If you do not add lights to your scene your render will be black.

Add lights through the **Arnold > Lights** top menu

![arnold lights menu in Maya](images/lights.jpg)

Or by creating a standard spot, direction or point light through the **create > Lights** top menu

![Create light menu](images/create_light.jpg)

Note that the ambient light does not work in the Arnold renderer.

To see an aproxomation of the lights in your viewport, turn them on 

![show lights in viewport button](images/show_lights.jpg)

Otherwise, you will only see the effect when rendering.

### Lights troubleshooting

If you lights do not show up in your render, check the following

- Are directional, spot or area lights are pointed in the right direction
- Are your lights bright enough, if you are not sure, type a really big number in the attribute editor ( 100000) to see if you get anything.

![Arnold light intensity](images/intensity.jpg)

## Camera

Although you can render the perspective camera, it can be very inconvinient to use the same camera to edit and render your scene, the bellow video shows you how to make a new camera:

[<img alt="video showing how to setup a render camera in Maya" src="images/video-render-camera.jpg">](https://uwe.cloud.panopto.eu/Panopto/Pages/Viewer.aspx?id=63b7c854-7183-425f-8378-b49c00ee3ed4)

When exporting an animation from Maya, rather than rending straight to video you need to render out a sequence of images, one for each frame of your animation.

## Render settings

Now we have setup our camera we can render it out, but first we need to decide on the format and size of our rendered images.

[<img alt="video showing how to change the render settings in Maya" src="images/video-render-settings.jpg">](https://uwe.cloud.panopto.eu/Panopto/Pages/Viewer.aspx?id=7c7cb552-0fc0-49a1-9aa3-b49c00ef3d73)

## Render a sequence

We can now render out our sequence.

[<img alt="video showing how to render out a sequence in Maya" src="images/render_sequence.jpg">](https://uwe.cloud.panopto.eu/Panopto/Pages/Viewer.aspx?id=1f0f82a9-14d8-447f-b3aa-b49c00f08e0d)

You should now have a folder full of rendered images.

You can import them into a video editor like premier to the export them as a video file.


## Other resources - fog

If you want to add some atmosphere to your scene, you could add fog.

Maya has a few ways to add fog, but be aware that it will increase render times.

[Maya fog](https://www.youtube.com/watch?v=q2Bq4lRkvAs)

