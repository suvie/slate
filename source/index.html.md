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











#Error
##Error Codes
##Error Object









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
[
  {
    "city": "Armonk, New York",
    "name": "IBM",
    "zip": "10504",
    "country": "United States",
    "industry": "Information Technology and Services",
    "site": "http://www.ibm.com",
    "id": "1009",
    "path": "ibm",
    "type": "Public Company",
    "region": "NY",
    "street_address": [
      "New Orchard Road",
      "International Business Machines Corp."
    ],
    "size": "10,001+"
  }
]
```

An company represents the organisation that is being researched. To run the get request the company name needs to be known and an access token needs to be obtained.

Parameter | Description
--------- | ----------- | -----------
city | **string** <br> The city the company is based in.
name | **string** <br> Name of company.
zip | **string** <br> Zip code or post code of company.
country | **string** <br> The country the company is based in.
industry | **string** <br> The industry the company operates in.
site | **string** <br> Company home website.
id | **integer** <br> Numerical company id.
path | **string** <br> Path name for the company. 
type | **string** <br> The type of business entity such as public comapny, limited comapany etc.
region | **string** <br> The region the company head quaters are located at.
street address | **string** <br> Address of the company head quaters.
size | **string** <br> Size braket for the company, which determines how many people are employed by the comapny.




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
    "city": "Armonk, New York",
    "name": "IBM",
    "zip": "10504",
    "country": "United States",
    "industry": "Information Technology and Services",
    "site": "http://www.ibm.com",
    "id": "1009",
    "path": "ibm",
    "type": "Public Company",
    "region": "NY",
    "street_address": [
      "New Orchard Road",
      "International Business Machines Corp."
    ],
    "size": "10,001+"
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
id | **string** <br> Numerical id for deadletter.
source | **string** <br> ???
type | **string** <br> ???
at | **integer** <br> ???

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



























#Documents v1

##Document Object

```json
?? What is this?
```

What do we actually get with this? What is a document?

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
{
  "query": {
    "keywords": [
      "appoints.chief marketing officer"
    ],
    "searchFields": [
      "abstract"
    ],
    "outputFields": [
      "headline"
    ],
    "exclusions": [],
    "dateFrom": "20.06.2016",
    "dateTo": "20.08.2016",
    "annotation": [],
    "source": [
      "social"
    ]
  },
  "documents": [??????]
}
```

What documents? Who can access what? Any other info on docs? 

This endpoint retrieves what information in the docs??


### HTTP Request

<aside class="success">
GET
</aside>

`http://api.cognism.io/api/v1/documents/json?keywords={keywords}&fields={fields}&exclusions={exclusions}&outputFields={output_fields}&source={source}&dateFrom={date_from}&dateTo={date_to}&annotation={annotation}&accessToken={access_token}&secretKey={secret_key}`


### Query Parameters

Parameter | Description
--------- | ----------- | -----------
keywords | **optional** <br> Keywords for the search, such as appoints.chief marketing officer or named.chief marketing officer
fields | **optional** <br> Search fields such as articleName,subHeadline or abstract
exclusions | **optional** <br> Exclude words from search such as retirement or leaving
outputFields | **optional** <br> Output field(s) (i.e. headline,url,abstract)
source | **required** <br> ??
dateFrom | **optional** <br> Limit search by start date, dd.MM.yyyy
dateTo | **optional** <br> Limit search by end date, dd.MM.yyyy
annotation | **optional** <br> Annotation (i.e. subject=PER)
accessToken | **required** <br> Access Token
secretKey | **optional** <br> Secret Key










##Search Documents By Aboutness

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
{
  "query": {
    "keywords": [
      "Cognism"
    ],
    "searchFields": [
      "articleName",
      "subHeadline",
      "abstract"
    ],
    "outputFields": [
      "uid",
      "eid",
      "headline",
      "subHeadline",
      "abstract",
      "url",
      "date",
      "author",
      "source",
      "annotations",
      "photos",
      "videos",
      "entities",
      "quotations"
    ],
    "exclusions": [],
    "dateFrom": "20.06.2016",
    "dateTo": "20.08.2016",
    "annotation": [],
    "source": [
      "social"
    ]
  },
  "documents": []
}
```

What documents? Who can access what? Any other info on docs? 

This endpoint retrieves what information in the docs??


### HTTP Request

<aside class="success">
GET
</aside>

`http://api.cognism.io/api/v1/documents/org/Cognism?dateFrom={date_from}&dateTo={date_to}&source={source}&aboutness={aboutness}&page={page}&count={count}&accessToken={access_token}&secretKey={secret_key}`


### Query Parameters

Parameter | Description
--------- | ----------- | -----------
org | **optional** <br> Organization to search.
dateFrom | **optional** <br> Limit search by start date, dd.MM.yyyy
dateTo | **optional** <br> Limit search by end date, dd.MM.yyyy
source | **optional** <br> ??
aboutness | **required** <br> Minimum Aboutness Score ???
page | **optional** <br> ??
count | **optional** <br> Page Size ??
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
Cognism Data Report

Query Parameters:
  Keywords = appoints.chief marketing officer
  Search fields = artcleName
  Exclusions = retirement
  Date From = 20.06.2016
  Date To = 20.08.2016
  Annotation = ArraySeq()
  Source = social
```

What documents? Who can access what? Any other info on docs? 

This endpoint retrieves what information in the docs??


### HTTP Request

<aside class="success">
GET
</aside>

`http://api.cognism.io/api/v1/documents/txt?keywords={keywords}&fields={fields}&exclusions={exclusions}&source={source}&dateFrom={date_from}&dateTo={date_to}&annotation={annotation}&accessToken={access_token}&secretKey={secret_key}`


### Query Parameters

Parameter | Description
--------- | ----------- | -----------
keywords | **optional** <br> Keywords for the search, such as appoints.chief marketing officer or named.chief marketing officer
fields | **optional** <br> Search fields such as articleName,subHeadline or abstract
exclusions | **optional** <br> Exclude words from search such as retirement or leaving
outputFields | **optional** <br> Output field(s) (i.e. headline,url,abstract)
source | **required** <br> ??
dateFrom | **optional** <br> Limit search by start date, dd.MM.yyyy
dateTo | **optional** <br> Limit search by end date, dd.MM.yyyy
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
Cognism Data Report (DIFF)

Query Parameters:
  Keywords = appoints.chief marketing officer
  Search fields = articleName
  Exclusions = 
  Date From = 20.06.2016
  Date To = 20.08.2016
  Annotation = ArraySeq()
  Source = social
Query Parameters:
  Keywords = chief marketing officer
  Search fields = subHeadline
  Exclusions = 
  Date From = 20.06.2016
  Date To = 20.08.2016
  Annotation = ArraySeq()
  Source = social
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
keywords1 | **optional** <br> Keywords for the search, such as appoints.chief marketing officer or named.chief marketing officer
keywords2 | **optional** <br> Second keyword for the search, such as chief marketing officer
fields1 | **optional** <br> Search fields such as articleName,subHeadline or abstract
fields2 | **optional** <br> Search fields such as articleName,subHeadline or abstract
source | **required** <br> ??
dateFrom | **optional** <br> Limit search by start date, dd.MM.yyyy
dateTo | **optional** <br> Limit search by end date, dd.MM.yyyy
annotation | **optional** <br> Annotation (i.e. subject=PER)
accessToken | **required** <br> Access Token
secretKey | **optional** <br> Secret Key





















#Documents v2

##Document Object

```json
??? No idea
```

What will this document really generate?

Parameter | Description
--------- | ----------- | -----------
?? | **string** <br> First name of audit user.
?? | **string** <br> Last name of audit user.
?? | **string** <br> Address for audit user.








##Search Documents by Entities

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
Cognism Data Report

Query Parameters:
  Keywords = ORGANIZATION:Cognism
  Search fields = body
  Exclusions = None
  Date From = 20.05.2016
  Date To = 20.08.2016
  Annotation = All
  Source = social
```

What documents? Who can access what? Any other info on docs? 

This endpoint retrieves what information in the docs??


### HTTP Request

<aside class="success">
GET
</aside>

`http://api.cognism.io/api/v2/documents/search?dateFrom={date_from}&dateTo={date_to}&tag={tag}&term={term}&source={source}&aboutness={aboutness}&page={page}&count={count}&accessToken={access_token}&secretKey={security_key}`



### Query Parameters

Parameter | Description
--------- | ----------- | -----------
dateFrom | **optional** <br> Limit search by start date, dd.MM.yyyy
dateTo | **optional** <br> Limit search by end date, dd.MM.yyyy
tag | **optional** <br> Search by tags: ORGANIZATION, PERSON or LOCATION
term | **optional** <br> Search term
source | **required** <br> ??
aboutness | **required** <br> ??
page | **required** <br> ??
count | **required** <br> Page size.
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

`http://api.cognism.io/api/v1/events/stream?dateFrom={date_from}&dateTo={date_to}&rule={query_rule}&page={page}&count={count}&enrich={true/false}`


### Query Parameters

Parameter | Description
--------- | ----------- | -----------
dateFrom | **optional** <br> Limit search by start date, dd.MM.yyyy
dateTo | **optional** <br> Limit search by end date, dd.MM.yyyy
rule | **optional** <br> Query rule such as type=job-join|job-leave;org=IBM;employee.title=valuelist(mediaradar-jobtitle)
page | **optional** <br> From index to start the search from. Defaults to 0. ???
count | **optional** <br> The number of search hits to return. Defaults to 50.  ???
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

`http://api.cognism.io/api/v1/events/stream/csv?dateFrom={date_from}&dateTo={date_to}&rule={query_rule}&page={page}&count={count}&accessToken={access_token}&secretKey={secret_key}&enrich={true/false}`


### Query Parameters

Parameter | Description
--------- | ----------- | -----------
dateFrom | **optional** <br> Limit search by start date, dd.MM.yyyy
dateTo | **optional** <br> Limit search by end date, dd.MM.yyyy
rule | **optional** <br> Query rule such as type=job-join|job-leave;org=IBM;employee.title=valuelist(mediaradar-jobtitle)
page | **optional** <br> From index to start the search from. Defaults to 0. ???
count | **optional** <br> The number of search hits to return. Defaults to 50.  ???
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

`http://api.cognism.io/api/v1/events/stream/search?accessToken={access_token}&secretKey={secret_key}`


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
{
  "city": "London",
  "vc": 1463147456,
  "ver": 1,
  "groups": [
    "Women @ IBM",
    "Big Data, Analytics, Hadoop, NoSQL & Cloud Computing",
    "IBM Ecosystem ISV and MSP"
  ],
  "cc": "uk",
  "country": "United Kingdom",
  "experience": [
    {
      "company": "IBM",
      "from": "September 2015",
      "description": "Technical sales and solutions specialist working with clients across the UK and Europe on Big Data platforms including hadoop, data warehousing, analytics, managed services and streaming analytics.",
      "name": "Big Data and Hadoop Technical Sales Specialist"
    },
    {
      "to": "September 2015",
      "company": "IBM",
      "from": "January 2015",
      "description": "Big Data technical sales within IBM Analytics Platform.",
      "name": "Big Data Technical Sales Specialist"
    }
  ],
  "current": "IBM",
  "skills": [
    "Data Management",
    "Teamwork",
    "Big Data"
  ],
  "state": "Hampshire",
  "certifications": [
    {
      "company": "IBM",
      "from": "October 2015",
      "name": "IBM PureData System for Analytics Technical Professional V1"
    }
  ],
  "birth_date": 662688000,
  "full_name": "Mary Mitchell",
  "topcard": {
    "current": [
      "IBM"
    ],
    "locality": "Hursley, Hampshire, United Kingdom",
    "headline": "Big Data and Hadoop Technical Specialist at IBM Analytics",
    "industry": "Information Technology and Services",
    "member-connections": "500+",
    "full_name": "Mary Mitchell"
  },
  "education": [
    {
      "to": "2013",
      "company": "BSc (Hons), Natural Sciences, First Class Honours",
      "from": "2009",
      "name": "University of Newcastle"
    },
    {
      "to": "2009",
      "company": ", A Levels: Physics (A), Chemistry (A), Biology (A), AS Levels: Further Mathematics and Psychology, Grade: 4 As at AS Level, 2 As at A2 Level",
      "from": "2007",
      "name": "Matwell School"
    }
  ],
  "full_name_normalized": "mary mitchell",
  "uid": "marymitchell"
}
```

What is this object used for? Below example of output:

Parameter | Description
--------- | ----------- | -----------
city | **string** <br> The city the person's work is located at.
vc | **integer** <br> ??
ver | **integer** <br> ??
groups | **string** <br> List of groups that the person is a member of.
cc | **string** <br> ??
country | **string** <br> The country the person is based at.
current | **string** <br> Name of current employer.
skills | **string** <br> List of skills this person has.
state | **string** <br> The state or provnce this person is based in.
birth date | **integer** <br> Person's date of birth.
fullname | **string** <br> Person's fullname.
topcard | **string** <br> Overview of the person's current situation.
fullname normalized | **string** <br> ??
uid | **string** <br> persons user id

EXPERIENCE

Parameter | Description
--------- | ----------- | -----------
to | **integer** <br> Date the person finished work at the company. Blank if this is the person's current role.
company | **string** <br> Name of the company that employed the person.
from | **integer** <br> Date the person started work at the company.
description | **string** <br> Description of the person's role at the company.
name | **string** <br> Person's job title in this role.

CERTIFICATIONS

Parameter | Description
--------- | ----------- | -----------
to | **integer** <br> End date for finishing the certificate. ??
company | **string** <br> Name of the company that employed the person.
from | **integer** <br> Date the person gained the certificate. 
description | **string** <br> Description of the certificate.
name | **string** <br> Title of the certificate.

EDUCATION

Parameter | Description
--------- | ----------- | -----------
to | **integer** <br> Date the person finished the program.
company | **string** <br> Name of the institution that provided the education.
from | **integer** <br> Date the program started.
description | **string** <br> Description of the educational program.
name | **string** <br> Name of the educational program.










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
{
  "items": [
    {
      "city": "London",
      "vc": 1463147456,
      "ver": 1,
      "groups": [
        "Women @ IBM",
        "Big Data, Analytics, Hadoop, NoSQL & Cloud Computing",
        "IBM Ecosystem ISV and MSP"
      ],
      "cc": "uk",
      "country": "United Kingdom",
      "experience": [
        {
          "company": "IBM",
          "from": "September 2015",
          "description": "Technical sales and solutions specialist working with clients across the UK and Europe on Big Data platforms including hadoop, data warehousing, analytics, managed services and streaming analytics.",
          "name": "Big Data and Hadoop Technical Sales Specialist"
        }
      ],
      "current": "IBM",
      "skills": [
        "Data Management",
        "Teamwork",
        "Big Data"
      ],
      "state": "Hampshire",
      "certifications": [
        {
          "company": "IBM",
          "from": "October 2015",
          "name": "IBM PureData System for Analytics Technical Professional V1"
        }
      ],
      "birth_date": 662688000,
      "full_name": "Mary Mitchell",
      "topcard": {
        "current": [
          "IBM"
        ],
        "locality": "Hursley, Hampshire, United Kingdom",
        "headline": "Big Data and Hadoop Technical Specialist at IBM Analytics",
        "industry": "Information Technology and Services",
        "member-connections": "500+",
        "full_name": "Mary Mitchell"
      },
      "education": [
        {
          "to": "2013",
          "company": "BSc (Hons), Natural Sciences, First Class Honours",
          "from": "2009",
          "name": "University of Newcastle"
        }
      ],
      "full_name_normalized": "mary mitchell",
      "uid": "marymitchell"
    }
  ]
}
```

This API find information about a specific person. THe search can be defined by a first name, last name or a company name. The response returns information about the person's employment history as well as their skills, certifications and education.


### HTTP Request

<aside class="success">
GET
</aside>

`http://api.cognism.io/api/v1/person?firstName={first_name}&lastName={last_name}&company={company}`


### Query Parameters

Parameter | Description
--------- | ----------- | -----------
firstName | **optional** <br> First name of person to search.
lastName | **optional** <br> Last name of person to search.
company | **optional** <br> The company the person works at.
X-API -AccessToken | **required** <br> Access Token
X-API-SecretKey | **optional** <br> Secret Key























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
    "url": "https://www.??",
    "headers": [
      "articles"
    ]
  },
  "active": false,
  "createdAt": 1472649167365,
  "updatedAt": 1472649167365
}
```

What is this object used for? Below example of output:

Parameter | Description
--------- | ----------- | -----------
_id | **required** <br> Id of subscription.
idUser | **required** <br> Id of the user - what user?
idOrg | **required** <br> Id of the organisation - what org?
name | **required** <br> ??
active | **required** <br> ??
created at | **required** <br> When the subscription was created.
updated at | **required** <br> When the subsription was last modified.

PATTERN
Parameter | Description
--------- | ----------- | -----------
type | **required** <br> Company type code?? - looks like a type code for an org
org | **required** <br> Name of what org?

CALLBACK HTTP
Parameter | Description
--------- | ----------- | -----------
method | **required** <br> Callback method, e.g. POST
url | **required** <br> ??
headers | **required** <br> e.g. string







##Get All Subsrciptions
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
      "url": "https://www.??",
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

Get all subscriptions that have been created for the account. This request only requires the authentification token and gives a list of the current subscriptions.


### HTTP Request

<aside class="success">
GET
</aside>

`http://api.cognism.io/api/v1/subscription`


### Query Parameters

Parameter | Description
--------- | ----------- | -----------
X-API -AccessToken | **required** <br> Access Token
X-API-SecretKey | **required** <br> Secret Key












##Create Subscription

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
    "url": "https://www.???",
    "headers": [
      "articles"
    ]
  },
  "active": false,
  "createdAt": 1472649167365,
  "updatedAt": 1472649167365
}
```

Create a subsriction. 


### HTTP Request

<aside class="success">
POST
</aside>

`http://api.cognism.io/api/v1/subscription`


### Query Parameters

Parameter | Description
--------- | ----------- | -----------
X-API -AccessToken | **required** <br> Access Token
X-API-SecretKey | **required** <br> Secret Key
name | **required** <br> Name of who?
active | **required** <br> Person is active?

PATTERN
Parameter | Description
--------- | ----------- | -----------
type | **required** <br> Company type code?? - looks like a type code for an org
org | **required** <br> Name of what org?

CALLBACK HTTP
Parameter | Description
--------- | ----------- | -----------
method | **required** <br> Callback method, e.g. POST
url | **required** <br> ??
headers | **required** <br> e.g. string









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

  $ curl http://api.cognism.io/api/v1/audit/user?accessToken=0000-0000-0000 \
  -d 'action=String' \
  -d 'source=String' \
  -d 'data=1' \
```

> **RESPONSE EXAMPLE**  


```json
[]
```

Delete any subscription that has been previously created. The id of the subscription is required for this action.


### HTTP Request

<aside class="success">
DELETE
</aside>

`http://api.cognism.io/api/v1/subscription/{subscription_id}`


### Query Parameters

Parameter | Description
--------- | ----------- | -----------
id | **required** <br> Id of the subscription to be deleted.
X-API -AccessToken | **required** <br> Access Token
X-API-SecretKey | **required** <br> Secret Key










##Get Subscription
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
    "url": "https://www.??",
    "headers": [
      "articles"
    ]
  },
  "active": false,
  "createdAt": 1472649847431,
  "updatedAt": 1472649847431
}
```

Get details of a specific subscription. The id of the subscription is required. To find a list of all subscriptions, see "Get All Subsrciptions"


### HTTP Request

<aside class="success">
GET
</aside>

`http://api.cognism.io/api/v1/subscription/{subscription_id}`


### Query Parameters

Parameter | Description
--------- | ----------- | -----------
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

  $ curl http://api.cognism.io/api/v1/audit/user?accessToken=0000-0000-0000 \
  -d 'action=String' \
  -d 'source=String' \
  -d 'data=1' \
```

> **RESPONSE EXAMPLE**  


```json
no content
```

Modify a pre-existing subsription. The id of the subscription is needed. All other fields of the subsriction can be modified.


### HTTP Request

<aside class="success">
PUT
</aside>

`http://api.cognism.io/api/v1/subscription/{subscription_id}`


### Query Parameters

Parameter | Description
--------- | ----------- | -----------
X-API -AccessToken | **required** <br> Access Token
X-API-SecretKey | **required** <br> Secret Key
name | **required** <br> Name of who?
active | **required** <br> Person is active?

PATTERN
Parameter | Description
--------- | ----------- | -----------
type | **required** <br> Company type code?? - looks like a type code for an org
org | **required** <br> Name of what org?

CALLBACK HTTP
Parameter | Description
--------- | ----------- | -----------
method | **required** <br> Callback method, e.g. POST
url | **required** <br> ??
headers | **required** <br> e.g. string





















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