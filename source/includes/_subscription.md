#Subscription

##Subscription Object

```json
{
  "_id": "9d363669-c334-4307-8c62-5cf1fc49e28b",
  "idUser": "2280",
  "idOrg": "2",
  "name": "mysubscription",
  "pattern": {
    "type": "310",
    "org": "IBM"
  },
  "callback-http": {
    "method": "POST",
    "url": "https://www.callbackurl.com/xyz",
    "headers": [
      "articles"
    ]
  },
  "active": false,
  "createdAt": 1472649167365,
  "updatedAt": 1472649167365
}
```

In the event of a Sales Trigger, you can set up a subscription that will send information about the event to your web service. The subscription object includes the pattern that defines the conditions for the trigger as well as the callback information that defines the web service that Cognism will send the information to.



Parameter | Description
--------- | ----------- 
_id | **string** <br> Id of subscription.
name | **string** <br> Customer defined name of subscription.
active | **boolean** <br> Is the subscription active. Boolean value with options true or false.
created at | **integer** <br> UNIX number indicating the time the subscription was created.
updated at | **integer** <br> UNIX number indicating the time the subscription was last modified.


CALLBACK HTTP

Parameter | Description
--------- | ----------- 
method | **string** <br> Callback method such as POST.
url | **string** <br> Callback URL. Web service URL that Cognism will provide updates to based on chosen requirements.
headers | **string** <br> Headers required for the called web service.












##Get All Subscriptions
```ruby
api.subscription.all()
```

```python
sub = api.Subscription.all()
```

```shell
$ curl -v http://api.cognism.io/api/v1/subscription

  -H "X-API-AccessToken: your_access_token" 
  -H "X-API-SecretKey: your_secret_key"
```

```javascript

```

> **RESPONSE EXAMPLE**  


```json
[
  {
    "_id": "9d363669-c334-4307-8c62-5cf1fc49e28b",
    "idUser": "2280",
    "idOrg": "2",
    "name": "mysubscription",
    "pattern": {
      "type": "310",
      "org": "IBM"
    },
    "callback-http": {
      "method": "POST",
      "url": "https://www.callbackurl.com/xyz",
      "headers": [
        "articles"
      ]
    },
    "active": false,
    "createdAt": 1472649167365,
    "updatedAt": 1472649167365
  }
]
```

This API will list all subscriptions you have previously set up.


### HTTP Request

<aside class="tag">
<div class="lbl-get">GET</div>
</aside>

`http://api.cognism.io/api/v1/subscription`


### Query Parameters

Parameter | Description
--------- | ----------- 
X-API -AccessToken | **required** <br> Access Token
X-API-SecretKey | **required** <br> Secret Key












##Create Subscription

```ruby
api.subscription.create({ 
            name: 'mysubscriptionname',
            active: 'false',
            pattern:       {type: '310',
                              org: 'IBM'},
            callback-http: {method: 'POST',
                              url: 'myurl',
                              headers: ['title']}
            })
```

```python
api.Subscription.create({ 
            "name": "mysubscriptionname",
            "active": false,
            "pattern":       {"type": "310",
                              "org": "IBM"},
            "callback-http": {"method": "POST",
                              "url": "myurl",
                              "headers": ["title"]}
            })
```

```shell
  $ curl http://api.cognism.io/api/v1/subscription
  -H "X-API-AccessToken: your_access_token" 
  -H "X-API-SecretKey: your_secret_key" 
  -H "Content-type: application/json" 
  --request POST 
  --data '{ "name": "mysubscriptionname",
            "active": false,
            "pattern":       {"type": "310",
                              "org": "IBM"},
            "callback-http": {"method": "POST",
                              "url": "myurl",
                              "headers": ["title"]}}' 
```

> **RESPONSE EXAMPLE**  


```json
{
  "_id": "9d363669-c334-4307-8c62-5cf1fc49e28b",
  "idUser": "2280",
  "idOrg": "2",
  "name": "mysubsription",
  "pattern": {
    "type": "310",
    "org": "IBM"
  },
  "callback-http": {
    "method": "POST",
    "url": "https://www.callbackurl.com/xyz",
    "headers": [
      "articles"
    ]
  },
  "active": false,
  "createdAt": 1472649167365,
  "updatedAt": 1472649167365
}
```

This API allows you to create a subscription. In the event of a Sales Trigger, you can set up a subscription that will send information about the event to your web service. The conditions for triggering the web service call can be defined in the pattern. You will also need to define the callback parameters that describe the method for sending the HTTP call, your web service URL and any required headers.



### HTTP Request

<aside class="tag">
<div class="lbl-post">POST</div>
</aside>


`http://api.cognism.io/api/v1/subscription`


### Query Parameters

Parameter | Description
--------- | ----------- 
X-API -AccessToken | **required** <br> Access Token
X-API-SecretKey | **required** <br> Secret Key
name | **required** <br> Customer defined name of subscription.
active | **required** <br> Is the subscription active. Boolean value with options true or false.


CALLBACK HTTP

Parameter | Description
--------- | ----------- 
method | **required** <br> Callback method such as POST.
url | **required** <br> Callback URL. Web service URL that Cognism will provide updates to based on chosen requirements.
headers | **required** <br> Headers required for the called web service.









##Delete Subscription

```ruby
audit_hash = {
  action: "string",
  source: "string",
  data: 1
  }]
}

api.audit.create(audit_hash)
```

```python
audit_details = {
  action: "string",
  source: "string",
  data: 1
}

api.Audit.create(audit_details)
```

```shell
  $ curl http://api.cognism.io/api/v1/subscription
                              /your_subscription_id

  -H "X-API-AccessToken: your_access_token" 
  -H "X-API-SecretKey: your_secret_key" 
  --request DELETE 
```

> **RESPONSE EXAMPLE**  


```shell
no content
```

Delete any subscription that has been previously created. The id of the subscription is required for this action. If you are unsure what your id is, run "Get All Subscriptions" to see a list of your subscriptions.


### HTTP Request

<aside class="tag">
<div class="lbl-delete">DELETE</div>
</aside>


`http://api.cognism.io/api/v1/subscription/{subscription_id}`


### Query Parameters

Parameter | Description
--------- | ----------- 
id | **required** <br> Id of the subscription to be deleted.
X-API -AccessToken | **required** <br> Access Token
X-API-SecretKey | **required** <br> Secret Key










##Get Subscription

```ruby
api.subscription.find('your_subscription_id')
```

```python
subscription_id = "your_subscription_id"

sub = api.Subscription.find(subscription_id)
```

```shell
$ curl -v http://api.cognism.io/api/v1/subscription
                               /your_subscription_id

  -H "X-API-AccessToken: your_access_token" 
  -H "X-API-SecretKey: your_secret_key"
```

```javascript

```

> **RESPONSE EXAMPLE**  


```json
{
  "_id": "3ea44571-9358-4604-addf-0d43b61e22a3",
  "idUser": "2280",
  "idOrg": "2",
  "name": "mysubscription",
  "pattern": {
    "type": "310",
    "org": "IBM"
  },
  "callback-http": {
    "method": "POST",
    "url": "https://www.callbackurl.com/xyz",
    "headers": [
      "articles"
    ]
  },
  "active": false,
  "createdAt": 1472649847431,
  "updatedAt": 1472649847431
}
```

This API returns details of a specific subscription. The id of the subscription is required. To find a list of all subscriptions, see "Get All Subscriptions".


### HTTP Request

<aside class="tag">
<div class="lbl-get">GET</div>
</aside>


`http://api.cognism.io/api/v1/subscription/{subscription_id}`


### Query Parameters

Parameter | Description
--------- | ----------- 
id | **required** <br> Id of the subscription.
X-API -AccessToken | **required** <br> Access Token
X-API-SecretKey | **required** <br> Secret Key







##Modify Subscription
```ruby
audit_hash = {
  action: "string",
  source: "string",
  data: 1
  }]
}

api.audit.create(audit_hash)
```

```python
audit_details = {
  action: "string",
  source: "string",
  data: 1
}

api.Audit.create(audit_details)
```

```shell
$ curl http://api.cognism.io/api/v1/subscription
                            /your_subscription_id

-H "X-API-AccessToken: your_access_token" 
-H "X-API-SecretKey: your_secret_key" 
-H "Content-type: application/json" 
--request PUT 
--data  '{"name": "mymodifiedname",
          "active": false,
          "pattern":       {"type": "310",
                            "org": "IBM"},
          "callback-http": {"method": "POST",
                            "url": "http://myurl.com",
                            "headers": ["best title"]}}' 
```

> **RESPONSE EXAMPLE**  


```shell
no content
```

This API allows you to modify any pre-existing subscription. The id of the subscription is required. To find a list of all subscriptions, see "Get All Subscriptions".


### HTTP Request

<aside class="tag">
<div class="lbl-put">PUT</div>
</aside>


`http://api.cognism.io/api/v1/subscription/{subscription_id}`


### Query Parameters

Parameter | Description
--------- | ----------- 
X-API -AccessToken | **required** <br> Access Token
X-API-SecretKey | **required** <br> Secret Key
name | **required** <br> Customer defined name of subscription.
active | **required** <br> Is the subscription active. Boolean value with options true or false.


CALLBACK HTTP

Parameter | Description
--------- | ----------- 
method | **required** <br> Callback method such as POST.
url | **required** <br> Callback URL. Web service URL that Cognism will provide updates to based on chosen requirements.
headers | **required** <br> Headers required for the called web service.
