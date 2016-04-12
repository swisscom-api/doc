## <a id='overview'>Curl Examples</a> 

### <a id='overview'>SMS</a>

1. Send SMS (POST)
```
curl -ik -H "Content-Type: application/json" -H "client_id:%YOUR_CLIENT_ID%" -X POST "https://api.swisscom.com/messaging/v1/sms" -d "{\"to\": \"+417xxxxxxxx\", \"text\": \"hello world\"}"
```

### <a id='overview'>TOKEN VALIDATION</a> 

1. Send Token (POST)
```
curl -ik -H "Content-Type: application/json" -H "client_id:%YOUR_CLIENT_ID%" -X POST " https://api.swisscom.com/messaging/v1/sms/tokenvalidation" -d "{\"to\":\"+417xxxxxxxx\",\"text\":\"Take this token: %TOKEN%\", \"tokenType\":\"SHORT_NUMERIC\",\"expireTime\":120,\"tokenLength\":6}"
```

2. Validate Token (GET)
```
curl -ik -H "Accept: application/json" -H "client_id:%YOUR_CLIENT_ID%" -X GET " https://api.swisscom.com/messaging/v1/sms/tokenvalidation/00417xxxxxxxx/%RECEIVED_TOKEN_GOES_HERE%"
```