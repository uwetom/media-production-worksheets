[Back](https://uwetom.github.io/media-production-worksheets)

# Using external data in unity pt 2

![enter image description here](https://raw.githubusercontent.com/uwetom/media-production-worksheets/refs/heads/master/wk-unity-external-data-2/images/asteroids.gif)
*(AR scene of Near Earth Objects designated as hazardous by NASA, generated from a NASA dataset)*

## Overview
In this next tutorial we are going to use  data to add objects and information to an AR scene (preview above)..

This follows on directly from **Using external data in unity pt 1** So you should have completed pt 1 and have your your Unity project open and your **GetData** C# script open in Visual Studio to begin.

It is possible to use incoming data to alter nearly every aspect of  your project by using the data to change, add and remove  Game Objects in your scene. (This could include objects in your scene, or atmosphere (fog), skybox, materials, textures, physics properties and so on). 

In this example we are going to use the data instantiate (create) objects in our scene.

We will use the NASA JSON data to add a rock / asteroid into our scene to represents every hazardous near earth object in the NASA data.

## Set up: install asteroids package

I've prepared the rock / asteroids that we are going to use, creating prefabs with a simple rotation animation. Download [the package here](https://github.com/uwetom/media-production-worksheets/raw/refs/heads/master/wk-unity-external-data-2/Asteroids.unitypackage) 

Drag it into your Assets folder to install it.

![Inspector screenshot](https://raw.githubusercontent.com/uwetom/media-production-worksheets/refs/heads/master/wk-unity-external-data-2/images/install-rocks.png)

## Set up: script and prefabs
In this next video we are going to set up the script and prefabs ready to deploy in the AR scene.

[<img src="https://raw.githubusercontent.com/uwetom/media-production-worksheets/refs/heads/master/wk-unity-external-data-2/images/edit-prefab-video.png">](https://uwe.cloud.panopto.eu/Panopto/Pages/Viewer.aspx?id=18c829c7-389e-48d9-8617-b28701019986)

(Note: In the video above  I referred to the Array that we created as a 'List'. It is in fact an Array. In Unity Lists are quite different).

## Use data to add asteroids / rocks to the AR scene
Now we are ready to add asteroids / rocks to the AR scene based on the NASA data, and using the ```instantiate``` function.

[<img src="https://raw.githubusercontent.com/uwetom/media-production-worksheets/refs/heads/master/wk-unity-external-data-2/images/add-rocks.png">](https://uwe.cloud.panopto.eu/Panopto/Pages/Viewer.aspx?id=de75c10d-37ff-4556-955e-b28900b87d0c)


### Key technique
We have used an Array in our ```GetData``` script to hold all the Rock prefabs.

We initialised the Array in the code as a public Array of Game Objects that we named rockInstances:   
```public GameObject[] rockInstances;```   

Then we assigned data to the Array in the inspector. Adding the rock prefabs to it.   

![inspector screenshot](https://raw.githubusercontent.com/uwetom/media-production-worksheets/refs/heads/master/wk-unity-external-data-2/images/assign-array.png)

We accessed data from the array using the index of each element (0, 1, 2).   
```rockInstances[0] // returns Rock_01```

The key thing about Arrays in Unity is that you cannot add or remove elements to them once they have been initialised.

Like all variables in Unity you have to declare the type of data the Array will hold (in our case: Game Objects).

We could also have used a List in Unity which works slightly differently to an Array (you can add or remove elements to a List).

Learn more about Arrays and Lists here
https://www.youtube.com/watch?v=Q16KIxtomeo

## Use data to add text to the asteroids / rocks in the AR scene


## Build the project to an Android device
<!--stackedit_data:
eyJoaXN0b3J5IjpbODg2NDQzNDYyLC00NTExNTE4NzgsODg2Mj
Y4ODM4LDY4MDU3MzAsLTgwNjIzNjY0MCwtMTg2MTczMjQxNCwt
NDcwNzg5MjgsLTQ4ODQyNTE5NCwtMjI3MTg4NjYzLC0xMjIwNz
c0MzU3LDc0Mjg2Nzk1Myw5Nzg5NDMzMjAsNzI1MjgyNDA0LC04
OTQzNDI3NTQsLTMxMDM2ODI0OCwtODI2MzU3MDExLC04NDM5OT
U5ODJdfQ==
-->