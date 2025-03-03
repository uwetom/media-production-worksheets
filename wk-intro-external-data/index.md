[Back](https://uwetom.github.io/media-production-worksheets)

# Introduction to using external data (what are APIs)

## Accessing external data 
Using external data can be a powerful addition to your unity 3D environment, particularly if you want to simulate a physical environment in real time.

Or if you want to use unity to visualise some sort of data.

For example it's quite possible to completely change your unity scene based on say environmental or climate data.

In this session we're going to look at how to access external data from unity, where you might find it, and then how you might deploy it and use it in unity.  


## Rest APIs
Most external data is held in databases and can be accessed via a simple web link (HTTP request) using ```https://...``` these custom links are called 'designated entry points'. 

Sometimes you will need an account and passkey to access data other times the data will be open and unsecured.

Usually documentation that accompanies the database and repository of data will explain how you can access it.

This often involves making a HTTP request and the data is returned from that request in a JSON format.

This process is known as an application programming interface or API.

Let's have a look at how it works and access some data from our web browser and then we can try and work out how to do this in unity.

## Install a JSON formatter browser extension / addon Chrome browser extension
So that we can easily read the returned data Install one of these browser extensions.

The data that will be returned to us will be formatted as javaScript Object Notation. The browser extension will make it much easier to read.
Chrome extension:
https://chrome.google.com/webstore/detail/json-formatter/bcjindcccaagfpapjjmafapmmgkkhgoa?hl=en 

Firefox addon:
https://addons.mozilla.org/en-GB/firefox/addon/basic-json-formatter/ 

Use Safari or Edge? We feel for you…

## Getting some data
Let's start getting some data with a joke API to begin with. This API returns a random / different joke on every request. (The jokes aren't very good).

Put this URl in your browser
[https://v2.jokeapi.dev/joke/Any?safe-mode](https://v2.jokeapi.dev/joke/Any?safe-mode)
If you have successfully installed the Chrome or Firefox extension you should see a joke similar to the following.

  ![JSON data](https://raw.githubusercontent.com/uwetom/media-production-worksheets/master/wk-intro-external-data/images/joke-api-2.png)

### Code challenge - get some data
Now you have a go using weather data using open meteo. 
[https://open-meteo.com/](https://open-meteo.com/)
Look at the documentation and try and work out what HTTP browser request you need to make in order to return some live weather data for our current location…

(Hint: use maps to get our Latitude and Longitude position)

The returned meteo JSON data should look like:

![JSON file](https://raw.githubusercontent.com/uwetom/media-production-worksheets/master/wk-intro-external-data/images/meteo-api-2.png)

[Need the solution?](https://uwetom.github.io/media-production-worksheets/wk-intro-external-data/api-solutions.html)


## How JSON works
JSON files are structured using a ```key : value``` system. 
Multiple pairs are separated by commas.
A simple example JSON file might look like this:
```Javascript
{ "latitude": 52.52, "longtitude": 13.419, "location": "Bristol"}
```
Here ```"latitude"``` and ```"longtitude"``` and ```"location"``` are the keys
While ```52.52``` ```13.419``` ``"Bristol"`` are the values.

The format is 
```Javascript 
{ "key": "value"}
```
Multiple ```key : value``` pairs are separated by commas. 

Often JSON is written with line breaks so the same JSON file could be written like this:
```Javascript
{ 
	"latitude": 52.52, 
	"longtitude": 13.419, 
	"location": "Bristol"
}
```
It is also common for data to be nested like this:
```Javascript
{ 
	"latitude": 52.52, 
	"longtitude": 13.419, 
	"location": {
		"city": "Bristol",
		"street" : "Coldharbour Lane"
	}
}
```
## How to get values from JSON
To access the data in most programming languages you 'parse' the JSON file and turn into in an Object, then call each key to access the value
Using the JSON above:
```Javascript
MyJsonFile["latitude"]; // returns 52.52
MyJsonFile["longtitude"]; // returns 13.419
```
Access nested data like this:
```Javascript
MyJsonFile["location"]["city"]; // returns "Bristol"
MyJsonFile["location"]["street"]; // returns "Coldharbour Lane"
```
### Code challenge - try accessing some data
Using the meteo JSON example above write out (on paper) the syntax to access the the current temperature and rain?

## Data repositories / libraries
You can find a list of unsecured data with API access here

[https://mixedanalytics.com/blog/list-actually-free-open-no-auth-needed-apis/](https://mixedanalytics.com/blog/list-actually-free-open-no-auth-needed-apis/)

[https://free-apis.github.io/#/browse](https://free-apis.github.io/#/browse)


## API Keys
For many data repositories it is quite common to need to make an account and log in. You are then given a passkey (an API Key) which you add to the HTTP url when you make the request.

#### Near Earth Objects example:
This Nasa data repository about Near Earth Objects (NEO / asteroids that will pass close to earth) https://api.nasa.gov/ needs a log in and API Key. 

Scroll down on the link above to find the documentation about Asteroids-NeoWs (Near Earth Object Web Service).
![JSON file](https://raw.githubusercontent.com/uwetom/media-production-worksheets/refs/heads/master/wk-intro-external-data/images/neows-2.png)
The format for the HTTP web request to retrieve all Near Earth Objects is:

[`https://api.nasa.gov/neo/rest/v1/neo/browse?api_key=DEMO_KEY`](https://api.nasa.gov/neo/rest/v1/neo/browse?api_key=DEMO_KEY)

Go to https://api.nasa.gov/ Make a free account and replace ```DEMO_KEY``` with your api key on the link above. 

Open Chrome browser and run the link. You should see a list of  ```near_earth_objects```:

**! Important: Save the link in a text file.**

![JSON file](https://raw.githubusercontent.com/uwetom/media-production-worksheets/refs/heads/master/wk-intro-external-data/images/neows-4.png)

How many are 
```"is_potentially_hazardous_asteroid": true,```

Now let's get this data into Unity and learn how to use it....
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTEwMTM3MjA2NjgsMzE1Nzc1ODMsMTUzMT
gwOTg5MywxMzE4NDczMzk0LDc4Mzc0ODk0NiwtNTkyNDkyMTMy
LDM2NjM3NDUxMF19
-->