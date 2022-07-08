# Currently under construction until 11.07. 

# Welcome to the Mobility Data Space

## Overview of the Mobility Data Space 

The overview of the Mobility Data Space with explanations about component functionalities and currently deployed environments you can find [hier](https://github.com/Mobility-Data-Space/mobility-data-space/wiki/MDS-Architecture)

## Access to the Mobility Data Space 

After the contract signing with the Mobility Data Space you can get an access to the MDS in five simple steps (estimated time for the test implementation is one hour). <br>

### First Step (Software installation).
Download and install the connector. We recommend to use the [Dataspace Connector](https://github.com/International-Data-Spaces-Association/DataspaceConnector), but you also can use other connectors which are compatible with the DSC. <br>
_Optionally but recommended:_ Download and install the MDS Frontend.

### Second Step (Certificates). 
Register your connector to obtain your unique MDS certificate (so called DAPS token)

### Third Step (Configuration). 
Configure your connector before starting.

### [Fourth Step (Registration in the Catalog)](https://github.com/Mobility-Data-Space/mobility-data-space/wiki/4.-Step-(Registration-in-the-MDS-Catalog))
Register your connector in the MDS Catalog. <br>

### Fifth Step (Offering/Consuming data). 
Congratulations! Now you can offer and/or consume mobility data via MDS.



Then you can start a registration process to obtain your unique MDS certificate (so called DAPS token).

If you are using the [Dataspace Connector](https://github.com/International-Data-Spaces-Association/DataspaceConnector), you can configure your connector with tokens as described under  [Dataspace Connector-Configuration](https://international-data-spaces-association.github.io/DataspaceConnector/Deployment/Configuration). <br>
Please ensure that you are using a 7.x.x. version of the DSC connector, otherwise [update your DSC connector](https://github.com/International-Data-Spaces-Association/DataspaceConnector/releases).
To configure the connector please follow steps on the Settings Page.

## Stages
There are two separate stages or environments of the Mobility Data Space. There is a test environment and a productive environment. As the name implies, the test environment is used to test new connectors and resources. 
If you implemented or installed a new connector, you should first test it in the test environment.

Please note, that there is no logical link between the _test mode_ of the Dataspace Connector and the Mobility Data Space _test environment_. You need to use the **productive mode** of the Dataspace Connector to register in the **test environment** Catalog.

### Components in the test environment

* DAPS: https://daps.test.mobility-dataspace.eu
* Catalog: https://catalog.test.mobility-dataspace.eu
* Clearing House: https://clearing.test.mobility-dataspace.eu

### Components in the productive environment

* DAPS: https://daps.mobility-dataspace.eu
* Catalog: https://catalog.mobility-dataspace.eu
* Clearing House: https://clearing.mobility-dataspace.eu

To ensure traceability and auditability of transactions in the MDS, we require our participants to use the Clearing House. Only metadata (transaction ID, timestamp) are logged. Please make sure to set the logging in the connector accordingly. For further details s. Settings Page.

## Ontology
The Mobility Data Space uses the MDS Ontologie for the describing of additional mobility related metadata attributes. 

