## <a id='overview'>Voice VoIP Curl Examples</a> 

<p class="note">
   <strong>Note</strong>: <a href="https://rawgit.com/wiki/swisscom-api/doc/API_docs/voice/voice_voip_v1.html" target="_blank">Voice VoIP API Documentation</a>
</p>

### <a id='overview'>/voice/v1/voip/{id}/phoneNumbers/{phoneNumber}/calls </a>

* GET - Call history list
```
curl -ik -H "Authorization: Bearer %ACCESSTOKEN_GOES_HERE%" https://api.swisscom.com/voice/v1/voip/me/phoneNumbers/123/calls
```

* POST - Initiate an call
```
curl -ik-X POST -H "Authorization: Bearer %ACCESSTOKEN_GOES_HERE%" https://api.swisscom.com/voice/v1/voip/me/phoneNumbers/123/calls
```

### <a id='overview'>/voice/v1/voip/{id}/phoneNumbers/{phoneNumber}/phonebooks </a>

* GET - Phonebook entries
```
curl -ik -H "Authorization: Bearer %ACCESSTOKEN_GOES_HERE%" https://api.swisscom.com/voice/v1/voip/me/phoneNumbers/123/phonebooks
```

### <a id='overview'>/voice/v1/voip/{id}/numbers </a>

* GET - Voice VoIP numbers list
```
curl -ik -H "Authorization: Bearer %ACCESSTOKEN_GOES_HERE%" https://api.swisscom.com/voice/v1/voip/me/numbers
```

### <a id='overview'>/voice/v1/voip/{id}/phoneNumbers/{phoneNumber}/forwardings </a>

* GET - Current settings for the call forwarding of a specified phone number 
```
curl -ik -H "Authorization: Bearer %ACCESSTOKEN_GOES_HERE%" -H "Accept:application/json" -X GET -ik "https://api.swisscom.com/voice/v1/voip/me/phoneNumbers/%USER_PHONE_NUMBER%/forwardings"
```

* PUT - Set the call forwarding configuration of a specific type
```
curl -ik -H "Authorization: Bearer %ACCESSTOKEN_GOES_HERE%" -H "Accept:application/json" -H "Content-Type:application/json" -X PUT -ik "https://api.swisscom.com/voice/v1/voip/me/phoneNumbers/%USER_PHONE_NUMBER%/forwardings/busy"  -d "{\"active\": true, \"target\": \"0795481252\"}"
```

### <a id='overview'>/voice/v1/voip/{id}/phoneNumbers/{phoneNumber}/simrings </a>

* GET - The list of phone numbers, which ring simultaneously

```
curl -k -H "Authorization: Bearer %ACCESSTOKEN_GOES_HERE%" -H "Accept:application/json" -H "Content-Type:application/json" -X DELETE -ik "https://api.swisscom.com/voice/v1/voip/me/phoneNumbers/%USER_PHONE_NUMBER%/simrings"
```

* PUT  - Set a list of phone numbers, which ring simultaneously
```
curl -k -H "Authorization: Bearer %ACCESSTOKEN_GOES_HERE%" -H "Accept:application/json" -H "Content-Type:application/json" -X PUT -ik "https://api.swisscom.com/voice/v1/voip/me/phoneNumbers/%USER_PHONE_NUMBER%/simrings" -d "[\"%PHONE_NUMMER%\"]"
```

* PATCH - Allows adding new phone numbers to the resource, which shall ring simultaneously.
```
curl -k -H "Authorization: Bearer %ACCESSTOKEN_GOES_HERE%" -H "Accept:application/json" -H "Content-Type:application/json" -X PATCH -ik "https://api.swisscom.com/voice/v1/voip/me/phoneNumbers/%USER_PHONE_NUMBER%/simrings" -d "[\"%PHONE_NUMMER%\"]"
```

* DELETE - Delete all simRing entries
```
curl -k -H "Authorization: Bearer %ACCESSTOKEN_GOES_HERE%" -H "Accept:application/json" -H "Content-Type:application/json" -X DELETE-ik "https://api.swisscom.com/voice/v1/voip/me/phoneNumbers/%USER_PHONE_NUMBER%/simrings"
```

### <a id='overview'>/voice/v1/voip/{id}/events/subscriptions </a>

* GET - Retrieve all subscriptions for requesting user.
```
curl -k -H "Authorization: Bearer %ACCESSTOKEN_GOES_HERE%" -H "Accept:application/json" -X GET -ik "https://api.swisscom.com/voice/v1/voip/me/events/subscriptions"
```

* POST - Create a new subscription.
```
curl -k -H 'Authorization: Bearer %ACCESSTOKEN_GOES_HERE%' -H 'Accept:application/json' -X POST -ik 'https://api.swisscom.com/voice/v1/voip/me/events/subscriptions' -d '{"eventType":"voip-call-log-change","callback":{"url":"http://www.swisscom.com/fcl","authorization":"Bearer ABC1"},"targets":[{"type":"phoneNumber","value":"%USER_PHONE_NUMBER%"}]}'
```

#### <a id='overview'>/voice/v1/voip/{id}/events/subscriptions/{subscriptionId} </a>
* GET - Retrieve a subscription by id.
```
curl -k -H "Authorization: Bearer %ACCESSTOKEN_GOES_HERE%" -H "Accept:application/json" -X GET -ik "https://api.swisscom.com/voice/v1/voip/me/events/subscriptions\ %SUBSCRIPTIONS_ID%"
```

* PUT - Edit a given subscription.
```
curl -k -H 'Authorization: Bearer %ACCESSTOKEN_GOES_HERE%' -H 'Accept:application/json' -X PUT -ik 'https://api.swisscom.com/voice/v1/voip/me/events/subscriptions/%SUBSCRIPTIONS_ID%' -d '{"eventType":"voip-call-log-change","callback":{"url":"http://www.swisscom.com/fcl","authorization":"Bearer ABC1"},"targets":[{"type":"phoneNumber","value":"%USER_PHONE_NUMBER%"}]}'
```

* DELETE - Delete event subscription.
```
curl -k -H "Authorization: Bearer %ACCESSTOKEN_GOES_HERE%" -H "Accept:application/json" -X DELETE -ik "https://api.swisscom.com/voice/v1/voip/me/events/subscriptions\ %SUBSCRIPTIONS_ID%"
```
