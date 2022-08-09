# Architecture
![Architecture Overview](https://user-images.githubusercontent.com/91048868/173079801-34002bd5-8bae-41ac-8f13-f290cae10365.jpg "Architecture Overview")

# Components
To be added

# Environments
There are two separate environments of the Mobility Data Space. There is a test environment and a productive environment. As the name implies, the test environment is used to test new connectors and resources. If you implemented or installed a new connector, you should first test it in the test environment.

Please note, that there is no logical link between the Dataspace connector's deploy mode `TEST_DEPLOYMENT`/`PRODUCTIVE_DEPLOYMENT` (see [here](https://github.com/International-Data-Spaces-Association/IDS-Messaging-Services/wiki/10.-Settings:-Connector-Deploy-Modes) and [here](https://github.com/International-Data-Spaces-Association/DataspaceConnector/blob/4a39a8a4de71c0668a12669c233fc0614fb79ab2/src/main/resources/conf/config.json#L11)) and the Mobility Data Space's _test environment_ and _productive environment_. In both environments, you need to set the Dataspace Connector's deploy mode to `PRODUCTIVE_DEPLOYMENT` to register your connector at the Catalog.

## Components in the test environment
* Catalog (website for human user's browsing): https://catalog.test.mobility-dataspace.eu
* DAPS (technical endpoint for connector configuration): https://daps.test.mobility-dataspace.eu
* Catalog (technical endpoint for connector configuration): https://broker.test.mobility-dataspace.eu/infrastructure
* Clearing House (technical endpoint for  connector configuration): https://clearing.test.mobility-dataspace.eu

## Components in the productive environment
* Catalog (website for human user's browsing): https://catalog.mobility-dataspace.eu
* DAPS (technical endpoint for connector configuration): https://daps.mobility-dataspace.eu
* Catalog (technical endpoint for connector configuration): https://broker.mobility-dataspace.eu/infrastructure
* Clearing House (technical endpoint for connector configuration): https://clearing.mobility-dataspace.eu
