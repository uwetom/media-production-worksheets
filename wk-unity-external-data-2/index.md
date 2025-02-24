[Back](https://uwetom.github.io/media-production-worksheets)

# Using external data in unity pt 2

![enter image description here](https://raw.githubusercontent.com/uwetom/media-production-worksheets/refs/heads/master/wk-unity-external-data-2/images/asteroids.gif)
*(AR scene of Near Earth Objects designated as hazardous by NASA, generated from a NASA dataset)*

## Overview
In this next tutorial we are going to use  data to add objects and information to an AR scene (preview above)..

This follows on directly from **Using external data in unity pt 1** So you should have completed pt 1 and have your Unity project open and your **GetData** C# script open in Visual Studio to begin.

It is possible to use incoming data to alter nearly every aspect of  your project by using the data to change, add and remove  Game Objects in your scene. (This could include objects in your scene, or atmosphere (fog), skybox, materials, textures, physics properties and so on). 

In this example we are going to use the data instantiate (create) objects in our scene. We will use the NASA JSON data to add a rock / asteroid into our scene for every hazardous near earth object in the dataset.

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

### Code

Please type not copy and paste
```C#
using System.Collections;
using System.Collections.Generic;
using UnityEngine;
using SimpleJSON;
using UnityEngine.Networking;

public class GetData : MonoBehaviour
{
    public string DataURL;
    public GameObject rockText;
    public GameObject[] rockInstances;
    private int counter;

    // Start is called before the first frame update
    void Start()
    {
        counter = 0;
        StartCoroutine(getData());
    }

    // download the data 
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

    // this function reads the Json data
    // turns into an 'object' that can be parsed
    // and extracts information from it using different keys
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
                //Debug.Log(obj["near_earth_objects"][i]["name"].Value);
                //Debug.Log(obj["near_earth_objects"][i]["estimated_diameter"]["kilometers"]["estimated_diameter_min"].Value);
                //Debug.Log(obj["near_earth_objects"][i]["estimated_diameter"]["kilometers"]["estimated_diameter_max"].Value);

                // Rocks
                // Instantiate(Game object, xyz position, rotation)
                Vector3 position = new Vector3(Random.Range(-10.0f, 5.0f), Random.Range(0f, 10.0f), Random.Range(2.0f, 10.0f));
                if (counter >= rockInstances.Length)
                {
                    counter = 0;
                }
                Instantiate(rockInstances[counter], position, Random.rotation);
                counter++;
            }
        }

    }
    
}
```


### Key technique
We have used an Array in our `
``GetData``` script to hold all the Rock prefabs.

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
eyJoaXN0b3J5IjpbLTU1ODc0NTYyMywtMTAxNDgxMDQ1LDQ2MT
kyNDM2OCw3ODIwNjQ0MDcsLTQ1MTE1MTg3OCw4ODYyNjg4Mzgs
NjgwNTczMCwtODA2MjM2NjQwLC0xODYxNzMyNDE0LC00NzA3OD
kyOCwtNDg4NDI1MTk0LC0yMjcxODg2NjMsLTEyMjA3NzQzNTcs
NzQyODY3OTUzLDk3ODk0MzMyMCw3MjUyODI0MDQsLTg5NDM0Mj
c1NCwtMzEwMzY4MjQ4LC04MjYzNTcwMTEsLTg0Mzk5NTk4Ml19

-->