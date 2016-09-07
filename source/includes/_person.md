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

Cognism API's can return information about a specific person. The person object includes information such as the person's employment and education history as well as their skills, certifications and group memberships.

Parameter | Description
--------- | ----------- 
city | **string** <br> The city the person works at.
vc | **integer** <br> Unix timestamp of the document.
ver | **integer** <br> Document version number.
groups | **string** <br> List of groups that the person is a member of.
cc | **string** <br> Country code such as "uk"
country | **string** <br> The country the person is based at.
current | **string** <br> Name of current employer.
skills | **string** <br> List of skills this person has.
state | **string** <br> The state or province this person is based in.
birth date | **integer** <br> Person's date of birth.
fullname | **string** <br> Person's full name.
topcard | **string** <br> Overview of the person's current situation.
uid | **string** <br> Person's user id.

EXPERIENCE

Parameter | Description
--------- | ----------- 
to | **string** <br> Date the person finished work at the company. Blank if this is the person's current role.
company | **string** <br> Name of the company that employed the person.
from | **string** <br> Date the person started work at the company.
description | **string** <br> Description of the person's role at the company.
name | **string** <br> Person's job title in this role.

CERTIFICATIONS

Parameter | Description
--------- | ----------- 
to | **integer** <br> End date for finishing the certificate.
company | **string** <br> Name of the company that employed the person.
from | **integer** <br> Date the person gained the certificate. Alternatively the date the person started working on the certificate, taken it took an extended period of time.
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
api.person.find(  'Mary',
                'Mitchell',
                'IBM')
```

```python
firstName = "Mary"
lastName = "Mitchell"
company = "IBM"

person = api.Person.find(firstName,
                    lastName,
                    company)
```

```shell
$ curl -v 'http://api.cognism.io/api/v1/person?
            firstName=Mary&
            lastName=Mitchell&
            company=IBM

  -H "X-API-AccessToken: access_token" 
  -H "X-API-SecretKey: secret_key"
```

```javascript

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
This API let's you search for information on a person. The search can be defined by a first name, last name or a company name and the response object returns information about the person's employment history as well as their skills, certifications and education.


### HTTP Request

<aside class="tag">
<div class="lbl-get">GET</div>
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