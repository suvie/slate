#News Stream

##News Stream Object

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
          "quotation": "As Porsche is a representative luxury car maker with prestigious design and performance, this approval for the Porsche Cayenne proves the superior quality and advanced-technology of our products ."
        }
      ]
    }
```

The news stream object returns information about an online document or an article. The object includes metadata about the article such as its author, creation date and source, and will also provide key entities that are mentioned in the article, such as quotes, people and organizations.


Parameter | Description
--------- | ----------- 
headLine | **string** <br> Article headline.
subHeadline | **string** <br> Article sub headline.
abstract | **string** <br> Article abstract, commonly a short summary of text. Can also be the opening paragraph of article.
url | **string** <br> Source URL for article.
date | **string** <br> Date the article was published.
author | **string** <br> Author of the article.
source  | **string** <br> Data source such as PR Newswire, Financial Times or Associated Press.
annotations | **string** <br> Article metadata such as the subject or industry the article is about.
photos | **string** <br> Photo links found in article.
videos | **string** <br> Video links found in article.
entities | **string** <br> Entities mentioned in article such as locations, organizations, people or quotes.
quotations | **string** <br> Information about quotes present in article.






##Search Documents (JSON)

```ruby
api.document.all('marketing',
                  'Financial Times',
                  '20.04.2016',
                  '0.06.2016',
                  'your_access_token',
                  'your_secret_key')
```

```python
keywords = "marketing"
source = "Financial Times"
dateFrom = "20.04.2016"
dateTo = "20.06.2016"
accessToken = "your_access_token"
secretKey = "your_secret_key"

docs = api.Document.all(keywords, 
                  source, 
                  dateFrom, 
                  dateTo, 
                  accessToken, 
                  secretKey)
```

```shell
$ curl -v 'http://api.cognism.io/api/v1/documents/json?
              keywords=marketing&
              source=Financial%20Times&
              dateFrom=20.04.2016&
              dateTo=20.06.2016&
              accessToken=your_access_token& 
              secretKey=your_secret_key' 
```

```javascript

url = "http://api.cognism.io/api/v1/documents/json?
        keywords=marketing&
        source=Financial%20Times&
        dateFrom=20.04.2016&
        dateTo=20.06.2016&
        accessToken=your_access_token&
        secretKey=your_secret_key";

xmlHttp.open( "GET", url );

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
          "quotation": "As Porsche is a representative luxury car maker with prestigious design and performance, this approval for the Porsche Cayenne proves the superior quality and advanced-technology of our products ."
        }
      ]
    }
  ]
}
```

This API let's you search for online documents from specific sources using keywords. Some of the current sources include R Newswire, Financial Times and Associated Press. You can specify any keywords you wish and narrow down the search by excluding words, limiting the publishing date and specifying the field within the article that contains the keywords.

Output is returned in JSON format.


### HTTP Request

<aside class="tag">
<div class="lbl-get">GET</div>
</aside>

`http://api.cognism.io/api/v1/documents/json?keywords={keywords}&fields={fields}&exclusions={exclusions}&outputFields={output_fields}&source={source}&dateFrom={date_from}&dateTo={date_to}&annotation={annotation}&accessToken={access_token}&secretKey={secret_key}`


### Query Parameters

Parameter | Description
--------- | ----------- 
keywords | **optional** <br> Keywords for the search, such as marketing, appoints.chief marketing officer or named.chief marketing officer.
fields | **optional** <br> Search fields such as articleName,subHeadline or abstract.
exclusions | **optional** <br> Exclude words from search such as retirement or leaving.
outputFields | **optional** <br> Specify output fields for the search such as headline, URL and abstract.
source | **required** <br> Data source such as PR Newswire, Financial Times or Associated Press.
dateFrom | **optional** <br> Limit search by a start date. Use format dd.MM.yyyy.
dateTo | **optional** <br> Limit search by an end date. Use format dd.MM.yyyy.
annotation | **optional** <br> Document metadata such as subject of the article e.g. subject=PER.
accessToken | **required** <br> Access Token
secretKey | **optional** <br> Secret Key











##Search Documents (TXT)


```ruby
api.document.all('marketing',
                  'Financial Times',
                  '20.04.2016',
                  '0.06.2016',
                  'your_access_token',
                  'your_secret_key')
```

```python
keywords = "marketing"
source = "Financial Times"
dateFrom = "20.04.2016"
dateTo = "20.06.2016"
accessToken = "your_access_token"
secretKey = "your_secret_key"

docs = api.Document.all(keywords, 
                  source, 
                  dateFrom, 
                  dateTo, 
                  accessToken, 
                  secretKey)
```

```shell
$ curl -v 'http://api.cognism.io/api/v1/documents/txt?
              keywords=marketing&
              source=Financial%20Times&
              dateFrom=20.04.2016&
              dateTo=20.06.2016&
              accessToken=your_access_token& 
              secretKey=your_secret_key' 
```

```javascript
url = "http://api.cognism.io/api/v1/documents/txt?
              keywords=marketing&
              source=Financial%20Times&
              dateFrom=20.04.2016&
              dateTo=20.06.2016&
              accessToken=your_access_token& 
              secretKey=your_secret_key";

xmlHttp.open( "GET", url );

```

> **RESPONSE EXAMPLE**  


```txt
Cognism Data Report

Query Parameters:
  Keywords = marketing
  Search fields = articleName, subHeadline, abstract
  Exclusions = 
  Date From = 20.06.2016
  Date To = 20.08.2016
  Annotation = List()
  Source = Financial Times

[1] Dentsu strikes $1.5bn deal with US digital marketing 
firmEID: f995dd4a-5d44-11e6-bb77-a121aa8abd95 | UID: 
1271176 | Date: 08.08.2016 | Author: Arash Massoudi | 
Source: Financial Times 
URL: http://www.ft.com/cms/s/0/f995dd4a-5d44-11e6-bb77-
a121aa8abd95.html

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
  Jerry Buhlmann (Chief Executive Officer) @ Dentsu Aegis 
  Network => We are more about reaching the people you 
  don’t know and they are all about reaching people.
```

This API let's you search for online documents from specific sources using keywords. Some of the current sources include R Newswire, Financial Times and Associated Press. You can specify any keywords you wish and narrow down the search by excluding words, limiting the publishing date and specifying the field within the article that contains the keywords.

Output is returned in text format.


### HTTP Request

<aside class="tag">
<div class="lbl-get">GET</div>
</aside>

`http://api.cognism.io/api/v1/documents/txt?keywords={keywords}&fields={fields}&exclusions={exclusions}&source={source}&dateFrom={date_from}&dateTo={date_to}&annotation={annotation}&accessToken={access_token}&secretKey={secret_key}`


### Query Parameters

Parameter | Description
--------- | ----------- 
keywords | **optional** <br> Keywords for the search, such as marketing, appoints.chief marketing officer or named.chief marketing officer.
fields | **optional** <br> Search fields such as articleName,subHeadline or abstract.
exclusions | **optional** <br> Exclude words from search such as retirement or leaving.
outputFields | **optional** <br> Specify output fields for the search such as headline, URL and abstract.
source | **required** <br> Data source such as PR Newswire, Financial Times or Associated Press.
dateFrom | **optional** <br> Limit search by a start date. Use format dd.MM.yyyy.
dateTo | **optional** <br> Limit search by an end date. Use format dd.MM.yyyy.
annotation | **optional** <br> Document metadata such as subject of the article e.g. subject=PER.
accessToken | **required** <br> Access Token
secretKey | **optional** <br> Secret Key










##Search Documents by Entities

```ruby
api.document.all('20.04.2016',
                  '0.06.2016',
                  'Financial Times',
                  '4',
                  '2',
                  '10',
                  'your_access_token',
                  'your_secret_key')
```

```python
dateFrom = "20.04.2016"
dateTo = "20.06.2016"
source = "Financial Times"
aboutness = "4"
page = "2"
count = "10"
accessToken = "your_access_token"
secretKey = "your_secret_key"

docs = api.Document.all(dateFrom, 
                  dateTo, 
                  source, 
                  aboutness,
                  page,
                  count,
                  accessToken, 
                  secretKey)
```

```shell
$ curl -v 'http://api.cognism.io/api/v2/documents/search?
              dateFrom=20.04.2016&
              dateTo=20.06.2016&
              source=Financial%20Times&
              aboutness=4&
              page=5&
              count=10&
              accessToken=your_access_token& 
              secretKey=your_secret_key'
```



```javascript
url = "http://api.cognism.io/api/v2/documents/search?
              dateFrom=20.04.2016&
              dateTo=20.06.2016&
              source=Financial%20Times&
              aboutness=4&
              page=5&
              count=10&
              accessToken=your_access_token& 
              secretKey=your_secret_key";

xmlHttp.open( "GET", url );
```

> **RESPONSE EXAMPLE**  


```txt
Cognism Data Report

Query Parameters:
  Keywords = ORGANIZATION:IBM
  Search fields = body
  Exclusions = None
  Date From = 01.01.2016
  Date To = 20.08.2016
  Annotation = All
  Source = PR Newswire


[1] 6mm x 6mm, Longsys Technology launches the worlds 
smallest IoT WiFi SiP module
EID: 8667390 | UID: 1057574 | Date: Mon Jan 04 14:00:00 
UTC 2016 | Author: Some(Longsys Technology Co., Ltd.) | 
Source: PR Newswire
URL: Some(http://www.prnewswire.com/news-releases/36411
0661.html)

Abstract:
<p>LAS VEGAS, Jan. 4, 2016 /PRNewswire/ -- Longsys 
  Technology, the leading solutions provider of 
  Internet of Things (IoT), just announced the worlds 
  smallest IoT WiFi Silicon-in-package (SiP) module, 
  LTP0201.</p>

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
  ORGANIZATION=IBM (4.0)
  ORGANIZATION=AES (1.0)
  PERSON=Xiaogang Li (2.0)
    Ref: ORGANIZATION=Las Vegas (0.0)
    Ref: PHONE=+1 (10.0)
    Ref: EMAIL=iotsales@longsys.com (5.0)
  PHONE=+1 (10.0)
  QUOTE=In 5 years, more than 60 % IoT and wearable 
  products will incorporate SiP modules because of its 
  mini size and more consistent RF performance (1.0)
    Ref: PERSON=Dave Pang (7.0)
      Ref: TITLE=General Manager (1.0)
        Ref: COGNISM-ID = General Manager => id=73b52b17-
        8d63-435c-b121-c84c6ad9e827
      Ref: ORGANIZATION=Longsys Technology Co., Ltd. (6.0)
      Ref: PHONE=+1 (10.0)
      Ref: EMAIL=iotsales@longsys.com (5.0)
```

This API let's you search for online documents with specified entities. Current entities include ORGANIZATION, PERSON and LOCATION. The relevance of these entities in the article can be defined by the aboutness value, where 10 indicates high relevance. The output quantity can also be specified using the page and count variables. All data is returned in pages which include a specific amount of results each, i.e. count.


### HTTP Request

<aside class="tag">
<div class="lbl-get">GET</div>
</aside>

`http://api.cognism.io/api/v2/documents/search?dateFrom={date_from}&dateTo={date_to}&tag={tag}&term={term}&source={source}&aboutness={aboutness}&page={page}&count={count}&accessToken={access_token}&secretKey={security_key}`



### Query Parameters

Parameter | Description
--------- | ----------- 
dateFrom | **required** <br> Limit search by a start date. Use format dd.MM.yyyy.
dateTo | **required** <br> Limit search by an end date. Use format dd.MM.yyyy.
tag | **optional** <br> Search by tags ORGANIZATION, PERSON or LOCATION
term | **required** <br> Search term such as the name of an organization.
source | **required** <br> Data source such as PR Newswire, Financial Times or Associated Press.
aboutness | **optional** <br> A score given based on the relevance of the entity in the news article. Range set between 1 and 10 where 1 is the least relevant and 10 the most relevant.
page | **required** <br> Data is returned in pages, set here the number of pages retrieved by the search.
count | **required** <br> The number of results displayed on a single page.
accessToken | **required** <br> Access Token
secretKey | **optional** <br> Secret Key
