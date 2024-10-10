[Back](https://uwetom.github.io/media-production-worksheets)

# Using external data in unity
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

You can find a list of unsecured data with API access here

[https://mixedanalytics.com/blog/list-actually-free-open-no-auth-needed-apis/](https://mixedanalytics.com/blog/list-actually-free-open-no-auth-needed-apis/)

[https://free-apis.github.io/#/browse](https://free-apis.github.io/#/browse)

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

  ![JSON data](https://raw.githubusercontent.com/uwetom/media-production-worksheets/master/wk15-using-external-data/images/joke-api-1.png)

## Code Challenge - get some data
Now have a go using weather data using open meteo. Look at the documentation and try and work out what request you need to make in order to return some whether data about our current location…

[https://open-meteo.com/](https://open-meteo.com/)
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTY2OTgzOTMxMCwtNjkyNjA4MDE2LDkwOT
E2ODM4MSw5MzEyMzE0NjRdfQ==
-->