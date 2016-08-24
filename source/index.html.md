---
title: Cognism API

language_tabs:
  - shell
  - ruby
  - python
  - javascript

toc_footers:
  - <a href='http://www.cognism.com/Account/Register' style="font-size:13px;">Sign Up</a>
  - <a href='https://github.com/tripit/slate'>Documentation Powered by Slate</a>

includes:
  - errors

search: true
---

# Introduction

The Cognism API is used to submit lead generation, lead enrichment and sales management requests. The API is built using RESTful endpoints and standard HTTP verbs.

We have language bindings in Shell, Ruby, and Python! You can view code examples in the dark area to the right, and you can switch the programming language of the examples with the tabs in the top right.


# Authentication

> To authorize, use this code:

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
```

```shell
# With shell, you can just pass the correct header with each request
curl "api_endpoint_here"
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
```

> Make sure to replace `meowmeowmeow` with your API key.

Cognism uses token keys for authentification. How to get the key? Do we need it for all API requests? Example of what it looks like.

Also, security key, what is that?

Kittn uses API keys to allow access to the API. You can register a new Kittn API key at our [developer portal](http://example.com/developers).

Kittn expects for the API key to be included in all API requests to the server in a header that looks like the following:

`Authorization: meowmeowmeow`

<aside class="notice">
You must replace <code>meowmeowmeow</code> with your personal API key.
</aside>


# Audit

## Audit User


```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.get
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.get()
```

```shell
curl "http://example.com/api/kittens"
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let kittens = api.kittens.get();
```

> **RESPONSE EXAMPLE**  


```json
[
  {
    "date": "Tue, 23 Aug 2016 14:18:36 GMT",
    "content-encoding": "gzip",
    "x-content-type-options": "nosniff",
    "x-permitted-cross-domain-policies": "master-only",
    "x-frame-options": "DENY",
    "request-time": "178ms",
    "vary": "Accept-Encoding",
    "content-length": "20",
    "x-xss-protection": "1; mode=block",
    "content-type": null
  }
]
```

An audit user is...what is an audit user? How to become one? Any other info on audit user? 

This endpoint retrieves all audit users??


### HTTP Request

<aside class="success">
GET
</aside>

`http://api.cognism.io/api/v1/audit/user?accessToken={accessToken}`


### Query Parameters

Parameter | Description
--------- | ----------- | -----------
accessToken | **string** <br> Access Token
secretKey | **string** <br> Secret Key
body | **JSON** <br> How to put in JSON? Payload??


## Get a Specific Kitten

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.get(2)
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.get(2)
```

```shell
curl "http://api.cognism.io/api/v1/audit/user?accessToken=1030303-123123-123123"
  -H "Authorization: Your API Token"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let max = api.kittens.get(2);
```

> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "name": "Max",
  "breed": "unknown",
  "fluffiness": 5,
  "cuteness": 10
}
```

This endpoint retrieves a specific kitten.

<aside class="warning">Inside HTML code blocks like this one, you can't use Markdown, so use <code>&lt;code&gt;</code> blocks to denote code.</aside>

<aside class="success">
Remember — a happy kitten is an authenticated kitten!
</aside>

### HTTP Request

`GET http://example.com/kittens/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the kitten to retrieve


#Company

##Get By Name

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.get
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.get()
```

```shell
curl "http://example.com/api/kittens"
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let kittens = api.kittens.get();
```

> **RESPONSE EXAMPLE**  


```json
[
  {
    "date": "Tue, 23 Aug 2016 14:18:36 GMT",
    "content-encoding": "gzip",
    "x-content-type-options": "nosniff",
    "x-permitted-cross-domain-policies": "master-only",
    "x-frame-options": "DENY",
    "request-time": "178ms",
    "vary": "Accept-Encoding",
    "content-length": "20",
    "x-xss-protection": "1; mode=block",
    "content-type": null
  }
]
```

An audit user is...what is an audit user? How to become one? Any other info on audit user? 

This endpoint retrieves all audit users??


### HTTP Request

<aside class="success">
GET
</aside>

`http://api.cognism.io/api/v1/audit/user?accessToken={accessToken}`


### Query Parameters

Parameter | Description
--------- | ----------- | -----------
accessToken | **string** <br> Access Token
secretKey | **string** <br> Secret Key
body | **JSON** <br> How to put in JSON? Payload??


#DeadLetter

##Get DeadLetter Events

##Receive DeadLetter Event


#Documents

##Search Documents (JSON)
##Search Documents By Aboutness ??
##Search Documents (TXT)
##Search Documents By DIFF


#Events

##Get Event Stream
##Get Event Stream as CSV File
##Search Event Stream


#Person

##Get By Name


#Subscription

##Get Subsrciptions
##Create Subscription
##Delete Subscription
##Get Subscriptions ?? too similar to before
##Create Subscription


#Websocket

##Join Websocket
##Push Data Via Websocket