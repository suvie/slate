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

This object describes an event, or a Sales Trigger, that has taken place. This could be, for example, an employee moving into a different company. This object includes information about the time of the event, the people and companies involved, as well as any more specific information such as the new job title and relevant URL's.


Parameter | Description
--------- | ----------- 
id | **string** <br> Event id.
at | **integer** <br> Date in UNIX time when event occurred.
date | **string** <br> Date when event occurred.
type | **string** <br> Type of data, such as job-join, job-leave, job-move, location-move, person-mention, quote, 310 (Article Mentions) or 330 (Brand Mentions).
org | **string** <br> Name of the company.
orgInfo | **string** <br> Other information about the company.
loc | **string** <br> Geographical location of the company.
old_loc | **string** <br> Previous location of the company.
source | **string** <br> Data source such as social.
meta | **string** <br> Meta data such as the date the event was created.
typeName | **string** <br> The type of event that took place such as an external movement.
orgToInfo | **string** <br> Information about the new position the employee has moved to.
orgFromInfo | **string** <br> Information about the position the employee has moved from.

EMPLOYEE

Parameter | Description
--------- | ----------- 
city | **string** <br> City the employee is located at.
first name | **string** <br> Employee's first name.
last name | **string** <br> Employee's last name.
name | **string** <br> Full name of the employee.
title | **string** <br> Employee job title.
url | **string** <br> Contact URL for employee.
country | **string** <br> Employee's country of residence.
organisation | **string** <br> Employee's current employer.
state | **string** <br> State or province the employee lives in.
old job title | **string** <br> Previous job title of the employee.
photo url | **string** <br> URL to a photo of the employee.
old organisation | **string** <br> Previous employer of the employee.
age | **integer** <br> Employee's age.
previous | **integer** <br> Start and end dates for previous employment.






##Get Event Stream

```ruby
api.event.all(  '20.04.2016',
                '20.06.2016',
                'org=IBM;',
                '2',
                '10')
```

```python
dateFrom = "20.04.2016"
dateTo = "20.06.2016"
rule = "org=IBM;"
page = "2"
count = "10"

event = api.Event.all(dateFrom, 
                  dateTo, 
                  rule,
                  page, 
                  count)
```

```shell
$ curl -v 'http://api.cognism.io/api/v1/events/stream?
            dateFrom=20.04.2016&
            dateTo=20.06.2016&
            rule=org%3DIBM%3B&
            page=5&
            count=10'

  -H "X-API-AccessToken: access_token" 
  -H "X-API-SecretKey: secret_key" 
```

```javascript
url = "http://api.cognism.io/api/v1/events/stream?
            dateFrom=20.04.2016&
            dateTo=20.06.2016&
            rule=org%3DIBM%3B&
            page=5&
            count=10";

xmlHttp.open( "GET", url );
xmlHttp.setRequestHeader('X-API-AccessToken','your_access_token');
xmlHttp.setRequestHeader('X-API-SecretKey','your_secret_key');
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

This API allows you to specify a custom query rule to search for events that have taken place. The search can be limited further by selecting earliest and latest dates that the event could have taken place. The output quantity can also be specified using the page and count variables. All data is returned in pages which include a specific amount of results each, i.e. count.

The output is returned in JSON format.


### HTTP Request

<aside class="tag">
<div class="lbl-get">GET</div>
</aside>

`http://api.cognism.io/api/v1/events/stream?dateFrom={date_from}&dateTo={date_to}&rule={query_rule}&page={page}&count={count}`


### Query Parameters

Parameter | Description
--------- | ----------- 
dateFrom | **optional** <br> Limit search by a start date. Use format dd.MM.yyyy.
dateTo | **optional** <br> Limit search by an end date. Use format dd.MM.yyyy.
rule | **optional** <br> Query rule such as type=job-join|job-leave;org=IBM;employee.title=valuelist(mediaradar-jobtitle).
page | **optional** <br> Data is returned in pages, set here the number of pages retrieved by the search. Default values is 0.
count | **optional** <br> The number of results displayed on a single page. Default value is 50.
X-API-AccessToken | **required** <br> Access Token
X_API-SecretKey | **optional** <br> Secret Key








##Get Event Stream as CSV File

```ruby
api.event.all(  '20.04.2016',
                '20.06.2016',
                'org=IBM;',
                '2',
                '10',
                'your_access_token',
                'your_secret_key')
```

```python
dateFrom = "20.04.2016"
dateTo = "20.06.2016"
rule = "org=IBM;"
page = "2"
count = "10"
accessToken = "your_access_token"
secretKey = "your_secret_key"

event = api.Event.all(dateFrom, 
                  dateTo, 
                  rule,
                  page, 
                  count,
                  accessToken,
                  secretKey)
```

```shell
$ curl -v 'http://api.cognism.io/api/v1/events/stream/csv?
            dateFrom=20.04.2016&
            dateTo=20.06.2016&
            rule=org%3DIBM%3B&
            page=5&
            count=10&
            accessToken=your_access_token& 
            secretKey=your_secret_key'
```

```javascript
url = "http://api.cognism.io/api/v1/events/stream/csv?
            dateFrom=20.04.2016&
            dateTo=20.06.2016&
            rule=org%3DIBM%3B&
            page=5&
            count=10&
            accessToken=your_access_token& 
            secretKey=your_secret_key";

xmlHttp.open( "GET", url );
```

> **RESPONSE EXAMPLE**  


```txt
CSV File

Data returned with rule org=IBM
Event ID;
Date;
Event Type;
Employee Name;
Employee Job Title;
Employee Estimated Age;
Employee URL;
Organization Name;
rganization ID;
Client Organization ID;
Organization Industry;
Organization Website;
Organization Founded;
Organization Type;
Organization Size;
Region;
Country;
State;
City;
```

This API allows you to specify a custom query rule to search for events that have taken place. The search can be limited further by selecting earliest and latest dates that the event could have taken place. The output quantity can also be specified using the page and count variables. All data is returned in pages which include a specific amount of results each, i.e. count.

The output is returned in CSV format.


### HTTP Request

<aside class="tag">
<div class="lbl-get">GET</div>
</aside>

`http://api.cognism.io/api/v1/events/stream/csv?dateFrom={date_from}&dateTo={date_to}&rule={query_rule}&page={page}&count={count}&accessToken={access_token}&secretKey={secret_key}`


### Query Parameters

Parameter | Description
--------- | ----------- 
dateFrom | **optional** <br> Limit search by a start date. Use format dd.MM.yyyy.
dateTo | **optional** <br> Limit search by an end date. Use format dd.MM.yyyy.
rule | **optional** <br> Query rule such as type=job-join|job-leave;org=IBM;employee.title=valuelist(mediaradar-jobtitle)
page | **optional** <br> Data is returned in pages, set here the number of pages retrieved by the search. Default values is 0.
count | **optional** <br> The number of results displayed on a single page. Default value is 50.
accessToken | **required** <br> Access Token
secretKey | **optional** <br> Secret Key








##Search Event Stream


```ruby
api.event.create('your_access_token', 'your_secret_key', { 
            dateFrom: '20.04.2016',
            dateTo: '20.05.2016',
            page: '5',
            count: '10',
            pipeline: [{name: 'string',
                        operator: 'eq',
                        values: ['string'],
                        phase: 'match'
                      }]
            })
```

```python
api.Event.create("your_access_token", "your_secret_key", { 
            "dateFrom": "20.04.2016",
            "dateTo": "20.05.2016",
            "page": "5",
            "count": "10",
            "pipeline": [{"name": "string",
                          "operator": "eq",
                          "values": ["string"],
                          "phase": "match"
                        }]
            })
```

```javascript
url = "http://api.cognism.io/api/v1/events/stream/search?
            accessToken=your_access_token& 
            secretKey=your_secret_key";
data = '{ "dateFrom": "20.04.2016",
            "dateTo": "20.05.2016",
            "page": 5,
            "count": 10,
            "pipeline": [{"name": "string",
                          "operator": "eq",
                          "values": ["string"],
                          "phase": "match"
                        }]
          }';

xmlHttp.open( "POST", url );
xmlHttp.setRequestHeader('Content-type','application/json');
```


```shell
$ curl 'http://api.cognism.io/api/v1/events/stream/search?
            accessToken=your_access_token& 
            secretKey=your_secret_key'

  -H "Content-type: application/json" 
  --request POST 
  --data '{ "dateFrom": "20.04.2016",
            "dateTo": "20.05.2016",
            "page": 5,
            "count": 10,
            "pipeline": [{"name": "string",
                          "operator": "eq",
                          "values": ["string"],
                          "phase": "match"
                        }]
          }' 

```



This API allows you to search the event stream. The search can be limited further by selecting earliest and latest dates that the event could have taken place. The output quantity can also be specified using the page and count variables. All data is returned in pages which include a specific amount of results each, i.e. count.


### HTTP Request

<aside class="tag">
<div class="lbl-post">POST</div>
</aside>

`http://api.cognism.io/api/v1/events/stream/search?accessToken={access_token}&secretKey={secret_key}`


### Query Parameters

Parameter | Description
--------- | ----------- 
accessToken | **required** <br> Access Token
secretKey | **optional** <br> Secret Key
dateFrom | **optional** <br> Limit search by a start date. Use format dd.MM.yyyy.
dateTo | **optional** <br> Limit search by an end date. Use format dd.MM.yyyy.
page | **required** <br> Data is returned in pages, set here the number of pages retrieved by the search.
count | **required** <br> The number of results displayed on a single page.

