# Requesting and Configuring the certificate
The first thing you need to do to let your connector communicate with others in the MDS is to request a valid certificate for your connector. The request process is described at [Accessing the MDS](https://github.com/Mobility-Data-Space/mobility-data-space/wiki/Welcome-to-Mobility-Data-Space#zugang-zum-datenraum-mobilit%C3%A4t)

The certificate will be send to you in a zip-File by e-Mail. The zip-File contains a p12-file which must be configured in your Dataspace Connector as described in the [Dataspace Connector Configuration](https://international-data-spaces-association.github.io/DataspaceConnector/Deployment/Configuration#step-2-ids-certificate) section.

# Testing the connector communication using Swagger UI
To check if your connector can communicate with others in the MDS you can register your connector at the [MDS Test Broker](https://broker.test.mobilitydataspace.io/connector). Follow these steps to register your connector:
1. Browse to the Swagger UI. If you have your connector running locally on port 8080 this would be https://localhost:8080/api/docs 
<br>Please note, that the application uses Spring Security. Each endpoint behind /** needs a [user authentication](https://international-data-spaces-association.github.io/DataspaceConnector/Deployment/Configuration#authentication).
2. Scroll down to the [IDS Messages](https://localhost:8080/api/swagger-ui/index.html?configUrl=/v3/api-docs/swagger-config#/IDS%20Messages) section. 
3. Open the [Connector Update Message](https://localhost:8080/api/swagger-ui/index.html?configUrl=/v3/api-docs/swagger-config#/IDS%20Messages/sendConnectorUpdateMessage_3)
4. Select __Try it out__ on the right hand side.
5. Enter https://ids.broker.test.mobilitydataspace.io/infrastructure as the recipient URL and select __Execute__.
6. Browse to [MDS Test Broker](https://broker.test.mobilitydataspace.io/connector). Your connector should be listed in the list of connectors.

Congratulations. You've successfully set up a connector that can communicate to other parties in the MDS and you registered your connector at the Test Broker for others to be found.

## Unregistering a connector from a Broker
To unregister your connector from the Test Broker use the Swagger UI again. In the [IDS Messages](https://localhost:8080/api/swagger-ui/index.html?configUrl=/v3/api-docs/swagger-config#/IDS%20Messages) section use the [Connector unavailable message](https://localhost:8080/api/swagger-ui/index.html?configUrl=/v3/api-docs/swagger-config#/IDS%20Messages/sendConnectorUpdateMessage_4) and follow steps 4-6 from above to unregister your connector. 
