[Back](https://uwetom.github.io/media-production-worksheets)

# Using external data in unity 

<iframe width="560" height="315" src="https://www.youtube.com/embed/VZ1ThbYgEcQ?si=YO7O_Asb9WVCA67t" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
*(AR scene of Near Earth Objects designated as hazardous by NASA, generated from a NASA dataset)*

## Overview
In this session we are going to learn how to import live, external data (in JSON format) in Unity and extract  some data from the imported JSON.  

Then we will use the data to add objects and information into an AR scene.

Most of this will involve working with C# scripts and the Unity3D console. We are going to use the NASA data for Near Earth Objects that we looked at previously https://api.nasa.gov/.

We are also going to use an external C# code library for Unity called [SimpleJSON](https://github.com/Bunny83/SimpleJSON) to help us.

Eventually we will include this in an AR app (preview above). 

## Setup: Fork and clone the AR template
To get started you should make a new Unity project by forking and cloning Tom's [AR template](https://github.com/uwetom/AR-Template) on GitHub.

If you aren't sure how to Fork and Clone a GitHub repository watch this video: (otherwise skip ahead)

<iframe src="https://uwe.cloud.panopto.eu/Panopto/Pages/Embed.aspx?id=7bf90f82-466e-4255-a7c2-b27b0117b82a&autoplay=false&offerviewer=true&showtitle=true&showbrand=true&captions=false&interactivity=all" height="405" width="720" style="border: 1px solid #464646;" allowfullscreen allow="autoplay" aria-label="Panopto Embedded Video Player" aria-description="MP fork and clone 5 February 2025 at 16:54:57" ></iframe>

Open the AR-Template project in Unity and add a new folder in 'Assets' called 'Scripts'.

Download a zip file of the code library for Unity called [SimpleJSON](https://github.com/Bunny83/SimpleJSON) and unzip it.

![download a GitHub repo as zip file](https://uwetom.github.io/media-production-worksheets/wk15-using-external-data/images/download-repo.png)

Add / drag the file called SimpleJSON.cs to your Scripts folder. Do not add any of the other files.

## Set up the virtual testing environment for AR

Next set up the virtual testing environment for AR... Check it works.

<iframe src="https://uwe.cloud.panopto.eu/Panopto/Pages/Embed.aspx?id=86f965ba-81fe-474c-ad22-b2830133d12d&autoplay=false&offerviewer=true&showtitle=true&showbrand=true&captions=false&interactivity=all" height="405" width="720" style="border: 1px solid #464646;" allowfullscreen allow="autoplay" aria-label="Panopto Embedded Video Player" aria-description="MP-livedata-1 Thursday 13 February 2025 at 18:37:48" ></iframe>

So we now have a basic AR scene working in the virtual testing environment.

In the next steps we will add some external data.

## Get a link to some external data (JSON)

Before you start this section you should have followed the previous tutorial and made an account on https://api.nasa.gov/ and used your API key to get some external data about Near Earth Objects.

You should be able to preview the HTTP request from the URL link you generated  in your browser and see a JSON file that looks like [this]( https://raw.githubusercontent.com/uwetom/media-production-worksheets/master/wk15-using-external-data/images/neows-3.png). It has a list of ```near_earth_objects``` that we will be using.

Save the https://... link in a text file (if you haven't already).

If this isn't working you will need to revisit the previous tutorial.

## Use C# to get external data into Unity
In the next video we will use Unity networking to access the data in the NASA JSON file, live from the NASA dataset. Unity will access the link and download the data into your project.



Coroutines provide an excellent way of easily managing things that need to happen after a delay or over the course of time. You can learn more about them here:
https://learn.unity.com/tutorial/coroutines# 






<!--stackedit_data:
eyJoaXN0b3J5IjpbLTEyNTYzNDY3MjQsLTkwODM0ODEyNiwzMz
Y2NDQxNDgsLTE1NTY0NDA5ODgsNTE1NTYzNjczLC00MTI3NTU0
OTUsLTEzMTE3NTcxNjYsLTg0MTUwMjAzMywtMTEyMDU0NDk1MS
wxMzI1OTA1MTY4LDIxMDI5NTMyMjYsMTI4ODMyNDMwNCwtMTkw
NDg4OTUxNCwtMTI5ODQxMzk2Miw5OTE5Mjc3LC03MzA3ODg2Nj
UsLTE5MzY3Njg3OCwtMzE2MzE1ODAxLDE1MDM1NzYzMjYsMTYy
MTg0MjY2N119
-->