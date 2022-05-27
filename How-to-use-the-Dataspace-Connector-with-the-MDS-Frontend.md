## Set-up the connector

1. Download [a last release of the Dataspace Connector](https://github.com/International-Data-Spaces-Association/DataspaceConnector/releases).

2. Request the DAPS token at [daps-certificates@aisec.fraunhofer.de](mailto:daps-certificates@aisec.fraunhofer.de)

3. Configure the connector. In the configuration file `resources/conf/config.json` <br>
a) set the path to the DAPS Token (keystore) <br>
b) change the connector deploy mode to PRODUCTIVE:<br>
`"ids:connectorDeployMode" : { "@id" : "idsc:PRODUCTIVE_DEPLOYMENT },`<br>
c) set the connector accessURL <br>
d) configure [another parameters](https://international-data-spaces-association.github.io/DataspaceConnector/Deployment/Configuration) if needed

4. Deploy and start the connector

5. If everything worked fine, the connector for the local build is available at `https://localhost:8080/.` 

## Set-up the frontend

1. Download [a last release of the Dataspace Connector Frontend](https://github.com/Mobility-Data-Space/DataspaceConnectorUI/releases).

2. Install [Node.js v.14](https://nodejs.org/en/download/)

3. Install the frontend: `npm install --no-audit`

4. Start the frontend `npm start`. 

5. If everything worked fine, the frontend for the local build is available at `https://localhost:8082/.` 

<img src="https://user-images.githubusercontent.com/91048868/169023128-e79a8770-0469-4264-9894-9ceed79deba8.jpg" width=600><br>

6. Using _Advanced View => Settings => General_ set the connector name, connector description, connector curator and connector maintainer.
**Please be aware that this information is accurate and complete**. These fields represent the connector in the MDS catalog.

<img src="https://user-images.githubusercontent.com/91048868/169081507-66ef0389-08ab-47ac-a240-4e588a9e6752.jpg" width=600>

## Data consumption

1. Using _Data Consumption => Requests => Request Resource_ select a desired resourse. You can directly enter the Connector URL (Access URL in the MDS Catalog) and select _Show available reasources_

<img src="https://user-images.githubusercontent.com/91048868/170651063-4cb93e89-cca8-44c2-aaff-a4a371c2db54.jpg" width=600><br>

Alternatively you can select _BROKER_ tab, enter the [Catalog URL](https://github.com/Mobility-Data-Space/mobility-data-space/wiki#broker--metadata-catalog) ([URL]/infrastructure) und a search term for the direct search of desired resources in the MDS Catalog.

2. Select a desired resource and click the icon _Show representations_ (second last on the right side).

<img src="https://user-images.githubusercontent.com/91048868/170658417-77c046df-c136-4b86-a709-012a38cb8c90.jpg" width=600><br>

3. Click the URL-Button under _Select representation_ and subsequently click the icon _Request artifact_ (last on the right side).

<img src="https://user-images.githubusercontent.com/91048868/170659186-66eb5861-6300-498b-b271-144180d27310.jpg" width=600><br>

4. Check the list of rules (usage policies), and a licence and click _ACCEPT_ if you agree with the usage policies. Additionally you can turn on _Subscribe_ to get a subscription for the resource. 

<img src="https://user-images.githubusercontent.com/91048868/170662482-56dd90dd-9bf4-4f76-81aa-ba021a472b30.jpg" width=400><br>

5. Click the URL-Button under _Download_ to download the requested artifact.