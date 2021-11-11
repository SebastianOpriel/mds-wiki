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

Swagger UI allows to visualize the REST API’s components and interact with them. Each component you created has a self-description link, which can be used as **complete URI** (red marked below) or as **ID** (yellow marked below).

<img src="https://user-images.githubusercontent.com/91048868/141110162-b3081d87-45a2-4ebb-8554-5b1154193e9c.jpg" width=700>

Swagger UI provides the following endpoints for components

* `GET` for getting a complete list of components
* `POST` for creating a new component
*  `GET {ID}` for getting the component with the specified ID
*  `PUT {ID}` for changing the component with the specified ID
*  `DELETE {ID}` for deleting the component with the specified ID

Furthermore it is possible to define a child component for a component (for example, _rule_ is the child component for _contract_) and perform all operations mentioned above with child components too. The detailed description of the REST API you can find [here](https://international-data-spaces-association.github.io/DataspaceConnector/Documentation/v6/RestApi).

For all operations within Swagger UI you must use the following sequence of commands: select **Try it out**, enter all required parameters (if needed), select **Execute**.

<img src="https://user-images.githubusercontent.com/91048868/141118138-79c94bfb-e972-4dbb-b6d0-213df82027f8.jpg" width=500>

HTTP Responses with codes 200, 201 or 204 would mean that your interaction was successful, all other responses would mean that your interaction failed. Further information about HTTP Responses you can find [here.](https://www.w3.org/Protocols/rfc2616/rfc2616-sec10.html)

### Register your resource step-by-step

**Step 1.** Create an _artifact_ 

To provide your raw data you need to create an artifact. For this test example an attrubute `value` containing a simple string is used. In the productive service you will use an attribute `accessUrl` to define your remote data source, as explained [here](https://international-data-spaces-association.github.io/DataspaceConnector/CommunicationGuide/v6/Provider#option-2-add-remote-data). 

Use the endpoint [Artifacts] `POST /api/artifacts`.

<img src="https://user-images.githubusercontent.com/91048868/141141000-14f646c0-f533-4910-9f9b-48635703d1dc.jpg" width=300>
<br/>
<br/>

**Step 2.** Create an _representation_

Use the endpoint [Representations] `POST /api/representations`.

<img src="https://user-images.githubusercontent.com/91048868/141144750-569c3961-08e2-432d-9e62-234678c4fdc8.jpg" width=350>
<br/>
<br/>

**Step 3.** Link the _artifact_ to the _representation_

Use the endpoint [Representations] `POST ​/api​/representations​/{id}​/artifacts`.

Enter the _representation_ **ID** and the _artifact_ **URI** into [the corresponding fields](https://user-images.githubusercontent.com/91048868/141148819-483988b8-d8a4-4aae-9551-3684552ca667.jpg). 

**Step 4.** Create an usage policy

An overview of existing usage policies can be found [here](https://international-data-spaces-association.github.io/DataspaceConnector/Documentation/v6/UsageControl).

You can use the endpoint [Usage Control] `POST /api/examples/policy` to create an usage policy you needed. Input samples for different policies are presented [here](https://international-data-spaces-association.github.io/DataspaceConnector/Documentation/v6/UsageControl). In this example the simpliest policy "provide access" (data usage is allowed) is used.

<img src="https://user-images.githubusercontent.com/91048868/141151385-ebd9d11f-3645-478c-b5a6-1a6fa81f0ded.jpg" width=350>
<br/>
<br/>

**Step 5.** Create a _rule_

Use the endpoint [Rules] `POST ​/api​/rules`. You can just copy the created policy into the "value" attribute field (escape internal quotation marks with backslashes if needed).

<img src="https://user-images.githubusercontent.com/91048868/141153874-e79e3ce3-52fb-4692-8e40-2ff1e56e528f.jpg" width=350>
<br/>
<br/>

**Step 6.** Create a _contract_

Use the endpoint [Contracts] `POST ​/api​/contracts`.

<img src="https://user-images.githubusercontent.com/91048868/141156014-3b645370-f328-49de-9217-680655c0cbdf.jpg" width=400>
<br/>
<br/>

**Step 7.** Link the _rule_ to the _contract_

Use the endpoint [Contracts] `POST ​/api​/contracts​/{id}​/rules`.

Enter the _contract_ **ID** and the _rule_ **URI** into [the corresponding fields](https://user-images.githubusercontent.com/91048868/141157105-8e6a6741-6241-46e9-b8d9-038417ce004e.jpg). 

**Step 8.** Create an _offer_

Use the endpoint [Offered Resources] `POST ​/api​/offers`.

<img src="https://user-images.githubusercontent.com/91048868/141163013-0b3a19b5-e81c-431b-9c34-6f4556cb43bf.jpg" width=450>
<br/>
<br/>

Please note, that the "[offer] title" and the "[offer] description" are **key descriptions to represent your offer**, which are located directly in the broker catalog.

**Step 9.** Link the _representation_ to the _offer_

Use the endpoint [Offered Resources] `POST ​/api/offers/{id}/representations`.

Enter the _offer_ **ID** and the _representation_ **URI** into [the corresponding fields](https://user-images.githubusercontent.com/91048868/141268423-5f9b1396-5f8b-49e6-8188-ee413e0cac16.jpg). 

**Step 10.** Link the _contract_ to the _offer_

Use the endpoint [Offered Resources] `POST /api/offers/{id}/contracts`.

Enter the _offer_ **ID** and the _contract_ **URI** into [the corresponding fields](https://user-images.githubusercontent.com/91048868/141269178-2a8c6489-f0e5-400c-bffa-04abebce4def.jpg). 

**Step 11.** Create a _catalog_

Use the endpoint [Catalogs] `POST ​/api​/catalogs`.

<img src="https://user-images.githubusercontent.com/91048868/141269680-108b6560-9453-46f8-bf87-8ef801dbb0d2.jpg" width=300>
<br/>
<br/>

**Step 12.** Link the _offer_ to the _catalog_

Use the endpoint [Catalogs] `POST /api/catalogs/{id}/offers`.

Enter the _catalog_ **ID** and the _offer_ **URI** into [the corresponding fields](https://user-images.githubusercontent.com/91048868/141270261-472dd7db-1cfd-498e-a55f-76085f22151d.jpg). 

**Step 13.** Update The connector

Use the endpoint [Messages] `POST /api/ids/connector/update`.

Enter `https://ids.broker.test.mobilitydataspace.io/infrastructure` as the recipient URL.

<img src="https://user-images.githubusercontent.com/91048868/141270978-faaf7253-93ae-4967-b71b-d44442ae3ea6.jpg" width=400>
<br/>
<br/>

**Step 14.** Register your resourse at the broker

Use the endpoint [Messages] `POST /api/ids/resource/update`.

Enter `https://ids.broker.test.mobilitydataspace.io/infrastructure` as the recipient URL and the _offer_ **ID** as the resource id.

<img src="https://user-images.githubusercontent.com/91048868/141272052-b1868e36-a452-4d6c-ab8c-0e3e5b206fe0.jpg" width=450>
<br/>
<br/>

**Congratulations!** Now your resource should be available on [the Test Broker](https://broker.test.mobilitydataspace.io/resources).