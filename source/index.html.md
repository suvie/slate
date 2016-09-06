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
  - company
  - documents
  - events
  - person
  - subscription
  - websockets
  - errors

search: true
---

# Introduction

The Cognism API is used to submit lead generation, lead enrichment and sales management requests. The API is built using RESTful endpoints and standard HTTP verbs.

For authentification API tokens are used which can be obtained from your Cognism Customer Success Manager.

Most API responses return JSON, with the exception of documents, which can be returned in text format, or events, which are also available as a CSV file. All POST requests require a JSON input. 

Examples for language bindings are provided in Shell, Ruby, Python and Javascript on the right hand tab.


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
curl "api_endpoint_here"
  -H "X-API-AccessToken: your_access_token" 
  -H "X-API-SecretKey: your_secret_key" 

OR

curl 'http://api_endpoint_here?
          accessToken=your_access_token&
          secretKey=your_secret_key'
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('0000-0000-0000');
```

> Make sure to replace `your_access_token` and `your_secret_key` with API keys obtained from Cognism.

Cognism uses API keys to allow access to the API's. There are two types of keys: Access Token and Secret Key, which are one time generated tokens privded by Cognism. Most API's will work using the Access Token, however, some will require both keys. If you do not have your Access Token or Secret Key, please as your Customer Success Manager.

The documentation below defines these keys as either accessTokens and secretKeys or X-API-AccessTokens and X-API-SecretKeys. The keys themselves are the same, but the latter are used solely in API headers when the first are added as input parameters in certain GET requests. The documentation will provide information on the exact authentification method used for each API.