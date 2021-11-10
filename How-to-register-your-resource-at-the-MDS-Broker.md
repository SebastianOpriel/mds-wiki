## Overview of resource components
After your connector [has been successfully registered](https://github.com/Mobility-Data-Space/mobility-data-space/wiki/How-to-configure-a-Dataspace-Connector-to-use-the-MDS), you can start defining, describing and offering resourses via the broker.

For this purpose you need to create the following components:
* _artifact_, which has a 1:1 relation to the raw data
* _representation_, which contains one or more artifacts
* _rule_, which represents one usage policy
* _contract_, which contains one or more rules
* _offer_, which contains one or more representations and one or more contracts
* _catalog_, which contains one or more offers

The overview of the data model you can find [here](https://international-data-spaces-association.github.io/DataspaceConnector/Documentation/v6/DataModel).
Please note that if one or more of these components are missing or not properly linked, the registration of your resource at the broker is not technically possible.

## How to create resource components using Swagger UI

### Introduction

The [Dataspace Connector’s repository](https://github.com/International-Data-Spaces-Association/DataspaceConnector) comes with a `scripts/tests` folder that provides some Python scripts. Using these you are able to create different data offering samples: for a single resource with a single usage policy, a single resource with multiple usage policies or providing multiple artifacts at once. Feel free to use or modify them.

Alternatively you can use the Swagger UI of the Dataspace Connector to create all resource components manually. In this chapter the procedure is explained step by step on the basis of a minimalistic example (a single catalog with a single offer with a single representation with a single artifact). The important attributes which will be displayed later on the broker, are highlighted. **Please fill out the attribute values properly to have a best possible representation of your offer on the broker.**

### Basic features of Swagger UI

Swagger UI allows to visualize the REST API’s components and interact with them. Each component you created has a self-description link, which can be used as complete URI (red marked below) or as ID (yellow marked below).

<img src="https://user-images.githubusercontent.com/91048868/141110162-b3081d87-45a2-4ebb-8554-5b1154193e9c.jpg" width=700>

Swagger UI provides the following endpoints for components

* `GET` for getting a complete list of components
* `POST` for creating a new component
*  `GET {ID}` for getting the component with the specified ID
*  `PUT {ID}` for changing the component with the specified ID
*  `DELETE {ID}` for deleting the component with the specified ID

Furthermore it is possible to define a child component for a component (for example, _rule_ is the child component for _contract_) and perform all operations mentioned above with child components too. The detailed description of the REST API you can find [here](https://international-data-spaces-association.github.io/DataspaceConnector/Documentation/v6/RestApi).

For all operations within Swagger UI you must use the following sequence of commands: select **Try it out**, fill out all required parameters (if needed), select **Execute**.

<img src="https://user-images.githubusercontent.com/91048868/141118138-79c94bfb-e972-4dbb-b6d0-213df82027f8.jpg" width=500>

HTTP Responses with codes 200, 201 or 204 would mean that your interaction was successful, all other responses would mean that your interaction failed. Further information about HTTP Responses you can find [here.](https://www.w3.org/Protocols/rfc2616/rfc2616-sec10.html)

### Register your resource step-by-step

**Step 1.** Create an _artifact_ 

To provide your raw data you need create an artifact. For this test example an attrubute `value` containing a simple string is used. In the productive service you will use an attribute `accessUrl` to define your remote data source, as explained [here](https://international-data-spaces-association.github.io/DataspaceConnector/CommunicationGuide/v6/Provider#option-2-add-remote-data). 

<img src="https://user-images.githubusercontent.com/91048868/141141000-14f646c0-f533-4910-9f9b-48635703d1dc.jpg" width=300>

**Step 2. ** Create a _representation_

<img src="https://user-images.githubusercontent.com/91048868/141144750-569c3961-08e2-432d-9e62-234678c4fdc8.jpg" width=300>