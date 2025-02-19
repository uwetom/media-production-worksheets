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

![Inspector screenshot](https://raw.githubusercontent.com/uwetom/media-production-worksheets/refs/heads/master/wk-unity-external-data-2/images/install-rocks.png)
 
In this next video we are going to set up the script and prefabs ready to deploy in the AR scene.

[<img src="https://raw.githubusercontent.com/uwetom/media-production-worksheets/refs/heads/master/wk-unity-external-data-2/images/edit-prefab-video.png">](https://uwe.cloud.panopto.eu/Panopto/Pages/Viewer.aspx?id=18c829c7-389e-48d9-8617-b28701019986)

(Note: In the last video I reffered to the Array that we created as a 'list'. It is in fact an Array. In Unity Lists are quite different).

Now we are ready to add asteroids / rocks to the AR scene based on the NASA data, and using the ```instantiate``` function.

[<img src="https://raw.githubusercontent.com/uwetom/media-production-worksheets/refs/heads/master/wk-unity-external-data-2/images/add-rocks.png">](https://uwe.cloud.panopto.eu/Panopto/Pages/Viewer.aspx?id=de75c10d-37ff-4556-955e-b28900b87d0c)


### Key technique
We have used an Array in our ```GetData``` script to hold all the Rock prefabs.

We initialised the Array in the code 
```public GameObject[] rockInstances;```   
as a public Array of Game Objects that we named rockInstances.

Then we assigned data to the Array in the inspector. Adding the rock prefabs to it.
![inspector screenshot](https://raw.githubusercontent.com/uwetom/media-production-worksheets/refs/heads/master/wk-unity-external-data-2/images/assign-array.png)

We accessed data from the array using the index of each element (0, 1, 2).
```rockInstances[0] // returns Rock_01```

The key thing about Arrays in Unity is that you cannot add or remove elements to them once they have been initialised.

Like all variables in Unity you have to declare the type of data the Array will hold (in our case: Game Objects).

You could also make a List in Unity which works slightly differently to an Array (you can add or remove elements to Lists).

Learn more about Arrays and Lists here
https://www.youtube.com/watch?v=Q16KIxtomeo
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTkxMDg2MTc5Niw4ODYyNjg4MzgsNjgwNT
czMCwtODA2MjM2NjQwLC0xODYxNzMyNDE0LC00NzA3ODkyOCwt
NDg4NDI1MTk0LC0yMjcxODg2NjMsLTEyMjA3NzQzNTcsNzQyOD
Y3OTUzLDk3ODk0MzMyMCw3MjUyODI0MDQsLTg5NDM0Mjc1NCwt
MzEwMzY4MjQ4LC04MjYzNTcwMTEsLTg0Mzk5NTk4Ml19
-->