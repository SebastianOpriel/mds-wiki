## Overview of resource components
After your connector [has been successfully registered](https://github.com/Mobility-Data-Space/mobility-data-space/wiki/How-to-configure-a-Dataspace-Connector-to-use-the-MDS), you can start defining, describing and offering resourses via the broker.

For this purpose you need to create the following components:
* artifact, which has a 1:1 relation to the raw data
* representation, which contains one or more artifacts
* rule, which represents one usage policy
* contract, which contains one or more rules
* offer, which contains one or more representations and one or more contracts
* catalog, which contains one or more offers

The overview of the data model you can find [here](https://international-data-spaces-association.github.io/DataspaceConnector/Documentation/v6/DataModel).
Please note that if one or more of these components are missing or not properly linked, the registration of your resource at the broker is not technically possible.

## How to create resource components using Swagger UI

### Introduction

The [Dataspace Connector’s repository](https://github.com/International-Data-Spaces-Association/DataspaceConnector) comes with a `scripts/tests` folder that provides some Python scripts. Using these you are able to create different data offering samples: for a single resource with a single usage policy, a single resource with multiple usage policies or providing multiple artifacts at once. Feel free to use or modify them.

Alternatively you can use the Swagger UI of the Dataspace Connector to create all resource components manually. In this chapter the procedure is explained step by step on the basis of a minimalistic example (a single catalog with a single offer with a single representation with a single artifact). The important attributes which will be displayed later on the broker, are highlighted. **Please fill out the attribute values properly to have a best possible representation of your offer on the broker.**

### Basic features of Swagger UI

Swagger UI allows to visualize the REST API’s components and interact with them. Each component you created has a self-description link, which can be used as complete URI (red marked below) or as ID (yellow marked below).
