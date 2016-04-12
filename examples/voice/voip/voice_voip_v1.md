## Voice VoIP Example Application

It is a simple java application which shows how the following resources works:

* **/voice/v1/voip/{id}/phoneNumbers/{phoneNumber}/phonebooks**
    * GET - get phone books 
* **/voice/v1/voip/{id}/phoneNumbers/{phoneNumber}/calls** - 
    * GET . get call history of a customers phone
* **/voice/v1/voip/{id}/phoneNumbers/{phoneNumber}/calls** 
    * POST - initiates an call
* **/voice/v1/voip/{id}/phoneNumbers/{phoneNumber}/forwardings**
    * GET - get current settings for the call forwarding of a specified phone number
    * PUT - set the call forwarding configuration of a specific type
    * DELETE - delete all forwarding entries 

<p class="note">
  <strong>Note</strong>: API Documentation you can find under: <a href="https://github.com/swisscom-api/doc/wiki" target="_blank">Swisscom API Documentation</a>
</p>

## How to configured your clientId/consumerSecret

In order to set up your client_id and consumer_secret which has been assigned to your developer account, you have to change the two following properties under: **{glassfish4Path}\glassfish\domains\domain1\applications\voipapis\application.properties**

*   **local.consent_client_id**
*   **local.consent_auth_header** (encoded with base64 - client_id:consumer_secret)


## How to run the application

1.	Download and unzip the following file ./glassfish4WithApp.zip
2.	Make sure that you have a java version >= 1.7
3.	Run the server with build-in application by executing the following command line: {glassfish4Path}\glassfish\bin asadmin start-domain domain1
4.	Open a web browser: http://localhost:8080/voipapis/index.xhtml




