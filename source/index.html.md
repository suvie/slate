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

Difference between AccessToken, SecretKey, X-API-AccessToken and X-API-SecretKey

Also, security key, what is that?

Kittn uses API keys to allow access to the API. You can register a new Kittn API key at our [developer portal](http://example.com/developers).

Kittn expects for the API key to be included in all API requests to the server in a header that looks like the following:

`Authorization: meowmeowmeow`

<aside class="notice">
You must replace <code>0000-0000-0000</code> with your personal API key.
</aside>










# Audit

##Audit User Object

```json
Whatever the object looks like:
[
  {
    "firt_name": "Michael",
    "last_name": "Zane",
    "email": "michaelz@email.com"
  }
]
```

What is this object used for? Below example of output:

Parameter | Description
--------- | ----------- | -----------
first_name | **string** <br> First name of audit user.
last_name | **string** <br> Last name of audit user.
address | **string** <br> Address for audit user.

## Get Audit User?


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

  $ curl http://api.cognism.io/api/v1/audit/user?accessToken=0000-0000-0000 \
  -d 'action=String' \
  -d 'source=String' \
  -d 'data=1' \
```

```javascript
const audit = require('kittn');

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
POST
</aside>

`http://api.cognism.io/api/v1/audit/user?accessToken={access_token}`


### Query Parameters

Parameter | Description
--------- | ----------- | -----------
accessToken | **required** <br> Access Token
secretKey | **optional** <br> Secret Key
action | **required** <br> what is action?
source | **required** <br> what is source?
data | **required** <br> {optional} what is data? 


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
curl "http://api.cognism.io/api/v1/audit/user?accessToken=0000-0000-0000"
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

##Company Object

```json
Whatever the object looks like:
[
  {
    "firt_name": "Michael",
    "last_name": "Zane",
    "email": "michaelz@email.com"
  }
]
```

What is this object used for? Below example of output:

Parameter | Description
--------- | ----------- | -----------
first_name | **string** <br> First name of audit user.
last_name | **string** <br> Last name of audit user.
address | **string** <br> Address for audit user.

##Get By Name

```ruby
require 'Company'

api = Company::APIClient.authorize!('0000-0000-0000')
api.company.find('cognism')
```

```python
import comp

api = comp.authorize('0000-0000-0000')
api.Company.find('cognism')
```

```shell
$ curl http://api.cognism.io/api/v1/company/cognism \
  -H "Authorization: Access Token"
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

This API lets you access information for a specific company....what comapny? How to get list/access? Any other info on company? 

This endpoint retrieves what info from company??


### HTTP Request

<aside class="success">
GET
</aside>

`http://api.cognism.io/api/v1/company/{name}`


### Query Parameters

Parameter | Description
--------- | ----------- | -----------
name | **required** <br> Company name
X-API-AccessToken | **required** <br> Access Token
X-API-AccessToken | **optional** <br> Secret Key













#DeadLetter

##DeadLetter Object

```json
[
  {
    "_id": "2f9d283f-86cc-46b1-8d38-2866d4466888",
    "employee": {
      "name": "Laszlo Szabo",
      "title": "Digital Media Consultant and Online Marketing Expert",
      "url": "https://hu.linkedin.com/in/laszabo",
      "country": "United States",
      "organisation": "Russmedia Digital Limited",
      "state": "Hungary area",
      "age": 26
    },
    "source": "social",
    "meta": {
      "datecreated": "2016-04-12T12:31:58.886156"
    },
    "type": "job-leave",
    "at": 1460464400387
  }
]
```

What is this object used for? Below example of output:

Parameter | Description
--------- | ----------- | -----------
source | **string** <br> ???
type | **string** <br> ???

###EMPLOYEE

Parameter | Description
--------- | ----------- | -----------
name | **string** <br> Name of employee.
title | **string** <br> Job title of emplyee.
url | **string** <br> Emplyee's LinkdIn profile? Or URL where found?
country | **string** <br> Country of residence of employee.
organisation | **string** <br> Organisation worked at by employee.
state | **string** <br> State of residence of employee.
age | **integer** <br> Age of employee.


##Get DeadLetter Events

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
    "_id": "2f9d283f-86cc-46b1-8d38-2866d4466888",
    "employee": {
      "name": "Laszlo Szabo",
      "title": "Digital Media Consultant and Online Marketing Expert",
      "url": "https://hu.linkedin.com/in/laszabo",
      "country": "United States",
      "organisation": "Russmedia Digital Limited",
      "state": "Hungary area",
      "age": 26
    },
    "source": "social",
    "meta": {
      "datecreated": "2016-04-12T12:31:58.886156"
    },
    "type": "job-leave",
    "at": 1460464400387
  },
  {
    "_id": "b07fe290-5fa6-430c-bfe5-4153f95df1d4",
    "employee": {
      "city": "Harrisburg",
      "name": "Carly Anne Amos",
      "title": "Sales and Marketing Intern",
      "url": "https://www.linkedin.com/in/carly-anne-amos-70115593",
      "country": "United States",
      "organisation": "Hamptons Magazine",
      "state": "Pennsylvania"
    },
    "source": "social",
    "meta": {
      "datecreated": "2016-04-12T12:40:13.439424"
    },
    "type": "job-join",
    "at": 1460464894973
  }
]
```

What is a deadletter? This API gets information about people, as many people as the amount you specify for size...what people are these and where are they from? 

This endpoint retrieves information about the employee, their name, location and position. It will also explain the source of the information.


### HTTP Request

<aside class="success">
GET
</aside>

`http://api.cognism.io/api/v1/events/deadletter?page={page}&size={size}`


### Query Parameters

Parameter | Description
--------- | ----------- | -----------
page | **optional** <br> What is this page??
size | **optional** <br> The number of "people" to retrieve



##Receive DeadLetter Event

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

  $ curl http://api.cognism.io/api/v1/audit/user?accessToken=0000-0000-0000 \
  -d 'action=String' \
  -d 'source=String' \
  -d 'data=1' \
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
    "date": "Wed, 24 Aug 2016 08:14:32 GMT",
    "content-encoding": "gzip",
    "x-content-type-options": "nosniff",
    "x-permitted-cross-domain-policies": "master-only",
    "x-frame-options": "DENY",
    "request-time": "5ms",
    "vary": "Accept-Encoding",
    "content-length": "20",
    "x-xss-protection": "1; mode=block",
    "content-type": null
  }
]
```

What is a deadletter? This API gets information about people, as many people as the amount you specify for size...what people are these and where are they from? 

This endpoint retrieves information about ... I'm guessing one person?


### HTTP Request

<aside class="success">
POST
</aside>

`http://api.cognism.io/api/v1/events/deadletter`


### Query Parameters

Parameter | Description
--------- | ----------- | -----------
no idea | **required** <br> What are the inputs?












#Documents

##Document Object

```json
Whatever the object looks like:
[
  {
    "firt_name": "Michael",
    "last_name": "Zane",
    "email": "michaelz@email.com"
  }
]
```

What is this object used for? Below example of output:

Parameter | Description
--------- | ----------- | -----------
first_name | **string** <br> First name of audit user.
last_name | **string** <br> Last name of audit user.
address | **string** <br> Address for audit user.

##Search Documents (JSON)

```ruby
require 'Company'

api = Company::APIClient.authorize!('0000-0000-0000')
api.company.find('cognism')
```

```python
import comp

api = comp.authorize('0000-0000-0000')
api.Company.find('cognism')
```

```shell
$ curl http://api.cognism.io/api/v1/company/cognism \
  -H "Authorization: Access Token"
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

What documents? Who can access what? Any other info on docs? 

This endpoint retrieves what information in the docs??


### HTTP Request

<aside class="success">
GET
</aside>

`http://api.cognism.io/api/v1/documents/json?source={source}&accessToken={access_token}`


### Query Parameters

Parameter | Description
--------- | ----------- | -----------
keywords | **optional** <br> Keyword(s) (i.e. appoints.chief marketing officer,named.chief marketing officer)
fields | **optional** <br> Search field(s) (i.e. articleName,subHeadline,abstract)
exclusions | **optional** <br> Exclusion(s) (i.e. retirement,leaving)
outputFields | **optional** <br> Output field(s) (i.e. headline,url,abstract)
source | **required** <br> Document source(s)
dateFrom | **optional** <br> dd.MM.yyyy
dateTo | **optional** <br> dd.MM.yyyy
annotation | **optional** <br> Annotation (i.e. subject=PER)
accessToken | **required** <br> Access Token
secretKey | **optional** <br> Secret Key

##Search Documents By Aboutness ??


```ruby
require 'Company'

api = Company::APIClient.authorize!('0000-0000-0000')
api.company.find('cognism')
```

```python
import comp

api = comp.authorize('0000-0000-0000')
api.Company.find('cognism')
```

```shell
$ curl http://api.cognism.io/api/v1/company/cognism \
  -H "Authorization: Access Token"
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

What documents? Who can access what? Any other info on docs? 

This endpoint retrieves what information in the docs??


### HTTP Request

<aside class="success">
GET
</aside>

`http://api.cognism.io/api/v1/documents/org/{org}?dateFrom={date_from}&dateTo={date_to}&aboutness={aboutness}&page=1&count={count}&accessToken={access_token}`


### Query Parameters

Parameter | Description
--------- | ----------- | -----------
org | **optional** <br> Organization Name
dateFrom | **optional** <br> Date From: dd.MM.yyyy
dateTo | **optional** <br> Date To: dd.MM.yyyy
source | **optional** <br> Source
aboutness | **required** <br> Minimum Aboutness Score
page | **optional** <br> Page
count | **optional** <br> Page Size
accessToken | **required** <br> Access Token
secretKey | **optional** <br> Secret Key


##Search Documents (TXT)


```ruby
require 'Company'

api = Company::APIClient.authorize!('0000-0000-0000')
api.company.find('cognism')
```

```python
import comp

api = comp.authorize('0000-0000-0000')
api.Company.find('cognism')
```

```shell
$ curl http://api.cognism.io/api/v1/company/cognism \
  -H "Authorization: Access Token"
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

What documents? Who can access what? Any other info on docs? 

This endpoint retrieves what information in the docs??


### HTTP Request

<aside class="success">
GET
</aside>

`http://api.cognism.io/api/v1/documents/txt?source={source}&accessToken={access_token}`


### Query Parameters

Parameter | Description
--------- | ----------- | -----------
keywords | **optional** <br> Keyword(s) (i.e. appoints.chief marketing officer,named.chief marketing officer)
fields | **optional** <br> Search field(s) (i.e. articleName,subHeadline,abstract)
exclusions | **optional** <br> Exclusion(s) (i.e. retirement,leaving)
source | **required** <br> Document source(s)
dateFrom | **optional** <br> dd.MM.yyyy
dateTo | **optional** <br> dd.MM.yyyy
annotation | **optional** <br> Annotation (i.e. subject=PER)
accessToken | **required** <br> Access Token
secretKey | **optional** <br> Secret Key



##Search Documents By DIFF

```ruby
require 'Company'

api = Company::APIClient.authorize!('0000-0000-0000')
api.company.find('cognism')
```

```python
import comp

api = comp.authorize('0000-0000-0000')
api.Company.find('cognism')
```

```shell
$ curl http://api.cognism.io/api/v1/company/cognism \
  -H "Authorization: Access Token"
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

What documents? Who can access what? Any other info on docs? 

This endpoint retrieves what information in the docs??


### HTTP Request

<aside class="success">
GET
</aside>

`http://api.cognism.io/api/v1/documents/txt/diff?source={source}&accessToken={access_token}`


### Query Parameters

Parameter | Description
--------- | ----------- | -----------
keywords1 | **optional** <br> Keyword(s) #1 (i.e. appoints.chief marketing officer,named.chief marketing officer)
keywords2 | **optional** <br> Keyword(s) #2 (i.e. chief marketing officer)
fields1 | **optional** <br> Search field(s) (i.e. articleName,subHeadline,abstract)
fields2 | **optional** <br> Search field(s) (i.e. articleName,subHeadline,abstract)
source | **required** <br> Document source(s)
dateFrom | **optional** <br> dd.MM.yyyy
dateTo | **optional** <br> dd.MM.yyyy
annotation | **optional** <br> Annotation (i.e. subject=PER)
accessToken | **required** <br> Access Token
secretKey | **optional** <br> Secret Key





















#Events

##Event Object

```json
Whatever the object looks like:
[
  {
    "firt_name": "Michael",
    "last_name": "Zane",
    "email": "michaelz@email.com"
  }
]
```

What is this object used for? Below example of output:

Parameter | Description
--------- | ----------- | -----------
first_name | **string** <br> First name of audit user.
last_name | **string** <br> Last name of audit user.
address | **string** <br> Address for audit user.






##Get Event Stream

```ruby
require 'Company'

api = Company::APIClient.authorize!('0000-0000-0000')
api.company.find('cognism')
```

```python
import comp

api = comp.authorize('0000-0000-0000')
api.Company.find('cognism')
```

```shell
$ curl http://api.cognism.io/api/v1/company/cognism \
  -H "Authorization: Access Token"
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

What documents? Who can access what? Any other info on docs? 

This endpoint retrieves what information in the docs??


### HTTP Request

<aside class="success">
GET
</aside>

`http://api.cognism.io/api/v1/events/stream?enrich={true/false}`


### Query Parameters

Parameter | Description
--------- | ----------- | -----------
dateFrom | **optional** <br> dd.MM.yyyy
dateTo | **optional** <br> dd.MM.yyyy
rule | **optional** <br> Query rule (e.g. type=job-join|job-leave;org=IBM;employee.title=valuelist(mediaradar-jobtitle) ).
page | **optional** <br> From index to start the search from. Defaults to 0.
count | **optional** <br> The number of search hits to return. Defaults to 50.
enrich | **optional** <br> Enrich events with custom data. Choose either true or false. The default value is true.
X-API-AccessToken | **required** <br> Access Token
X_API-SecretKey | **optional** <br> Secret Key






##Get Event Stream as CSV File

```ruby
require 'Company'

api = Company::APIClient.authorize!('0000-0000-0000')
api.company.find('cognism')
```

```python
import comp

api = comp.authorize('0000-0000-0000')
api.Company.find('cognism')
```

```shell
$ curl http://api.cognism.io/api/v1/company/cognism \
  -H "Authorization: Access Token"
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

What documents? Who can access what? Any other info on docs? 

This endpoint retrieves what information in the docs??


### HTTP Request

<aside class="success">
GET
</aside>

`http://api.cognism.io/api/v1/events/stream/csv?count={count}&accessToken={access_token}&enrich={true/false}`


### Query Parameters

Parameter | Description
--------- | ----------- | -----------
dateFrom | **optional** <br> dd.MM.yyyy
dateTo | **optional** <br> dd.MM.yyyy
rule | **optional** <br> Query rule (e.g. type=job-join|job-leave;org=IBM;employee.title=valuelist(mediaradar-jobtitle) ).
page | **optional** <br> From index to start the search from. Defaults to 0.
count | **optional** <br> The number of search hits to return. Defaults to 50.
enrich | **optional** <br> Enrich events with custom data. Choose either true or false. The default value is true.
accessToken | **required** <br> Access Token
secretKey | **optional** <br> Secret Key





##Search Event Stream


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

  $ curl http://api.cognism.io/api/v1/audit/user?accessToken=0000-0000-0000 \
  -d 'action=String' \
  -d 'source=String' \
  -d 'data=1' \
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

What documents? Who can access what? Any other info on docs? 

This endpoint retrieves what information in the docs??


### HTTP Request

<aside class="success">
POST
</aside>

`http://api.cognism.io/api/v1/events/stream/search?accessToken={access_token}`


### Query Parameters

Parameter | Description
--------- | ----------- | -----------
accessToken | **required** <br> Access Token
secretKey | **optional** <br> Secret Key
dateFrom | **optional** <br> dd.MM.yyyy
dateTo | **optional** <br> dd.MM.yyyy
page | **required** <br> From index to start the search from. Defaults to 0.
count | **required** <br> The number of search hits to return. Defaults to 50.
name | **required** <br> ??
operator | **required** <br> ??
values | **required** <br> ??
phase | **required** <br> ??





















#Person

##Person Object

```json
Whatever the object looks like:
[
  {
    "firt_name": "Michael",
    "last_name": "Zane",
    "email": "michaelz@email.com"
  }
]
```

What is this object used for? Below example of output:

Parameter | Description
--------- | ----------- | -----------
first_name | **string** <br> First name of audit user.
last_name | **string** <br> Last name of audit user.
address | **string** <br> Address for audit user.






##Get By Name

```ruby
require 'Company'

api = Company::APIClient.authorize!('0000-0000-0000')
api.company.find('cognism')
```

```python
import comp

api = comp.authorize('0000-0000-0000')
api.Company.find('cognism')
```

```shell
$ curl http://api.cognism.io/api/v1/company/cognism \
  -H "Authorization: Access Token"
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

What documents? Who can access what? Any other info on docs? 

This endpoint retrieves what information in the docs??


### HTTP Request

<aside class="success">
GET
</aside>

`http://api.cognism.io/api/v1/person`


### Query Parameters

Parameter | Description
--------- | ----------- | -----------
firstName | **optional** <br> Person's first name.
lastName | **optional** <br> Person's last name.
company | **optional** <br> The company the person works in.
X-API -AccessToken | **required** <br> Access Token
X-API-SecretKey | **optional** <br> Secret Key















#Subscription

##Subscription Object

```json
Whatever the object looks like:
[
  {
    "firt_name": "Michael",
    "last_name": "Zane",
    "email": "michaelz@email.com"
  }
]
```

What is this object used for? Below example of output:

Parameter | Description
--------- | ----------- | -----------
first_name | **string** <br> First name of audit user.
last_name | **string** <br> Last name of audit user.
address | **string** <br> Address for audit user.

##Get Subsrciptions
##Create Subscription
##Delete Subscription
##Get Subscriptions ?? too similar to before
##Create Subscription


















#Websocket

##Websocket Object

```json
Whatever the object looks like:
[
  {
    "firt_name": "Michael",
    "last_name": "Zane",
    "email": "michaelz@email.com"
  }
]
```

What is this object used for? Below example of output:

Parameter | Description
--------- | ----------- | -----------
first_name | **string** <br> First name of audit user.
last_name | **string** <br> Last name of audit user.
address | **string** <br> Address for audit user.






##Join Websocket
```ruby
require 'Company'

api = Company::APIClient.authorize!('0000-0000-0000')
api.company.find('cognism')
```

```python
import comp

api = comp.authorize('0000-0000-0000')
api.Company.find('cognism')
```

```shell
$ curl http://api.cognism.io/api/v1/company/cognism \
  -H "Authorization: Access Token"
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

What documents? Who can access what? Any other info on docs? 

This endpoint retrieves what information in the docs??


### HTTP Request

<aside class="success">
GET
</aside>

`http://api.cognism.io/api/v1/websocket`


### Query Parameters

Parameter | Description
--------- | ----------- | -----------
accessToken | **optional** <br> Access Token
secretKey | **optional** <br> Secret Key
pattern | **optional** <br> ??
X-API -AccessToken | **required** <br> Access Token
X-API-SecretKey | **required** <br> Secret Key







##Push Data Via Websocket

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

  $ curl http://api.cognism.io/api/v1/audit/user?accessToken=0000-0000-0000 \
  -d 'action=String' \
  -d 'source=String' \
  -d 'data=1' \
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

What documents? Who can access what? Any other info on docs? 

This endpoint retrieves what information in the docs??


### HTTP Request

<aside class="success">
POST
</aside>

`http://api.cognism.io/api/v1/websocket/session`


### Query Parameters

Parameter | Description
--------- | ----------- | -----------
session | **optional** <br> Websocket session.