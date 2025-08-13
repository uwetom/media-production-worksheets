# Using external data in unity pt 1

![enter image description here](images/asteroids.gif)
*(AR scene of Near Earth Objects designated as hazardous by NASA, generated from a NASA dataset)*

## Overview
In this session we are going to learn how to import live, external data (in JSON format) in Unity and extract  some data from the imported JSON.  

Then in the next worksheet we will use the data to add objects and information to an AR scene (preview above)..

Most of this worksheet will involve working with a C# script and the Unity3D console. We are going to use the NASA data for Near Earth Objects that we looked at previously https://api.nasa.gov/.

We are also going to use an external C# code library for Unity called [SimpleJSON](https://github.com/Bunny83/SimpleJSON) to help us.


## Setup: Fork and clone the AR template
To get started you should make a new Unity project by forking and cloning Tom's [AR template](https://github.com/uwetom/AR-Template) on GitHub.

If you aren't sure how to Fork and Clone a GitHub repository watch this video: (otherwise skip ahead)

[<img src="images/fork-clone.jpg">](https://uwe.cloud.panopto.eu/Panopto/Pages/Viewer.aspx?id=7bf90f82-466e-4255-a7c2-b27b0117b82a&start=0)



Open the AR-Template project in Unity and add a new folder in 'Assets' called 'Scripts'.

Next download a zip file of the code library for Unity called [SimpleJSON](https://github.com/Bunny83/SimpleJSON) and unzip it.

![download a GitHub repo as zip file](images/download-repo.png)

Add / drag the file called SimpleJSON.cs to your Scripts folder. Do not add any of the other files.

## Set up the virtual testing environment for AR

Next set up the virtual testing environment for AR... Check it works.

[<img src="images/data-1.jpg">](https://uwe.cloud.panopto.eu/Panopto/Pages/Viewer.aspx?id=86f965ba-81fe-474c-ad22-b2830133d12d&start=0)


So we now have a basic AR scene working in the virtual testing environment.

In the next steps we will add some external data.

## Get a link to some external data

Before you start this next section you should have followed the previous tutorial and made an account on https://api.nasa.gov/ and used your API key to get some external data about Near Earth Objects.

The URL link you generated should allow you to preview the HTTP request in your browser and see a JSON file that looks like [this]( https://raw.githubusercontent.com/uwetom/media-production-worksheets/master/wk-intro-external-data/images/neows-3.png). It has a list of ```near_earth_objects``` that we will be using.

Save the URL link in a text file (if you haven't already).

If this isn't working you will need to revisit the previous tutorial.

## Use C# to get external data into Unity
In this next video we will use Unity networking to access the data in the NASA JSON file, live from the NASA website. Unity will access the link and download the data into your Unity project. We will look at the raw downloaded data in the console.    

[<img src="images/data-2.jpg">](https://uwe.cloud.panopto.eu/Panopto/Pages/Viewer.aspx?id=3f680212-dab6-4da2-acc3-b28400e8c6db&start=0)


### Key technique
In this video we used a Coroutine / IENumerator. 
Coroutines provide an excellent way of easily managing things that need to happen after a delay or over the course of time. You can learn more about them here:
https://learn.unity.com/tutorial/coroutines# 

This is the code I used in the video ( please type not copy and paste!):
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
            }

        }
    }
}
```
The Unity project that you now have will allow you to download data from any data repository or API that is in JSON format. 
It will also work in an AR / VR or normal Unity project. Very useful!


## Use C# to navigate and extract data from JSON

In the next video I am going to add to the ``GetData`` C# script to extract specific information from the JSON data.

I want to get information about Near Earth Objects (asteroids) that NASA has designated as hazardous, then listing the asteroid names and their size in km.

Each asteroid is  classified as ```"is_potentially_hazardous_asteroid": false,``` or ```true```. 
We will use this to filter the data with an ```if()`` statement.

Each ```near_earth_object```(asteroid) also has a name and  size.

In this [Preview](https://raw.githubusercontent.com/uwetom/media-production-worksheets/master/wk-intro-external-data/images/neows-4.png)   you can see that NASA json data contains all this information.  

**Note:** Before you follow this video it might be helpful to review the section of the last worksheet called **How to get values from JSON**. We will be using keys to access the values in data.

[<img src="images/data-3.jpg">](https://uwe.cloud.panopto.eu/Panopto/Pages/Viewer.aspx?id=d9464bce-ae0c-4ecc-bcb6-b284011ed94b&start=0)

The final code is below (please type not copy and paste!):

This should give you a good starting point and a useful method for extracting data from **any** JSON file. The key / value principles and the nested key / value structure are used in many datasets.

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
eyJoaXN0b3J5IjpbLTY2NDMzNjQyOCwtMTUzODQ2MjIxMSwxNT
ExMTcwOTkzLDE0MzYyMTAwMzQsLTEzNTU5MDQ3MjYsOTcxMDY0
NzYyLDE1NjM5ODExNjIsMjA3ODQwMTEyNiwtMzgyMzU3MzQyLD
EzNzcxOTEwNzQsLTEyODMzOTE1NzhdfQ==
-->