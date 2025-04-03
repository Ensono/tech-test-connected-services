# The technical test for Connected Services consultants

## Overview
There is an existing Ensono Digital REST API, and we’d like to you write a client to interact with it. The client can be any type of project, even a console application. We are looking for you to demonstrate a good engineering (e.g. SOLID practices, etc) and testing approach (TDD/BDD).

The endpoint enables CRUD operations on a User. There are some constraints on this, the details of which are below. You have full access to the Internet, please feel free to use it. You may use whichever libraries you feel appropriate. Please keep notes of what you have done, and what you would do next given more time (eg. make it production ready, etc), so we can discuss this with you after the test.

## Available Services
### Auth Token Service
All calls to the endpoint require an auth token in the header in the format _bearer [token]_. For example:

```Authorization: bearer 12345678```

See this link for how to set a bearer token in an HTTP header. https://developers.google.com/gmail/markup/actions/verifying-bearer-tokens - you do not need to verify the token, just submit it with every request.

Calling the token service will provide a valid token which can be used to call the user REST api.

* Url: [http://ensono-test.hyhrfebuhvd2eueh.westeurope.azurecontainer.io:7000/token](http://ensono-test.hyhrfebuhvd2eueh.westeurope.azurecontainer.io:7000/token) • Verb: GET

### Create User Service
When creating a User, the name must be "Joe" and the password "MyCurrentPassword." The service endpoint below can be called to create a user. The new user URL will be returned in the relevant response header.

* URL: [http://ensono-test.hyhrfebuhvd2eueh.westeurope.azurecontainer.io:7000/users](http://ensono-test.hyhrfebuhvd2eueh.westeurope.azurecontainer.io:7000/users) • Verb: POST • Parameters: name, password (posted as form data)

Get, Update and Delete a User Service
This service endpoint can be called with the relevant verb to get, update or delete a user. Note that when updating a password, the new password should be MyNewPassword

* URL: [http://ensono-test.hyhrfebuhvd2eueh.westeurope.azurecontainer.io:7000/users/{UserId}](http://ensono-test.hyhrfebuhvd2eueh.westeurope.azurecontainer.io:7000/users/1234) • Verb: GET, PUT, DELETE • Parameters: name, password (posted as form data)

## User Stories to Test
Please test the following user stories.

### User Creation
As a user   
I want to be able to create a user account   
So that my identity is known  

### User Update
As a user   
I want to be able to update my password  
o that I can keep my account secure
