#Websocket

In the event of a Sales Trigger or a News Item, you can set up a websocket trigger that will send information about the event to your system. As for the subscription object, websockets require a pattern that defines the conditions for the trigger.



##Join Websocket 
```ruby
api.websocket.all('your_access_token',
                'your_secret_key',
                '{pattern}')
```

```python
accessToken = "your_access_token"
secretKey = "your_secret_key"
pattern = "{pattern}" 

websocket = api.Websocket.all(accessToken,
                              secretKey,
                              pattern)
```

```shell
$ curl -v 'http://api.cognism.io/api/v1/websocket?
                accessToken=your_access_token& 
                secretKey=your_secret_key&
                pattern={pattern}'

  -H "X-API-AccessToken: your_access_token" 
  -H "X-API-SecretKey: your_secret_key"
```

```javascript
url = "http://api.cognism.io/api/v1/websocket?
                accessToken=your_access_token& 
                secretKey=your_secret_key&
                pattern={pattern}";

xmlHttp.open( "GET", url );
xmlHttp.setRequestHeader('X-API-AccessToken','your_access_token');
xmlHttp.setRequestHeader('X-API-SecretKey','your_secret_key');
```

This API allows you to create a websocket trigger, which, in the event of a Sales Trigger, will send information about the event to your system. The conditions for the trigger can be defined in the pattern. The authentication tokens are required for the X-API headers, while they can also be added into the GET URL.


### HTTP Request

<aside class="tag">
<div class="lbl-get">GET</div>
</aside>

`http://api.cognism.io/api/v1/websocket?accessToken={access_token}&secretKey={secret_key}&pattern={pattern}`


### Query Parameters

Parameter | Description
--------- | ----------- | -----------
accessToken | **optional** <br> Access Token
secretKey | **optional** <br> Secret Key
pattern | **optional** <br> Search pattern
X-API -AccessToken | **required** <br> Access Token
X-API-SecretKey | **required** <br> Secret Key







##Push Data Via Websocket

```ruby
api.websocket.create({session})
```

```python
api.Websocket.create({session})
```

```shell
$ curl -v http://api.cognism.io/api/v1/websocket/session?
          session={session}
```

```javascript
url = "http://api.cognism.io/api/v1/websocket/session?
          session={session}";

xmlHttp.open( "POST", url );
```


This API allows you to push data through the websocket. The session id for the websocket connection is required.


### HTTP Request

<aside class="tag">
<div class="lbl-post">POST</div>
</aside>

`http://api.cognism.io/api/v1/websocket/session?session={session}`


### Query Parameters

Parameter | Description
--------- | ----------- | -----------
session | **optional** <br> Websocket session id.