## Set-up the connector

1. Download [a last release of the Dataspace Connector](https://github.com/International-Data-Spaces-Association/DataspaceConnector/releases).

2. Request the DAPS token at [daps-certificates@aisec.fraunhofer.de](mailto:daps-certificates@aisec.fraunhofer.de)

3. Configure the connector. In the configuration file `resources/conf/config.json`
a) set the path to the DAPS Token (keystore)
b) change the connector deploy mode to PRODUCTIVE:<br>
`"ids:connectorDeployMode" : { "@id" : "idsc:PRODUCTIVE_DEPLOYMENT },`
c) configure [another parameters](https://international-data-spaces-association.github.io/DataspaceConnector/Deployment/Configuration) if needed

4. Deploy and start the connector

5. If everything worked fine, the connector for the local build is available at `https://localhost:8080/.` 

## Set-up the frontend

1. Download [a last release of the Dataspace Connector Frontend](https://github.com/Mobility-Data-Space/DataspaceConnectorUI/releases).

2. Install [Node.js v.14](https://nodejs.org/en/download/)

3. Install the frontend: `npm install --no-audit`

4. Start the frontend `npm start`. 

5. If everything worked fine, the frontend for the local build is available at `https://localhost:8082/.` 

<img src="https://user-images.githubusercontent.com/91048868/169023128-e79a8770-0469-4264-9894-9ceed79deba8.jpg" width=500>