## <a id='overview'>Voice VoIP Curl Examples</a> 

### <a id='overview'>SMS</a>
<h3>List calls</h3>
<code>
curl -k -H "Authorization: Bearer %ACCESSTOKEN_GOES_HERE%" https://api.swisscom.com/voice/v1/voip/me/phoneNumbers/123/calls
</code>

<h3>Initiate a call</h3>
<code>
curl -X POST -k -H "Authorization: Bearer %ACCESSTOKEN_GOES_HERE%" https://api.swisscom.com/voice/v1/voip/me/phoneNumbers/123/calls
</code>

<h3>List phonebook entries</h3>
<code>
curl -k -H "Authorization: Bearer %ACCESSTOKEN_GOES_HERE%" https://api.swisscom.com/voice/v1/voip/me/phoneNumbers/123/phonebooks
</code>

<h3>List VoIP group numbers</h3>
<code>
curl -k -H "Authorization: Bearer %ACCESSTOKEN_GOES_HERE%" https://api.swisscom.com/voice/v1/voip/me/numbers
</code>

<h3>VoIP call forwardings</h3>
<h3>GET</h3>
<code>
curl -k -H "Authorization: Bearer %ACCESSTOKEN_GOES_HERE%" -H "Accept:application/json" -X GET -ik "https://api.swisscom.com/voice/v1/voip/me/phoneNumbers/%USER_PHONE_NUMBER%/forwardings"
</code>

<h3>PUT</h3>
<code>
curl -k -H "Authorization: Bearer %ACCESSTOKEN_GOES_HERE%" -H "Accept:application/json" -H "Content-Type:application/json" -X GET -ik "https://api.swisscom.com/voice/v1/voip/me/phoneNumbers/%USER_PHONE_NUMBER%/forwardings/busy"  -d "{\"active\": true, \"target\": \"0795481252\"}"
</code>

<h3>VoIP Simultaneous rings </h3>
<h3>GET</h3>
<code>
curl -k -H "Authorization: Bearer %ACCESSTOKEN_GOES_HERE%" -H "Accept:application/json" -H "Content-Type:application/json" -X GET -ik "https://api.swisscom.com/voice/v1/voip/me/phoneNumbers/%USER_PHONE_NUMBER%/simrings"
</code>

<h3>PUT</h3>
<code>
curl -k -H "Authorization: Bearer %ACCESSTOKEN_GOES_HERE%" -H "Accept:application/json" -H "Content-Type:application/json" -X PUT -ik "https://api.swisscom.com/voice/v1/voip/me/phoneNumbers/%USER_PHONE_NUMBER%/simrings" -d "[\"%PHONE_NUMMER%\"]"
</code>

<h3>PATCH</h3>
<code>
curl -k -H "Authorization: Bearer %ACCESSTOKEN_GOES_HERE%" -H "Accept:application/json" -H "Content-Type:application/json" -X PATCH -ik "https://api.swisscom.com/voice/v1/voip/me/phoneNumbers/%USER_PHONE_NUMBER%/simrings" -d "[\"%PHONE_NUMMER%\"]"
</code>

<h3>DELETE</h3>
<code>
curl -k -H "Authorization: Bearer %ACCESSTOKEN_GOES_HERE%" -H "Accept:application/json" -H "Content-Type:application/json" -X DELETE-ik "https://api.swisscom.com/voice/v1/voip/me/phoneNumbers/%USER_PHONE_NUMBER%/simrings"
</code>

<h3>VoIP events subscriptions</h3>
<h3>GET</h3>
<code>
curl -k -H "Authorization: Bearer %ACCESSTOKEN_GOES_HERE%" -H "Accept:application/json" -X GET -ik "https://api.swisscom.com/voice/v1/voip/me/events/subscriptions"
</code>

<h3>POST</h3>
<code>
curl -k -H 'Authorization: Bearer %ACCESSTOKEN_GOES_HERE%' -H 'Accept:application/json' -X POST -ik 'https://api.swisscom.com/voice/v1/voip/me/events/subscriptions' -d '{"eventType":"voip-call-log-change","callback":{"url":"http://www.swisscom.com/fcl","authorization":"Bearer ABC1"},"targets":[{"type":"phoneNumber","value":"%USER_PHONE_NUMBER%"}]}'
</code>

<h3>GET /{subscriptionId}</h3>
<code>
curl -k -H "Authorization: Bearer %ACCESSTOKEN_GOES_HERE%" -H "Accept:application/json" -X GET -ik "https://api.swisscom.com/voice/v1/voip/me/events/subscriptions\ %SUBSCRIPTIONS_ID%"
</code>

<h3>PUT /{subscriptionId}</h3>
<code>
curl -k -H 'Authorization: Bearer %ACCESSTOKEN_GOES_HERE%' -H 'Accept:application/json' -X PUT -ik 'https://api.swisscom.com/voice/v1/voip/me/events/subscriptions/%SUBSCRIPTIONS_ID%' -d '{"eventType":"voip-call-log-change","callback":{"url":"http://www.swisscom.com/fcl","authorization":"Bearer ABC1"},"targets":[{"type":"phoneNumber","value":"%USER_PHONE_NUMBER%"}]}'
</code>

<h3>DELETE /{subscriptionId}</h3>
<code>
curl -k -H "Authorization: Bearer %ACCESSTOKEN_GOES_HERE%" -H "Accept:application/json" -X DELETE -ik "https://api.swisscom.com/voice/v1/voip/me/events/subscriptions\ %SUBSCRIPTIONS_ID%"
</code>