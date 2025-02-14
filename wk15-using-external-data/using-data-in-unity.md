[Back](https://uwetom.github.io/media-production-worksheets)

# Using external data in unity 

<iframe width="560" height="315" src="https://www.youtube.com/embed/VZ1ThbYgEcQ?si=YO7O_Asb9WVCA67t" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

*(AR scene of Near Earth Objects designated as hazardous by NASA, generated from a NASA dataset)*

## Overview
In this session we are going to learn how to import live, external data (in JSON format) in Unity and extract  some data from the imported JSON.  

Then in the next worksheet we will use the data to add objects and information to an AR scene (preview above)..

Most of this worksheet will involve working with a C# script and the Unity3D console. We are going to use the NASA data for Near Earth Objects that we looked at previously https://api.nasa.gov/.

We are also going to use an external C# code library for Unity called [SimpleJSON](https://github.com/Bunny83/SimpleJSON) to help us.


## Setup: Fork and clone the AR template
To get started you should make a new Unity project by forking and cloning Tom's [AR template](https://github.com/uwetom/AR-Template) on GitHub.

If you aren't sure how to Fork and Clone a GitHub repository watch this video: (otherwise skip ahead)

<iframe src="https://uwe.cloud.panopto.eu/Panopto/Pages/Embed.aspx?id=7bf90f82-466e-4255-a7c2-b27b0117b82a&autoplay=false&offerviewer=true&showtitle=true&showbrand=true&captions=false&interactivity=all" height="405" width="720" style="border: 1px solid #464646;" allowfullscreen allow="autoplay" aria-label="Panopto Embedded Video Player" aria-description="MP fork and clone 5 February 2025 at 16:54:57" ></iframe>

Open the AR-Template project in Unity and add a new folder in 'Assets' called 'Scripts'.

Next download a zip file of the code library for Unity called [SimpleJSON](https://github.com/Bunny83/SimpleJSON) and unzip it.

![download a GitHub repo as zip file](https://uwetom.github.io/media-production-worksheets/wk15-using-external-data/images/download-repo.png)

Add / drag the file called SimpleJSON.cs to your Scripts folder. Do not add any of the other files.

## Set up the virtual testing environment for AR

Next set up the virtual testing environment for AR... Check it works.

<iframe src="https://uwe.cloud.panopto.eu/Panopto/Pages/Embed.aspx?id=86f965ba-81fe-474c-ad22-b2830133d12d&autoplay=false&offerviewer=true&showtitle=true&showbrand=true&captions=false&interactivity=all" height="405" width="720" style="border: 1px solid #464646;" allowfullscreen allow="autoplay" aria-label="Panopto Embedded Video Player" aria-description="MP-livedata-1 Thursday 13 February 2025 at 18:37:48" ></iframe>

So we now have a basic AR scene working in the virtual testing environment.

In the next steps we will add some external data.

## Get a link to some external data

Before you start this next section you should have followed the previous tutorial and made an account on https://api.nasa.gov/ and used your API key to get some external data about Near Earth Objects.

The URL link you generated should allow you to preview the HTTP request in your browser and see a JSON file that looks like [this]( https://raw.githubusercontent.com/uwetom/media-production-worksheets/master/wk15-using-external-data/images/neows-3.png). It has a list of ```near_earth_objects``` that we will be using.

Save the URL link in a text file (if you haven't already).

If this isn't working you will need to revisit the previous tutorial.

## Use C# to get external data into Unity
In this next video we will use Unity networking to access the data in the NASA JSON file, live from the NASA website. Unity will access the link and download the data into your Unity project. We will look at the raw downloaded data in the console.

<iframe src="https://uwe.cloud.panopto.eu/Panopto/Pages/Embed.aspx?id=3f680212-dab6-4da2-acc3-b28400e8c6db&autoplay=false&offerviewer=true&showtitle=true&showbrand=true&captions=false&interactivity=all" height="405" width="720" style="border: 1px solid #464646;" allowfullscreen allow="autoplay" aria-label="Panopto Embedded Video Player" aria-description="MP-data-2 Get JSON data" ></iframe>

In this video we used a Coroutine / IENumerator. 
Coroutines provide an excellent way of easily managing things that need to happen after a delay or over the course of time. You can learn more about them here:
https://learn.unity.com/tutorial/coroutines# 

Code (but please type not copy and paste!):
```C#
using System.Collections.Generic;
using UnityEngine;
using SimpleJSON;
using UnityEngine.Networking;

public class GetData : MonoBehaviour
{
    public string DataURL;

    // Start is called before the first frame update
    void Start()
    {
        StartCoroutine(getData());
    }

    IEnumerator getData()
    {
        using (UnityWebRequest request = UnityWebRequest.Get(DataURL))
        {
            yield return request.SendWebRequest();

            if (request.result == UnityWebRequest.Result.ConnectionError)
            {
                Debug.LogError(request.error);
            }
            else
            {
                string json = request.downloadHandler.text;
                Debug.Log(json);
            }

        }
    }
}
```
The Unity project that you now have will allow you to download data from any data repository or API that is in JSON format. 
It will also work in an AR / VR or normal Unity project. Very useful!


## Use C# to navigate and extract data from JSON

In the next video I am going to add to the ``GetData`` C# script to extract specific information from the JSON data.

I want to get information about Near Earth Objects (asteroids) that NASA has designated as hazardous, listing the asteroid names and their size in km.
The NASA json data contains all this information.  Each [near_earth_object](https://raw.githubusercontent.com/uwetom/media-production-worksheets/master/wk15-using-external-data/images/neows-3.png) (asteroid) has a name and  size.  Each asteroid is also classified as ```"is_potentially_hazardous_asteroid": false,``` or ```true```. We will use this to filter the data.

**Note:** Before you follow this video it might be helpful to review the section of the last worksheet called **How to get values from JSON**. We will be using keys to access the values in data.

<iframe src="https://uwe.cloud.panopto.eu/Panopto/Pages/Embed.aspx?id=d9464bce-ae0c-4ecc-bcb6-b284011ed94b&autoplay=false&offerviewer=true&showtitle=true&showbrand=true&captions=false&interactivity=all" height="405" width="720" style="border: 1px solid #464646;" allowfullscreen allow="autoplay" aria-label="Panopto Embedded Video Player" aria-description="MP-data-3b extract data" ></iframe>

This code should give you a good starting point and some methods for extracting data from any JSON file. The key / value principles and the nested key / value structure are used in all datasets.

The final code is (please type not copy and paste!):

```C#
using System.Collections;
using System.Collections.Generic;
using UnityEngine;
using SimpleJSON;
using UnityEngine.Networking;

public class GetData : MonoBehaviour
{
    public string DataURL;

    // Start is called before the first frame update
    void Start()
    {
        StartCoroutine(getData());
    }

    IEnumerator getData()
    {
        using (UnityWebRequest request = UnityWebRequest.Get(DataURL))
        {
            yield return request.SendWebRequest();

            if (request.result == UnityWebRequest.Result.ConnectionError)
            {
                Debug.LogError(request.error);
            }
            else
            {
                string json = request.downloadHandler.text;
                Debug.Log(json);
                ReadJSON(json);
            }
        }
    }

    void ReadJSON(string jsonString)
    {
        JSONNode node = JSON.Parse(jsonString);
        JSONObject obj = node.AsObject;
        Debug.Log(obj["near_earth_objects"].Count);
        int numOfAsteroids = obj["near_earth_objects"].Count;

        for (int i = 0; i < numOfAsteroids; i++)
        {
            string isHazardous = obj["near_earth_objects"][i]["is_potentially_hazardous_asteroid"].Value;

            if (isHazardous == "True")
            {
                Debug.Log(obj["near_earth_objects"][i]["name"].Value);
                Debug.Log(obj["near_earth_objects"][i]["estimated_diameter"]["kilometers"]["estimated_diameter_min"].Value);
                Debug.Log(obj["near_earth_objects"][i]["estimated_diameter"]["kilometers"]["estimated_diameter_max"].Value);
            }
        }
    }
}
```
<!--stackedit_data:
eyJoaXN0b3J5IjpbMjAyNzA2NzY0NiwtNjU2Nzc0NDY4LDIzND
k3NjY2MSwxMzQ4MDM0MzA0LC05MDgyNzk5NDYsLTE1NDMyNTA5
MzcsLTY3MjgzNjAsMTAwNTY2MDc0MiwxNzcyMjE1MjE0LC00OD
MzODc5LC05MDgzNDgxMjYsMzM2NjQ0MTQ4LC0xNTU2NDQwOTg4
LDUxNTU2MzY3MywtNDEyNzU1NDk1LC0xMzExNzU3MTY2LC04ND
E1MDIwMzMsLTExMjA1NDQ5NTEsMTMyNTkwNTE2OCwyMTAyOTUz
MjI2XX0=
-->