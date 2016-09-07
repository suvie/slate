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

Cognism API's can return information about a specific company. The company object includes information such as the company's location, size and industry.

Parameter | Description
--------- | ----------- 
city | **string** <br> The city the company is based in.
name | **string** <br> Name of the company.
zip | **string** <br> Zip code or post code of company.
country | **string** <br> The country the company is based in.
industry | **string** <br> The industry the company operates in.
site | **string** <br> Company home website.
id | **integer** <br> Numerical company id.
path | **string** <br> Company path name. 
type | **string** <br> The type of business entity such as public company, limited company etc.
region | **string** <br> The region of company head quarters.
street address | **string** <br> Address of company head quarters.
size | **string** <br> Company size. How many people are employed by the company.




##Get By Name

```ruby
api.company.find('IBM')
```

```python
api.Company.find('IBM')
```

```shell
$ curl -v http://api.cognism.io/api/v1/company/IBM
  -H "X-API-AccessToken: access_token" 
  -H "X-API-SecretKey: secret_key" 
```

```javascript
const comp = require('comp');

let api = comp.authorize('your_access_token');
let company = api.company.get('IBM');
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

This API let's you search for information about a company. Use the name of the company in the API to access information such as the company's size, its location and the industry it operates in.



### HTTP Request

<aside class="tag">
<div class="lbl-get">GET</div>
</aside>

`http://api.cognism.io/api/v1/company/{name}`


### Query Parameters

Parameter | Description
--------- | ----------- 
name | **required** <br> Name of the company being searched.
X-API-AccessToken | **required** <br> Access Token
X-API-AccessToken | **optional** <br> Secret Key
