[Back](https://uwetom.github.io/media-production-worksheets)

# Accessing external data 
Using external data can be a powerful addition to your unity 3D environment, particularly if you want to simulate a physical environment in real time.

Or if you want to use unity to visualise some sort of data.

For example it's quite possible to completely change your unity scene based on say environmental or climate data.

In this session we're going to look at how to access external data from unity, where you might find it, and then how you might deploy it and use it in unity.

## Rest APIs

Most external data is held in databases and can be accessed through designated entry points. Sometimes you will need an account and passkey to access data other times the data will be open and unsecured.

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
Let's start getting some data with a joke API to begin with. This API returns a random / different joke on every request.

Put this URl in your browser
[https://v2.jokeapi.dev/joke/Any?safe-mode](https://v2.jokeapi.dev/joke/Any?safe-mode)
If you have successfully installed the Chrome or Firefox extension you should see the following.

  ![JSON data](https://raw.githubusercontent.com/uwetom/media-production-worksheets/master/wk15-using-external-data/images/joke-api-2.png)

## Data repositories / libraries
You can find a list of unsecured data with API access here

[https://mixedanalytics.com/blog/list-actually-free-open-no-auth-needed-apis/](https://mixedanalytics.com/blog/list-actually-free-open-no-auth-needed-apis/)

[https://free-apis.github.io/#/browse](https://free-apis.github.io/#/browse)

## Code Challenge - get some data
Now you have a go using weather data using open meteo. Look at the documentation and try and work out what request you need to make in order to return some weather data for our current location…
[https://open-meteo.com/](https://open-meteo.com/)
(Hint: use maps to get our Latitude and Longitude position)

The returned data should look like:

![enter image description here](https://raw.githubusercontent.com/uwetom/media-production-worksheets/master/wk15-using-external-data/images/meteo-api-2.png)

[Need the solution?](https://uwetom.github.io/media-production-worksheets/api-solutions.html)

## API Keys
For many data repositories it is quite common to need to make an account and log in. You are then given a passkey (an API Key) which you ad to the url with the request.

This example of data about Near Earth Objects (asteroids that will pass close to earth) https://api.nasa.gov/ needs a log in and API Key.



Now let's get this data into Unity and learn how to use it....
<!--stackedit_data:
eyJoaXN0b3J5IjpbODMxMjUzMzk4LC0xNDIzMjQyNjAzLDE0OT
M1MTAyNzYsLTE3NjA2MjQzNjgsMTYyMTc1OTc2NywtMTA0MDE1
MzEyMywxMzg0ODU4MTc4LDEzMzYxMjgyMDgsLTY2OTgzOTMxMC
wtNjkyNjA4MDE2LDkwOTE2ODM4MSw5MzEyMzE0NjRdfQ==
-->