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

Install a JSON formatter browser extension / addon
Chrome browser extension
https://chrome.google.com/webstore/detail/json-formatter/bcjindcccaagfpapjjmafapmmgkkhgoa?hl=en 

Firefox addon
https://addons.mozilla.org/en-GB/firefox/addon/basic-json-formatter/ 

Use Safari or Edge? We feel for you…

<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE5NzM5NDcyODMsOTMxMjMxNDY0XX0=
-->