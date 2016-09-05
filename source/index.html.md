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

api = Kittn::APIClient.authorize!('0000-0000-0000')
```

```python
import kittn

api = kittn.authorize('0000-0000-0000')
```

```shell

# With shell, you can just pass the correct header with each request
curl "api_endpoint_here"
  -H "Authorization: 0000-0000-0000"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('0000-0000-0000');
```

> Make sure to replace `0000-0000-0000` with your API key.

Cognism uses token keys for authentification. How to get the key? Do we need it for all API requests? Example of what it looks like.

Difference between AccessToken, SecretKey, X-API-AccessToken and X-API-SecretKey

Also, security key, what is that?


Users in most API calls can use one of two tokens:
(1) accessToken + secretKey => these are one time generated tokens that we manually provide to our users. They are generated within our user management application, Cristian can tell you more about it.  Currently our users cannot regenerate or get these tokens without our customer success manager but that will change over time.

How do you get a token? Register?




Kittn uses API keys to allow access to the API. You can register a new Kittn API key at our [developer portal](http://example.com/developers).

Kittn expects for the API key to be included in all API requests to the server in a header that looks like the following:

`Authorization: 0000-0000-0000`

<aside class="notice">
You must replace <code>0000-0000-0000</code> with your personal API key.
</aside>


















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

A company represents the organisation that is being searched. Information about the company's location, size and indusctry can be found in this object.

Parameter | Description
--------- | ----------- 
city | **string** <br> The city the company is based in.
name | **string** <br> Name of the company.
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

This API let's you search for information on a comapany of your chosing. The name of the comapany needs to be known to access information such as the address the company is located at, its size and industry.



### HTTP Request

<aside class="success">
GET
</aside>


`http://api.cognism.io/api/v1/company/{name}`


### Query Parameters

Parameter | Description
--------- | ----------- 
name | **required** <br> Name of the company being searched.
X-API-AccessToken | **required** <br> Access Token
X-API-AccessToken | **optional** <br> Secret Key






























#Documents v1

##Document Object

```json
{
      "uid": 1296861,
      "eid": "9028205",
      "headline": "Nexen Tire Supplies Original Equipment Tires for the Porsche Cayenne",
      "subHeadline": "-- Nexen Tire's N'FERA RU1 selected as original equipment tires for the Porsche Cayenne - it is the tire manufacturer's first time supplying to Porsche.",
      "abstract": "<p>SEOUL, South Korea, Sept. 4, 2016 /PRNewswire/ -- Nexen Tire, a leading global tire manufacturer, announced that it will supply the Porsche Cayenne with its N'FERA RU1 255/55R18 109Y XL as original equipment (OE) tires.</p>",
      "url": "http://www.prnewswire.com/news-releases/nexen-tire-supplies-original-equipment-tires-for-the-porsche-cayenne-300322435.html",
      "date": "05.09.2016",
      "author": "Nexen Tire",
      "source": "PR Newswire",
      "annotations": [
        {
          "kind": "industry",
          "label": "AUT"
        }
      ],
      "photos": [
        "http://photos.prnewswire.com/prnh/20160901/403424"
      ],
      "videos": [],
      "entities": [
        {
          "type": "LOCATION",
          "value": "SEOUL",
          "relevance": 1
        },
        {
          "type": "ORGANIZATION",
          "value": "South Korea",
          "relevance": 0
        },
        {
          "type": "PERSON",
          "value": "Yangsan",
          "relevance": 4
        },
        {
          "type": "QUOTE",
          "value": "We are thrilled to supply original equipment tires for Porsche for the first time",
          "relevance": 1
        }
      ],
      "quotations": [
        {
          "speakerName": "Travis Kang",
          "speakerTitle": "Chief Executive Officer",
          "speakerOrganization": "Nexen",
          "quotation": "As Porsche is a representative luxury carmaker with prestigious design and performance, this approval for the Porsche Cayenne proves the superior quality and advanced-technology of our products ."
        }
      ]
    }
```

What do we actually get with this? What is a document?

Parameter | Description
--------- | ----------- 
headLine | **string** <br> First name of audit user.
subHeadline | **string** <br> Last name of audit user.
address | **string** <br> Address for audit user.
abstract | **string** <br> Article abstract, commonly a short summary of text.
url | **string** <br> Source URL for article.
date | **string** <br> Date the article was published.
author | **string** <br> Author of the article.
source  | **string** <br> Data source such as PR Newswire, Financial Times or Associated Press.
annotations | **string** <br> Document metadata such as subject of the article e.g. subject=PER
photos | **string** <br> Photo links in article.
videos | **string** <br> Video links in article.
entities | **string** <br> Entities mentioned in article such as locations, organizations, people or quotes.
quotations | **string** <br> Information about quotes present in articles.








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
      "marketing"
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
    "dateFrom": "05.09.2016",
    "dateTo": "05.09.2016",
    "annotation": [],
    "source": [
      "PR Newswire"
    ]
  },
  "documents": [
    {
      "uid": 1296861,
      "eid": "9028205",
      "headline": "Nexen Tire Supplies Original Equipment Tires for the Porsche Cayenne",
      "subHeadline": "-- Nexen Tire's N'FERA RU1 selected as original equipment tires for the Porsche Cayenne - it is the tire manufacturer's first time supplying to Porsche. -- For Nexen Tire supplying Porsche proves the tire's superior quality and advanced-technology. -- By taking this momentum as a great opportunity, the company will strengthen the brand value through various premium marketing activities",
      "abstract": "<p>SEOUL, South Korea, Sept. 4, 2016 /PRNewswire/ -- Nexen Tire, a leading global tire manufacturer, announced that it will supply the Porsche Cayenne with its N'FERA RU1 255/55R18 109Y XL as original equipment (OE) tires. This is the first time that Nexen Tire is supplying its original equipment tires to any of the Porsche car models.</p>",
      "url": "http://www.prnewswire.com/news-releases/nexen-tire-supplies-original-equipment-tires-for-the-porsche-cayenne-300322435.html",
      "date": "05.09.2016",
      "author": "Nexen Tire",
      "source": "PR Newswire",
      "annotations": [
        {
          "kind": "industry",
          "label": "AUT"
        },
        {
          "kind": "industry",
          "label": "TRN"
        },
        {
          "kind": "industry",
          "label": "TRT"
        }
      ],
      "photos": [
        "http://photos.prnewswire.com/prnh/20160901/403424",
        "http://photos.prnewswire.com/prnh/20160901/403424"
      ],
      "videos": [],
      "entities": [
        {
          "type": "LOCATION",
          "value": "SEOUL",
          "relevance": 1
        },
        {
          "type": "ORGANIZATION",
          "value": "South Korea",
          "relevance": 0
        },
        {
          "type": "PERSON",
          "value": "Yangsan",
          "relevance": 4
        },
        {
          "type": "QUOTE",
          "value": "We are thrilled to supply original equipment tires for Porsche for the first time",
          "relevance": 1
        }
      ],
      "quotations": [
        {
          "speakerName": "Travis Kang",
          "speakerTitle": "Chief Executive Officer",
          "speakerOrganization": "Nexen",
          "quotation": "As Porsche is a representative luxury carmaker with prestigious design and performance, this approval for the Porsche Cayenne proves the superior quality and advanced-technology of our products ."
        }
      ]
    }
  ]
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
--------- | ----------- 
keywords | **optional** <br> Keywords for the search, such as marketing, appoints.chief marketing officer or named.chief marketing officer
fields | **optional** <br> Search fields such as articleName,subHeadline or abstract
exclusions | **optional** <br> Exclude words from search such as retirement or leaving
outputFields | **optional** <br> Output field(s) (i.e. headline,url,abstract)
source | **required** <br> Data source such as PR Newswire, Financial Times or Associated Press.
dateFrom | **optional** <br> Limit search by start date, dd.MM.yyyy
dateTo | **optional** <br> Limit search by end date, dd.MM.yyyy
annotation | **optional** <br> Document metadata such as subject of the article e.g. subject=PER
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
  Keywords = marketing
  Search fields = articleName, subHeadline, abstract
  Exclusions = 
  Date From = 20.06.2016
  Date To = 20.08.2016
  Annotation = List()
  Source = Financial Times

  [1] Dentsu strikes $1.5bn deal for US digital marketing firm
EID: f995dd4a-5d44-11e6-bb77-a121aa8abd95 | UID: 1271176 | Date: 08.08.2016 | Author: Arash Massoudi | Source: Financial Times
URL: http://www.ft.com/cms/s/0/f995dd4a-5d44-11e6-bb77-a121aa8abd95.html

Annotations:
  genre => News
  section => US & Canada
  section => Media

Named Entities:
  LOCATION=UK (1.0)
  LOCATION=Silicon Valley (1.0)
  PERSON=Lazard (1.0)
  PERSON=David Williams (1.0)
  ORGANIZATION=Dentsu Aegis Network (1.0)
  ORGANIZATION=Evercore Partners (1.0)
  LOCATION=Merkle (3.0)
  PERSON=Merkle (4.0)

Quotations:
  Jerry Buhlmann (Chief Executive Officer) @ Dentsu Aegis Network => We are more about reaching the people you don’t know and they are all about reaching people you do
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
--------- | ----------- 
keywords | **optional** <br> Keywords for the search, such as appoints.chief marketing officer or named.chief marketing officer
fields | **optional** <br> Search fields such as articleName,subHeadline or abstract
exclusions | **optional** <br> Exclude words from search such as retirement or leaving
outputFields | **optional** <br> Output field(s) (i.e. headline,url,abstract)
source | **required** <br> Data source such as PR Newswire, Financial Times or Associated Press.
dateFrom | **optional** <br> Limit search by start date, dd.MM.yyyy
dateTo | **optional** <br> Limit search by end date, dd.MM.yyyy
annotation | **optional** <br> Document metadata such as subject of the article e.g. subject=PER
accessToken | **required** <br> Access Token
secretKey | **optional** <br> Secret Key


























#Documents v2

##Document Object

```json
Cognism Data Report

Query Parameters:
  Keywords = ORGANIZATION:IBM
  Search fields = body
  Exclusions = None
  Date From = 01.01.2016
  Date To = 20.08.2016
  Annotation = All
  Source = PR Newswire


[1] 6mm x 6mm, Longsys Technology launches the world's smallest IoT WiFi SiP module
EID: 8667390 | UID: 1057574 | Date: Mon Jan 04 14:00:00 UTC 2016 | Author: Some(Longsys Technology Co., Ltd.) | Source: PR Newswire
URL: Some(http://www.prnewswire.com/news-releases/364110661.html)

Abstract:
<p>LAS VEGAS, Jan. 4, 2016 /PRNewswire/ -- Longsys Technology, the leading solutions provider for the Internet of Things (IoT), just announced the world's smallest IoT WiFi Silicon-in-package (SiP) module, LTP0201, which is designed for IoT and wearable devices that can connect to other smart devices or directly connect to the Internet for cloud-based data analytics and enhanced services.</p>

Annotations:
  subject => PDT
  industry => CPR

Photos:
  http://photos.prnewswire.com/prnh/20151228/318161
  http://photos.prnewswire.com/prnh/20151228/318162

Named Entities:
  EMAIL=iotsales@longsys.com (5.0)
  EMAIL=xiaogang.li@longsys.com (5.0)
  LOCATION=Las Vegas Blvd. (7.0)
  LOCATION=LAS VEGAS (4.0)
  ORGANIZATION=MCU (4.0)
  ORGANIZATION=IBM (1.0)
    Ref: COGNISM-ID = International Business Machines Corporation => id=3dd271de-db38-472e-b8d7-1d968ef428c0
  ORGANIZATION=Las Vegas (0.0)
  ORGANIZATION=AES (1.0)
  ORGANIZATION=Longsys Technology Co., Ltd. (6.0)
  PERSON=Dave Pang (7.0)
    Ref: TITLE=General Manager (1.0)
      Ref: COGNISM-ID = General Manager => id=73b52b17-8d63-435c-b121-c84c6ad9e827
    Ref: ORGANIZATION=Longsys Technology Co., Ltd. (6.0)
  PERSON=Caesar (2.0)
    Ref: ORGANIZATION=Las Vegas (0.0)
  PERSON=Xiaogang Li (2.0)
    Ref: ORGANIZATION=Las Vegas (0.0)
    Ref: PHONE=+1 (10.0)
    Ref: EMAIL=iotsales@longsys.com (5.0)
  PHONE=+1 (10.0)
  QUOTE=In 5 years, more than 60 % IoT and wearable products will incorporate SiP modules because of its mini size and more consistent RF performance (1.0)
    Ref: PERSON=Dave Pang (7.0)
      Ref: TITLE=General Manager (1.0)
        Ref: COGNISM-ID = General Manager => id=73b52b17-8d63-435c-b121-c84c6ad9e827
      Ref: ORGANIZATION=Longsys Technology Co., Ltd. (6.0)
      Ref: PHONE=+1 (10.0)
      Ref: EMAIL=iotsales@longsys.com (5.0)
  QUOTE=As the fledgling industry evolves, connected devices require more functional chips packaged into one smaller SiP, longsys has devoted in this trend for years and now is the worldwide leading Wireless SiP technology provider (1.0)
    Ref: PERSON=Dave Pang (7.0)
      Ref: TITLE=General Manager (1.0)
        Ref: COGNISM-ID = General Manager => id=73b52b17-8d63-435c-b121-c84c6ad9e827
      Ref: ORGANIZATION=Longsys Technology Co., Ltd. (6.0)
      Ref: PHONE=+1 (10.0)
      Ref: EMAIL=iotsales@longsys.com (5.0)
```

What will this document really generate?

Parameter | Description
--------- | ----------- 
Document | Data report with information found for the search term.
Query Parameters | Query parameters set for search.
Abstract | Opening paragraph of article.
Annotations | Metadata for articles such as the subject or industry.
Photos | Photo links in article.
Names Entities | Details of companies, people and locations mentioned in the article.








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
  Keywords = ORGANIZATION:IBM
  Search fields = body
  Exclusions = None
  Date From = 01.01.2016
  Date To = 20.08.2016
  Annotation = All
  Source = PR Newswire


[1] 6mm x 6mm, Longsys Technology launches the world's smallest IoT WiFi SiP module
EID: 8667390 | UID: 1057574 | Date: Mon Jan 04 14:00:00 UTC 2016 | Author: Some(Longsys Technology Co., Ltd.) | Source: PR Newswire
URL: Some(http://www.prnewswire.com/news-releases/364110661.html)

Abstract:
<p>LAS VEGAS, Jan. 4, 2016 /PRNewswire/ -- Longsys Technology, the leading solutions provider for the Internet of Things (IoT), just announced the world's smallest IoT WiFi Silicon-in-package (SiP) module, LTP0201, which is designed for IoT and wearable devices that can connect to other smart devices or directly connect to the Internet for cloud-based data analytics and enhanced services.</p>

Annotations:
  subject => PDT
  industry => CPR

Photos:
  http://photos.prnewswire.com/prnh/20151228/318161
  http://photos.prnewswire.com/prnh/20151228/318162

Named Entities:
  EMAIL=iotsales@longsys.com (5.0)
  EMAIL=xiaogang.li@longsys.com (5.0)
  LOCATION=Las Vegas Blvd. (7.0)
  LOCATION=LAS VEGAS (4.0)
  ORGANIZATION=MCU (4.0)
  ORGANIZATION=IBM (1.0)
    Ref: COGNISM-ID = International Business Machines Corporation => id=3dd271de-db38-472e-b8d7-1d968ef428c0
  ORGANIZATION=Las Vegas (0.0)
  ORGANIZATION=AES (1.0)
  ORGANIZATION=Longsys Technology Co., Ltd. (6.0)
  PERSON=Dave Pang (7.0)
    Ref: TITLE=General Manager (1.0)
      Ref: COGNISM-ID = General Manager => id=73b52b17-8d63-435c-b121-c84c6ad9e827
    Ref: ORGANIZATION=Longsys Technology Co., Ltd. (6.0)
  PERSON=Caesar (2.0)
    Ref: ORGANIZATION=Las Vegas (0.0)
  PERSON=Xiaogang Li (2.0)
    Ref: ORGANIZATION=Las Vegas (0.0)
    Ref: PHONE=+1 (10.0)
    Ref: EMAIL=iotsales@longsys.com (5.0)
  PHONE=+1 (10.0)
  QUOTE=In 5 years, more than 60 % IoT and wearable products will incorporate SiP modules because of its mini size and more consistent RF performance (1.0)
    Ref: PERSON=Dave Pang (7.0)
      Ref: TITLE=General Manager (1.0)
        Ref: COGNISM-ID = General Manager => id=73b52b17-8d63-435c-b121-c84c6ad9e827
      Ref: ORGANIZATION=Longsys Technology Co., Ltd. (6.0)
      Ref: PHONE=+1 (10.0)
      Ref: EMAIL=iotsales@longsys.com (5.0)
  QUOTE=As the fledgling industry evolves, connected devices require more functional chips packaged into one smaller SiP, longsys has devoted in this trend for years and now is the worldwide leading Wireless SiP technology provider (1.0)
    Ref: PERSON=Dave Pang (7.0)
      Ref: TITLE=General Manager (1.0)
        Ref: COGNISM-ID = General Manager => id=73b52b17-8d63-435c-b121-c84c6ad9e827
      Ref: ORGANIZATION=Longsys Technology Co., Ltd. (6.0)
      Ref: PHONE=+1 (10.0)
      Ref: EMAIL=iotsales@longsys.com (5.0)
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
--------- | ----------- 
dateFrom | **optional** <br> Limit search by start date, dd.MM.yyyy
dateTo | **optional** <br> Limit search by end date, dd.MM.yyyy
tag | **optional** <br> Search by tags: ORGANIZATION, PERSON or LOCATION
term | **optional** <br> Search term such as the name of an organisation.
source | **required** <br> Data source such as social.
aboutness | **required** <br> A score given based on the relevance of the entity in the news article. Range set between 1 and 10, 1=least relevant 10=most relevant.
page | **required** <br> Data is returned in pages, set here the number of pages retrieved by the search.
count | **required** <br> The number of results displayed on a single page.
accessToken | **required** <br> Access Token
secretKey | **optional** <br> Secret Key

























#Events

##Event Object

```json
[
  {
    "id": "9c9567cf-10a1-4b4d-b553-77b83f5de16a",
    "at": 1471732633672,
    "date": "20.08.2016",
    "type": "job-join",
    "org": "IBM (Contract)",
    "orgInfo": {},
    "loc": {
      "country": "United States",
      "state": "Colorado",
      "city": "Colorado Springs",
      "region": "AMERICAS"
    },
    "old_loc": {
      "country": "United States",
      "state": "Colorado",
      "city": "Colorado Springs"
    },
    "source": "social",
    "meta": {
      "datecreated": "2016-08-20T22:32:21.989658"
    },
    "employee": {
      "city": "Colorado Springs",
      "first_name": "J. Warren",
      "last_name": "Padgett",
      "name": "J. Warren Padgett",
      "title": "North America Talent Search Team - Sourcing Recruiter",
      "url": "https://www.linkedin.com/in/jwarrenpadgett",
      "country": "United States",
      "organisation": "IBM (Contract)",
      "state": "Colorado",
      "old_job_title": "Senior Corporate Sourcing Recruiter",
      "photo_url": "https://media.licdn.com/mpr/mpr/shrinknp_200_200/p/8/005/073/1a6/302f13b.jpg",
      "old_organisation": "Hewlett Packard Enterprise (Contract)",
      "age": 39,
      "previous": {
        "time_to": "201608",
        "time_from": "201405"
      }
    },
    "typeName": "External Movement",
    "orgToInfo": {
      "name": "IBM (Contract)",
      "type": ""
    },
    "orgFromInfo": {
      "name": "Hewlett Packard Enterprise (Contract)",
      "type": ""
    }
  }
]
```

What is this object used for? Below example of output:

Parameter | Description
--------- | ----------- 
id | **string** <br> Event id.
at | **string** <br> Date in UNIX time when event occured.
date | **string** <br> Date when event occured.
type | **string** <br> Type of data, such as job-join, job-leave, job-move, location-move, person-mention, quote, 310 (Article Mentions) or 330 (Brand Mentions).
org | **string** <br> Name of company.
orgInfo | **string** <br> Other information about the company.
loc | **string** <br> Geographical location of the company.
old_loc | **string** <br> Previous location of the company.
source | **string** <br> Data source such as social.
meta | **string** <br> Meta data such as the date the event was created.
typeName | **string** <br> The type of event that took place such as external movement.
orgToInfo | **string** <br> Information about the new position the employee has moved to.
orgFromInfo | **string** <br> Information about the position the employee has moved from.

EMPLOYEE

Parameter | Description
--------- | ----------- 
city | **string** <br> City the epmloyee is located at.
first name | **string** <br> Employee's first name.
last name | **string** <br> Employee's last name.
name | **string** <br> Full name of the employee.
title | **string** <br> Employee job title.
url | **string** <br> Contact url for employee.
country | **string** <br> Employee's country of residence.
organisation | **string** <br> Employee's current employer.
state | **string** <br> State or province where the employee lives.
old job title | **string** <br> Previous job title of employee.
photo url | **string** <br> URL to a photo of the employee.
old organisation | **string** <br> Previous employer of the employee.
age | **string** <br> Employee's age.
previous | **string** <br> Start and end time of previous employment?






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
    "id": "9c9567cf-10a1-4b4d-b553-77b83f5de16a",
    "at": 1471732633672,
    "date": "20.08.2016",
    "type": "job-join",
    "org": "IBM (Contract)",
    "orgInfo": {},
    "loc": {
      "country": "United States",
      "state": "Colorado",
      "city": "Colorado Springs",
      "region": "AMERICAS"
    },
    "old_loc": {
      "country": "United States",
      "state": "Colorado",
      "city": "Colorado Springs"
    },
    "source": "social",
    "meta": {
      "datecreated": "2016-08-20T22:32:21.989658"
    },
    "employee": {
      "city": "Colorado Springs",
      "first_name": "J. Warren",
      "last_name": "Padgett",
      "name": "J. Warren Padgett",
      "title": "North America Talent Search Team - Sourcing Recruiter",
      "url": "https://www.linkedin.com/in/jwarrenpadgett",
      "country": "United States",
      "organisation": "IBM (Contract)",
      "state": "Colorado",
      "old_job_title": "Senior Corporate Sourcing Recruiter",
      "photo_url": "https://media.licdn.com/mpr/mpr/shrinknp_200_200/p/8/005/073/1a6/302f13b.jpg",
      "old_organisation": "Hewlett Packard Enterprise (Contract)",
      "age": 39,
      "previous": {
        "time_to": "201608",
        "time_from": "201405"
      }
    },
    "typeName": "External Movement",
    "orgToInfo": {
      "name": "IBM (Contract)",
      "type": ""
    },
    "orgFromInfo": {
      "name": "Hewlett Packard Enterprise (Contract)",
      "type": ""
    }
  }
]
```

What documents? Who can access what? Any other info on docs? 

This endpoint retrieves what information in the docs??


### HTTP Request

<aside class="success">
GET
</aside>

`http://api.cognism.io/api/v1/events/stream?dateFrom={date_from}&dateTo={date_to}&rule={query_rule}&page={page}&count={count}`


### Query Parameters

Parameter | Description
--------- | ----------- 
dateFrom | **optional** <br> Limit search by start date, dd.MM.yyyy
dateTo | **optional** <br> Limit search by end date, dd.MM.yyyy
rule | **optional** <br> Query rule such as type=job-join|job-leave;org=IBM;employee.title=valuelist(mediaradar-jobtitle)
page | **optional** <br> Data is returned in pages, set here the number of pages retrieved by the search. Default values is 0.
count | **optional** <br> The number of results displayed on a single page. Defualt value is 50.
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

`http://api.cognism.io/api/v1/events/stream/csv?dateFrom={date_from}&dateTo={date_to}&rule={query_rule}&page={page}&count={count}&accessToken={access_token}&secretKey={secret_key}`


### Query Parameters

Parameter | Description
--------- | ----------- 
dateFrom | **optional** <br> Limit search by start date, dd.MM.yyyy
dateTo | **optional** <br> Limit search by end date, dd.MM.yyyy
rule | **optional** <br> Query rule such as type=job-join|job-leave;org=IBM;employee.title=valuelist(mediaradar-jobtitle)
page | **optional** <br> Data is returned in pages, set here the number of pages retrieved by the search. Default values is 0.
count | **optional** <br> The number of results displayed on a single page. Defualt value is 50.
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
--------- | ----------- 
accessToken | **required** <br> Access Token
secretKey | **optional** <br> Secret Key
dateFrom | **optional** <br> Limit search by start date, dd.MM.yyyy
dateTo | **optional** <br> Limit search by start date, dd.MM.yyyy
page | **required** <br> Data is returned in pages, set here the number of pages retrieved by the search. Default values is 0.
count | **required** <br> The number of results displayed on a single page. Defualt value is 50.



























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
--------- | ----------- 
city | **string** <br> The city the person's work is located at.
vc | **integer** <br> Unix timestamp of the document.
ver | **integer** <br> Document version number.
groups | **string** <br> List of groups that the person is a member of.
cc | **string** <br> Country code such as "uk"
country | **string** <br> The country the person is based at.
current | **string** <br> Name of current employer.
skills | **string** <br> List of skills this person has.
state | **string** <br> The state or provnce this person is based in.
birth date | **integer** <br> Person's date of birth.
fullname | **string** <br> Person's fullname.
topcard | **string** <br> Overview of the person's current situation.
uid | **string** <br> persons user id

EXPERIENCE

Parameter | Description
--------- | ----------- 
to | **integer** <br> Date the person finished work at the company. Blank if this is the person's current role.
company | **string** <br> Name of the company that employed the person.
from | **integer** <br> Date the person started work at the company.
description | **string** <br> Description of the person's role at the company.
name | **string** <br> Person's job title in this role.

CERTIFICATIONS

Parameter | Description
--------- | ----------- 
to | **integer** <br> End date for finishing the certificate.cd s
company | **string** <br> Name of the company that employed the person.
from | **integer** <br> Date the person gained the certificate. 
description | **string** <br> Description of the certificate.
name | **string** <br> Title of the certificate.

EDUCATION

Parameter | Description
--------- | ----------- 
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
--------- | ----------- 
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

Since we have a platform that can stream events a.k.a. Sales Trigger then via subscriptions you can subscribe to certain event types which would then get sent to your system using HTTP web service you provide.

For a classic subscription (not websocket) you need to provide callback webservice which gets called when event satisfying your pattern gets into our system. If your webservice requires setting some kind of special headers like for security purposes you can define those inside callback details.



Parameter | Description
--------- | ----------- 
_id | **required** <br> Id of subscription.
name | **required** <br> Customer defined name of subscription.
active | **required** <br> Is the subscription active. Boolean value with options true or false.
created at | **required** <br> UNIX number indicating the time the subscription was created.
updated at | **required** <br> UNIX number indicating the time the subscription was last modified.


CALLBACK HTTP

Parameter | Description
--------- | ----------- 
method | **required** <br> Callback method, e.g. POST
url | **required** <br> Callback URL. Webservice URL that Cognism will provide updates to based on chosen requirements.
headers | **required** <br> Headers required for the called webservice.












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

Get all subscriptions that have been created for the account. This request only requires the authentification token and gives a list of the current subscriptions.


### HTTP Request

<aside class="success">
GET
</aside>

`http://api.cognism.io/api/v1/subscription`


### Query Parameters

Parameter | Description
--------- | ----------- 
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

Create a subsriction. 


### HTTP Request

<aside class="success">
POST
</aside>

`http://api.cognism.io/api/v1/subscription`


### Query Parameters

Parameter | Description
--------- | ----------- 
X-API -AccessToken | **required** <br> Access Token
X-API-SecretKey | **required** <br> Secret Key
name | **required** <br> Name of who?
active | **required** <br> Is the subscription active. Boolean value with options true or false.


CALLBACK HTTP

Parameter | Description
--------- | ----------- 
method | **required** <br> Callback method, e.g. POST
url | **required** <br> Callback URL. Webservice URL that Cognism will provide updates to based on chosen requirements.
headers | **required** <br> Headers required for the called webservice.









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
no content
```

Delete any subscription that has been previously created. The id of the subscription is required for this action.


### HTTP Request

<aside class="success">
DELETE
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

Get details of a specific subscription. The id of the subscription is required. To find a list of all subscriptions, see "Get All Subsrciptions"


### HTTP Request

<aside class="success">
GET
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
--------- | ----------- 
X-API -AccessToken | **required** <br> Access Token
X-API-SecretKey | **required** <br> Secret Key
name | **required** <br> Name of who?
active | **required** <br> Is the subscription active. Boolean value with options true or false.


CALLBACK HTTP

Parameter | Description
--------- | ----------- 
method | **required** <br> Callback method, e.g. POST
url | **required** <br> Callback URL. Webservice URL that Cognism will provide updates to based on chosen requirements.
headers | **required** <br> Headers required for the called webservice.



























#Websocket

Same as with a subscription but using Websocket technology. Websocket is bi-directional real-time channel through which we can push events, as they're flowing into our system, directly to customer system.







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

```

What documents? Who can access what? Any other info on docs? 

This endpoint retrieves what information in the docs??


### HTTP Request

<aside class="success">
GET
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

```

What documents? Who can access what? Any other info on docs? 

This endpoint retrieves what information in the docs??


### HTTP Request

<aside class="success">
POST
</aside>

`http://api.cognism.io/api/v1/websocket/session?session={session}`


### Query Parameters

Parameter | Description
--------- | ----------- | -----------
session | **optional** <br> Websocket session id.