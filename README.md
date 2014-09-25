#Forecast.it API

API documentation for the Forecast.it platform  http://forecast.it

This is a [REST](http://en.wikipedia.org/wiki/Representational_state_transfer)-style [API](http://en.wikipedia.org/wiki/Application_programming_interface) that uses [JSON](http://json.org/) for serialization and [HTTP](http://en.wikipedia.org/wiki/Hypertext_Transfer_Protocol) [Basic authentication](http://en.wikipedia.org/wiki/Basic_access_authentication).


##Making a request

All URLs start with https://api.forecast.it/api/v1/. **SSL only**. The path contains the API version. If we change the API in backward-incompatible ways, we'll increment the version marker and maintain stable support for the old URLs.

To make a request for all the projects on your account, you'd append the projects index path to the base url e.g. https://api.forecast.it/api/v1/projects

Using [curl](http://curl.haxx.se/) it will look like this:

```shell
curl -u {API-key}: https://api.forecast.it/api/v1/projects
```

That's it. Super simple, eh?

##Authentication

If you're making a private integration with Forecast.it for your own purposes, you can use HTTP Basic authentication. This is secure since all requests in Forecast.it use [SSL](http://en.wikipedia.org/wiki/Transport_Layer_Security).

API keys are generated in the administration module and used as username in Basic authentication.

Your API keys can be found and/or generated by logging into your Forecast.it account, clicking on the "Administration" link in the upper-right, and then clicking on "API Keys". From there you can generate, view, delete and (de)activate API Keys for use in your integrations.

**API keys provide full access to your Forecast.it account, so keep them like a secret.**

###Disabling an API key

If you're worried that an API key has been compromised, or you're simply no longer using the integration that was accessing your account through a particular API key, Forecast.it makes it possible to disable or delete that API key.

###API key security

API keys grant full access to your Forecast.it account, and should be protected the same way you would protect your password. In particular, there are a few common scenarios to keep in mind when working with API keys:
* Give each integration its own API key (or at least use a few). If a specific API key is compromised, you can disable that key without disabling access to all of your other integrations.
* Be careful not to expose the key to the public (such as in screenshots, videos, help documentation, etc). Remember that blurring your data isn't always enough. It's best to use "cut" functions in your graphics program to remove the data completely.
* If a key needs to be shared, generate a new key so it can be disabled, if needed. Make sure never to email the API key; if your email account becomes compromised, the emailed key would allow hackers access to your Forecast.it account as well.

##No XML, just JSON

We only support [JSON](http://json.org/) for serialization of data. Our format is to have no root element and we use [camelCase](http://en.wikipedia.org/wiki/CamelCase) with a lower case starting letter to describe attribute keys. This means that you have to send `Content-Type: application/json; charset=utf-8` when you're POSTing or PUTing data into Forecast.it. **All API URLs only accept and return JSON.**

##Responses

All GET requests return 200 OK on success along with the JSON of the requested elements (See specific resource entry for JSON examples).

Successful POST requests return 201 CREATED, and successful PUT requests return 200 OK. 

Successful PUT and POST requests also return the JSON of the created/updated resource similar to what you would get from a GET request for that specific resource.

Successful DELETE requests return 200 OK

##Handling errors

If Forecast.it is having trouble, you might see a 5xx error. 500 means that the app is entirely down, but you might also see 502 Bad Gateway, 503 Service Unavailable, or 504 Gateway Timeout. It's your responsibility in all of these cases to retry your request later.

Attempting a DELETE may result in a 403 Forbidden if the resource can not be deleted due to dependencies. Successful deletions return a 200 OK response. **Note that some resources will only be deactivated by a DELETE request and will therefore still appear on GET requests, but with â€œactiveâ€� : false.**

404 Errors usually means that you are trying to PUT/DELETE a resource that doesn't exist or doesn't belong to your company. 

##API sections

* [Users](https://github.com/Forecast-it/API/blob/master/sections/users.md)
* [Roles](https://github.com/Forecast-it/API/blob/master/sections/roles.md)
* [Teams](https://github.com/Forecast-it/API/blob/master/sections/teams.md)
* [Customers](https://github.com/Forecast-it/API/blob/master/sections/customers.md)
* [Business Units](https://github.com/Forecast-it/API/blob/master/sections/businessUnits.md)
* [Projects](https://github.com/Forecast-it/API/blob/master/sections/projects.md)
* [Project Phases](https://github.com/Forecast-it/API/blob/master/sections/projectPhases.md)
* [Project Types](https://github.com/Forecast-it/API/blob/master/sections/projectTypes.md)
* [Project People/Resources](https://github.com/Forecast-it/API/blob/master/sections/projectResources.md)
* [User Stories](https://github.com/Forecast-it/API/blob/master/sections/userStories.md)
* [User Story Types](https://github.com/Forecast-it/API/blob/master/sections/userStoryTypes.md)
* [Sprints](https://github.com/Forecast-it/API/blob/master/sections/sprints.md)
* [Tasks](https://github.com/Forecast-it/API/blob/master/sections/tasks.md)
* [Time Tracking/Registration](https://github.com/Forecast-it/API/blob/master/sections/timeRegistration.md)
* [Tags](https://github.com/Forecast-it/API/blob/master/sections/tags.md)
* [Files/Attachments](https://github.com/Forecast-it/API/blob/master/sections/filesAttachments.md)
* [Milestones](https://github.com/Forecast-it/API/blob/master/sections/milestones.md)
* [Versions](https://github.com/Forecast-it/API/blob/master/sections/versions.md)

##API libraries

* [Google APIs Client Library](https://code.google.com/p/google-api-java-client/) - Java
* [Jersey](https://jersey.java.net/) - Java
* Feel free to add libraries for other languages :) 

##Help us make it better

Please tell us how we can make the API better. If you have a specific feature request or if you found a bug, please use GitHub issues. Fork these docs and send a pull request with improvements.

To talk with us and other developers about the API, [post a question on StackOverflow](http://stackoverflow.com/questions/ask) tagged `forecast_it` or open a support ticket through the Forecast.it feedback system.

You can always reach us via email at info@forecast.it