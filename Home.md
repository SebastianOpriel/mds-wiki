# Welcome to Mobility Data Space

## Access to Mobility Data Space 

To get access to the data room with your connector, you first need a valid DAPS token. You can request this token under [Requested & Issued Demo certificates](https://industrialdataspace.jiveon.com/docs/DOC-2002) or directly from [Gerd Brost](https://www.dataspaces.fraunhofer.de/de/software/identity_provider.html).

If you are using the [Dataspace Connector](https://github.com/International-Data-Spaces-Association/DataspaceConnector), you can configure your connector with tokens as described under  [Dataspace Connector-Configuration](https://international-data-spaces-association.github.io/DataspaceConnector/Deployment/Configuration). Now you can [connect your connector e.g. to one of the brokers](https://github.com/Mobility-Data-Space/mobility-data-space/wiki/How-to-configure-a-Dataspace-Connector-to-use-the-MDS#testing-the-connector-communication) to publish your own resources or request resources from other connectors in the dataspace.

## Stages
There are two separate stages or environments of the Mobility Data Space. There is a test environment and a pilot environment. As the name implies, the test environment is used to test new connectors and resources. 
If you have a new connector, you should first test it in the test environment.

### Test environment
An overview of the test environment can be found here: https://logging.test.mobilitydataspace.io/

#### Broker / Metadata Catalog
The user interface of the broker/metadata catalog can be found at https://broker.test.mobilitydataspace.io/resources
The IDS self-disclosure are available at https://ids.broker.mobilitydataspace.io 
The IDS interface for publishing a resource can be found at https://ids.broker.test.mobilitydataspace.io/infrastructure **(available for POST requests only)**

#### Clearing House
For logging purposes a valid Clearing House URL must be configured in the Dataspace Connector configuration.
The Clearing House URL for the test stage is https://logging.test.mobilitydataspace.io/messages/log/
In the Dataspace Connector configuration the value of the clearing.house.url property must be set accordingly.
More information on how to configure the Clearing House URL for the Dataspace Connector can be found here: https://international-data-spaces-association.github.io/DataspaceConnector/Deployment/Configuration#ids-settings

### Pilot environment
An overview of the pilot environment can be found here: https://logging.mobilitydataspace.io/

#### Broker / Metadata Catalog
The user interface of the broker/metadata catalog can be found at https://broker.mobilitydataspace.io/resources  
The IDS self-disclosure are available at https://ids.broker.mobilitydataspace.io 
The IDS interface for publishing a resource can be found at https://ids.broker.mobilitydataspace.io/infrastructure **(available for POST requests only)**.

#### Clearing House
For logging purposes a valid Clearing House URL must be configured in the Dataspace Connector configuration.
The Clearing House URL for the test stage is https://logging.mobilitydataspace.io/messages/log/
In the Dataspace Connector configuration the value of the clearing.house.url property must be set accordingly.
More information on how to configure the Clearing House URL for the Dataspace Connector can be found here: https://international-data-spaces-association.github.io/DataspaceConnector/Deployment/Configuration#ids-settings

## Ontology
The Mobility Data Space uses the MobiDS Ontologie. 