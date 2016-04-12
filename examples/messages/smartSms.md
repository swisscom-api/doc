## <a id='overview'>Curl Examples</a> 

<p class="note">
 <strong>Note: API Documentation</strong>
 <ul>
 <li><a href="https://rawgit.com/wiki/swisscom-api/doc/API_docs/messaging/messaging_sms_v1.html" target="_blank">Messaging SMS</a> </li>
 <li><a href="https://rawgit.com/wiki/swisscom-api/doc/API_docs/messaging/messaging_tokenvalidation_v1.html" target="_blank">Messaging Token Validation</a></li>
 </ul>
</p>

### <a id='overview'>SMS</a>

* Send SMS (POST)
```
curl -ik -H "Content-Type: application/json" -H "client_id:%YOUR_CLIENT_ID%" -X POST "https://api.swisscom.com/messaging/v1/sms" -d "{\"to\": \"+417xxxxxxxx\", \"text\": \"hello world\"}"
```

### <a id='overview'>TOKEN VALIDATION</a> 

* Send Token (POST)
```
curl -ik -H "Content-Type: application/json" -H "client_id:%YOUR_CLIENT_ID%" -X POST " https://api.swisscom.com/messaging/v1/sms/tokenvalidation" -d "{\"to\":\"+417xxxxxxxx\",\"text\":\"Take this token: %TOKEN%\", \"tokenType\":\"SHORT_NUMERIC\",\"expireTime\":120,\"tokenLength\":6}"
```

* Validate Token (GET)
```
curl -ik -H "Accept: application/json" -H "client_id:%YOUR_CLIENT_ID%" -X GET " https://api.swisscom.com/messaging/v1/sms/tokenvalidation/00417xxxxxxxx/%RECEIVED_TOKEN_GOES_HERE%"
```