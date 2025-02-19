[Back](https://uwetom.github.io/media-production-worksheets)

# Using external data in unity pt 2

![enter image description here](https://raw.githubusercontent.com/uwetom/media-production-worksheets/refs/heads/master/wk-unity-external-data-2/images/asteroids.gif)
*(AR scene of Near Earth Objects designated as hazardous by NASA, generated from a NASA dataset)*

## Overview
In this next tutorial we are going to use  data to add objects and information to an AR scene (preview above)..

This follows on directly from **Using external data in unity pt 1** So you should have completed pt 1 and have your your Unity project open and your **GetData** C# script open in Visual Studio to begin.

It is possible to use incoming data to alter nearly every aspect of your your scene by using the data to interact with the components in your Game Objects (objects, atmosphere, materials, texture, physics and so on). 

In this example we are going to use the data instantiate (create) objects in our scene.

## Set up: install asteroids package

I've prepared the rock / asteroids that we are going to use, creating prefabs with a simple rotation animation. Download [the package here](https://github.com/uwetom/media-production-worksheets/raw/refs/heads/master/wk-unity-external-data-2/Asteroids.unitypackage) 

Drag it into your Assets folder to install it.

![enter image description here](https://raw.githubusercontent.com/uwetom/media-production-worksheets/refs/heads/master/wk-unity-external-data-2/images/install-rocks.png)
 
In this next video we are going to set up the script and prefabs ready to deploy in the AR scene.

[<img src="https://raw.githubusercontent.com/uwetom/media-production-worksheets/refs/heads/master/wk-unity-external-data-2/images/edit-prefab-video.png">](https://uwe.cloud.panopto.eu/Panopto/Pages/Viewer.aspx?id=18c829c7-389e-48d9-8617-b28701019986)


### Key technique
We have used an Array in our code to hold all the Rock prefabs.

We initialised the Array in the code ```public GameObject[] rockInstances;``` as a public Array of Game Objects that we are calling rockInstances.

Then we assigned data to the Array in the inspector

<!--stackedit_data:
eyJoaXN0b3J5IjpbLTc4NTYyMzkxNywtMjI3MTg4NjYzLC0xMj
IwNzc0MzU3LDc0Mjg2Nzk1Myw5Nzg5NDMzMjAsNzI1MjgyNDA0
LC04OTQzNDI3NTQsLTMxMDM2ODI0OCwtODI2MzU3MDExLC04ND
M5OTU5ODJdfQ==
-->