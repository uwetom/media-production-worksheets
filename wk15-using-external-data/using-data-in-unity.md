[Back](https://uwetom.github.io/media-production-worksheets)

# Using external data in unity 

<iframe width="560" height="315" src="https://www.youtube.com/embed/VZ1ThbYgEcQ?si=YO7O_Asb9WVCA67t" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
(Near Earth Objects designated as hazardous by NASA)

In this session we are going to learn how to import live, external data (in JSON format) in Unity and extract  some data from the imported JSON.  

Then we will use the data to add objects and information into an AR scene.

Most of this will involve working with C# scripts and the Unity3D console.

We are also going to use an external C# code library for Unity called [SimpleJSON](https://github.com/Bunny83/SimpleJSON) to help us.

Eventually we will include this in an AR app, so to get started you should make a new Unity project by forking and cloning Tom's [AR template](https://github.com/uwetom/AR-Template) on GitHub.

If you aren't sure how to Fork and Clone a GitHub repository watch this video: (otherwise skip ahead)

<iframe src="https://uwe.cloud.panopto.eu/Panopto/Pages/Embed.aspx?id=7bf90f82-466e-4255-a7c2-b27b0117b82a&autoplay=false&offerviewer=true&showtitle=true&showbrand=true&captions=false&interactivity=all" height="405" width="720" style="border: 1px solid #464646;" allowfullscreen allow="autoplay" aria-label="Panopto Embedded Video Player" aria-description="MP fork and clone 5 February 2025 at 16:54:57" ></iframe>

Open the AR-Template project in Unity and add a new folder in 'Assets' called 'Scripts'.

Download the code library for Unity called [SimpleJSON](https://github.com/Bunny83/SimpleJSON) and unzip it.

![download a GitHub repo as zip file](https://uwetom.github.io/media-production-worksheets/wk15-using-external-data/images/download-repo.png)

Add the file called SimpleJSON.cs to your Scripts folder. Do not add any of the other files.

## Set up the virtual testing environment for AR

Next set up the virtual testing environment for AR... Check it works.

<iframe src="https://uwe.cloud.panopto.eu/Panopto/Pages/Embed.aspx?id=86f965ba-81fe-474c-ad22-b2830133d12d&autoplay=false&offerviewer=true&showtitle=true&showbrand=true&captions=false&interactivity=all" height="405" width="720" style="border: 1px solid #464646;" allowfullscreen allow="autoplay" aria-label="Panopto Embedded Video Player" aria-description="MP-livedata-1 Thursday 13 February 2025 at 18:37:48" ></iframe>




<!--stackedit_data:
eyJoaXN0b3J5IjpbMTMyNTkwNTE2OCwyMTAyOTUzMjI2LDEyOD
gzMjQzMDQsLTE5MDQ4ODk1MTQsLTEyOTg0MTM5NjIsOTkxOTI3
NywtNzMwNzg4NjY1LC0xOTM2NzY4NzgsLTMxNjMxNTgwMSwxNT
AzNTc2MzI2LDE2MjE4NDI2NjcsLTE0ODU5NDIyMTRdfQ==
-->