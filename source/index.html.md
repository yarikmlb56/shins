---
title: API for Tax Calculator v0.0.2 alfa, Nov 2019
language_tabs:
  - ruby: Ruby
  - python: Python
toc_footers: []
includes: []
search: false
highlight_theme: darkula
headingLevel: 2

---

<!-- Generator: Widdershins v3.6.6 -->

<h1 id="api-for-tax-calculator">API for Tax Calculator v0.0.2 alfa, Nov 2019</h1>

> Scroll down for code samples, example requests and responses. Select a language for code samples from the tabs above or the mobile navigation menu.

Vertex API for Tax Calculator.

Base URLs:

* <a href="http://localhost:8004/">http://localhost:8004/</a>

Web: <a href="http://www.vertex.com">API Support</a> 
License: <a href="https://www.apache.org/licenses/LICENSE-2.0.html">Apache 2.0</a>

# Authentication

- HTTP Authentication, scheme: bearer 

* API Key (apiKeyAuth)
    - Parameter Name: **apikey**, in: header. API key to authorize requests.

<h1 id="api-for-tax-calculator-notification-template">Notification template</h1>

## Return registered templates.

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'apikey' => 'API_KEY'
}

result = RestClient.get 'http://localhost:8004/templates',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'apikey': 'API_KEY'
}

r = requests.get('http://localhost:8004/templates', headers = headers)

print(r.json())

```

`GET /templates`

Returns registered templates for current sale channel.

> Example responses

> 200 Response

```json
{
  "templates": [
    {
      "id": 624,
      "name": "email",
      "body": " Dear {name}, Your account is activated."
    }
  ]
}
```

<h3 id="return-registered-templates.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|OK|Returns collectin of the templates for 
current sale channel.|[Templates](#schematemplates)|
|404|Not Found|Unable to find any template.|[Errors](#schemaerrors)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKeyAuth
</aside>

## Register new template.

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'apikey' => 'API_KEY'
}

result = RestClient.post 'http://localhost:8004/templates',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'apikey': 'API_KEY'
}

r = requests.post('http://localhost:8004/templates', headers = headers)

print(r.json())

```

`POST /templates`

The endpoint is used to register new template
for current sale channel.

> Body parameter

```json
{
  "id": 624,
  "name": "email",
  "body": " Dear {name}, Your account is activated."
}
```

<h3 id="register-new-template.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[Template](#schematemplate)|true|none|

> Example responses

> 201 Response

```json
{
  "id": 624,
  "name": "email",
  "body": " Dear {name}, Your account is activated."
}
```

<h3 id="register-new-template.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|Created|Template is added successfully.|[Template](#schematemplate)|
|400|Bad Request|Unable to register template.|[Errors](#schemaerrors)|
|404|Not Found|Unable to register template. 
Template with the same name is already registered.|[Errors](#schemaerrors)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKeyAuth
</aside>

## Get template.

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'apikey' => 'API_KEY'
}

result = RestClient.get 'http://localhost:8004/templates/{templateId}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'apikey': 'API_KEY'
}

r = requests.get('http://localhost:8004/templates/{templateId}', headers = headers)

print(r.json())

```

`GET /templates/{templateId}`

Returns template with defined id. 

<h3 id="get-template.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|templateId|path|string|true|Template id.|

#### Detailed descriptions

**templateId**: Template id.

> Example responses

> 200 Response

```json
{
  "id": 624,
  "name": "email",
  "body": " Dear {name}, Your account is activated."
}
```

<h3 id="get-template.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|OK|Template|[Template](#schematemplate)|
|404|Not Found|Unable to find template.|[Errors](#schemaerrors)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKeyAuth
</aside>

## Update template.

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'apikey' => 'API_KEY'
}

result = RestClient.patch 'http://localhost:8004/templates/{templateId}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'apikey': 'API_KEY'
}

r = requests.patch('http://localhost:8004/templates/{templateId}', headers = headers)

print(r.json())

```

`PATCH /templates/{templateId}`

Makes changes in the defined template.

> Body parameter

```json
{
  "id": 624,
  "name": "email",
  "body": " Dear {name}, Your account is activated."
}
```

<h3 id="update-template.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|templateId|path|string|true|Template id.|
|body|body|[Template](#schematemplate)|true|none|

#### Detailed descriptions

**templateId**: Template id.

> Example responses

> 201 Response

```json
{
  "id": 624,
  "name": "email",
  "body": " Dear {name}, Your account is activated."
}
```

<h3 id="update-template.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|Created|Template is updated successfully.|[Template](#schematemplate)|
|404|Not Found|Unable to update template.|[Errors](#schemaerrors)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKeyAuth
</aside>

## Delete template.

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'apikey' => 'API_KEY'
}

result = RestClient.delete 'http://localhost:8004/templates/{templateId}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'apikey': 'API_KEY'
}

r = requests.delete('http://localhost:8004/templates/{templateId}', headers = headers)

print(r.json())

```

`DELETE /templates/{templateId}`

Deletes the defined template. 

<h3 id="delete-template.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|templateId|path|string|true|Template id.|

#### Detailed descriptions

**templateId**: Template id.

> Example responses

> 200 Response

```json
{
  "id": 624,
  "name": "email",
  "body": " Dear {name}, Your account is activated."
}
```

<h3 id="delete-template.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|OK|Template is deleted successfully.|[Template](#schematemplate)|
|404|Not Found|Template not found.|[Errors](#schemaerrors)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKeyAuth
</aside>

## Send notification.

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'apikey' => 'API_KEY'
}

result = RestClient.post 'http://localhost:8004/templates/{templateId}/send',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'apikey': 'API_KEY'
}

r = requests.post('http://localhost:8004/templates/{templateId}/send', headers = headers)

print(r.json())

```

`POST /templates/{templateId}/send`

The endpoint is used to notify current \
sale channel by e-mail. 

> Body parameter

```json
{
  "email": "user@vertex.com",
  "subject": "Account confirmation",
  "parameters": [
    {
      "name": "name",
      "value": "value"
    }
  ]
}
```

<h3 id="send-notification.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|templateId|path|string|true|Template id.|
|body|body|[Message](#schemamessage)|true|none|

#### Detailed descriptions

**templateId**: Template id.

> Example responses

> 201 Response

```json
{
  "email": "user@vertex.com",
  "subject": "Account confirmation",
  "parameters": [
    {
      "name": "name",
      "value": "value"
    }
  ]
}
```

<h3 id="send-notification.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|Created|Notification sent successfully.
Returns fulfilled message.|[Message](#schemamessage)|
|400|Bad Request|Unable to send notification.|[Errors](#schemaerrors)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKeyAuth
</aside>

<h1 id="api-for-tax-calculator-account-management">Account Management</h1>

## Create new account.

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'platform' => 'string'
}

result = RestClient.post 'http://localhost:8004/accounts',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'platform': 'string'
}

r = requests.post('http://localhost:8004/accounts', headers = headers)

print(r.json())

```

`POST /accounts`

The endpoint is used to create new account.
* The endpoint can be invoked by platform
in this case platform API key should be 
passed as token.
* Either the endpoint can be invoked without 
token. In this case sale channel
creates its own account.

> Body parameter

```json
{
  "id": 656,
  "name": "Cofe shop",
  "email": "shop@vertex.com",
  "password": "password"
}
```

<h3 id="create-new-account.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|platform|header|string|false|Platform API key.|
|body|body|[Account](#schemaaccount)|true|none|

#### Detailed descriptions

**platform**: Platform API key.

> Example responses

> 201 Response

```json
{
  "id": 656,
  "name": "Cofe shop",
  "email": "shop@vertex.com",
  "password": "password"
}
```

<h3 id="create-new-account.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|Created|Account created successfully.|[Account](#schemaaccount)|
|400|Bad Request|Unable to create account.|[Errors](#schemaerrors)|
|409|Conflict|Account already exists.|[Errors](#schemaerrors)|

<aside class="success">
This operation does not require authentication
</aside>

## Update an account

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.patch 'http://localhost:8004/accounts',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.patch('http://localhost:8004/accounts', headers = headers)

print(r.json())

```

`PATCH /accounts`

Updates account password.

> Body parameter

```json
{
  "id": 656,
  "name": "Cofe shop",
  "email": "shop@vertex.com",
  "password": "password"
}
```

<h3 id="update-an-account-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[Account](#schemaaccount)|true|none|

> Example responses

> 204 Response

```json
{
  "id": 656,
  "name": "Cofe shop",
  "email": "shop@vertex.com",
  "password": "password"
}
```

<h3 id="update-an-account-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|204|No Content|Account updated successfully.|[Account](#schemaaccount)|
|400|Bad Request|Unable to update account.|[Errors](#schemaerrors)|
|404|Not Found|Account not found.|[Errors](#schemaerrors)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
jwtAuth, apiKeyAuth
</aside>

## Get account information

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'apikey' => 'API_KEY'
}

result = RestClient.get 'http://localhost:8004/accounts/info',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'apikey': 'API_KEY'
}

r = requests.get('http://localhost:8004/accounts/info', headers = headers)

print(r.json())

```

`GET /accounts/info`

Returns all account information which 
tax calculation requires for defined account.
For sale platform email as a query can be 
used as an account identifier.

<h3 id="get-account-information-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|email|query|string|false|Account identifier.|

#### Detailed descriptions

**email**: Account identifier.

> Example responses

> 200 Response

```json
{
  "account": {
    "id": 656,
    "name": "Cofe shop",
    "email": "shop@vertex.com",
    "password": "password"
  },
  "businessInfo": {
    "id": 234,
    "businessName": "Cofe shop LTD",
    "fedTaxId": "2321-2323-2132"
  },
  "locations": {
    "locations": [
      {
        "id": 653,
        "type": "administrative",
        "city": "KNG OF PRUSSA",
        "state": "PA",
        "zip": "19406",
        "zipExt": "1101",
        "addressLine1": "875 MANCILL MILL RD"
      }
    ]
  }
}
```

<h3 id="get-account-information-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|OK|Returns account information.|[AccountInfo](#schemaaccountinfo)|
|404|Not Found|Unable to find an account.|[Errors](#schemaerrors)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKeyAuth
</aside>

## Get a link for resetting account password.

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.post 'http://localhost:8004/accounts/{email}/resetPassword',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.post('http://localhost:8004/accounts/{email}/resetPassword', headers = headers)

print(r.json())

```

`POST /accounts/{email}/resetPassword`

The endpoint is used to generate temporary link which 
can be used for resetting account password.

<h3 id="get-a-link-for-resetting-account-password.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|email|path|string|true|Account identifier.|

#### Detailed descriptions

**email**: Account identifier.

> Example responses

> 201 Response

```json
"http://192.168.0.17/api/v1.2/nextPage?size=12"
```

<h3 id="get-a-link-for-resetting-account-password.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|Created|Link created successfully.|[Link](#schemalink)|
|400|Bad Request|Unable to create a link.|[Errors](#schemaerrors)|
|409|Conflict|Unble to find account.|[Errors](#schemaerrors)|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="api-for-tax-calculator-token-management">Token Management</h1>

## Get active tokens

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'apikey' => 'API_KEY'
}

result = RestClient.get 'http://localhost:8004/tokens',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'apikey': 'API_KEY'
}

r = requests.get('http://localhost:8004/tokens', headers = headers)

print(r.json())

```

`GET /tokens`

Returns collection of active tokens for current sale point.

<h3 id="get-active-tokens-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|page|query|integer|false|Defines page number.|
|size|query|integer|false|Defines number of the records for single page. |

#### Detailed descriptions

**page**: Defines page number.

**size**: Defines number of the records for single page. 

> Example responses

> 200 Response

```json
{
  "pagination": {
    "self": "http://vertex.com/api/v1.2/logs?page=30&size=10",
    "prev": "http://vertex.com/api/v1.2/logs?page=29&size=10",
    "next": "http://vertex.com/api/v1.2/logs?page=31&size=10",
    "first": "http://vertex.com/api/v1.2/logs?page=1&size=10",
    "last": "http://vertex.com/api/v1.2/logs?page=80&size=10"
  },
  "fetchInfo": {
    "totalElements": 5000,
    "size": 10,
    "totslPages": 500,
    "page": 3
  },
  "tokens": [
    {
      "type": "sandbox",
      "token": "1324325543234324",
      "created": "2019-08-23T12:23:56TZ2"
    }
  ]
}
```

<h3 id="get-active-tokens-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|OK|Returns token.|[Tokens](#schematokens)|
|404|Not Found|Unable to return tokens.|[Errors](#schemaerrors)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKeyAuth
</aside>

## Generate token

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'apikey' => 'API_KEY'
}

result = RestClient.post 'http://localhost:8004/tokens',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'apikey': 'API_KEY'
}

r = requests.post('http://localhost:8004/tokens', headers = headers)

print(r.json())

```

`POST /tokens`

Creates a new token for API call.

> Body parameter

```json
{
  "type": "public"
}
```

<h3 id="generate-token-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[TokenType](#schematokentype)|true|none|

> Example responses

> 201 Response

```json
{
  "type": "sandbox",
  "token": "1324325543234324",
  "created": "2019-08-23T12:23:56TZ2"
}
```

<h3 id="generate-token-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|Created|Returns a token.|[Token](#schematoken)|
|400|Bad Request|Unable to create token.|[Errors](#schemaerrors)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKeyAuth, jwtAuth
</aside>

## Revoke the token.

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'apikey' => 'API_KEY'
}

result = RestClient.delete 'http://localhost:8004/tokens/{token}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'apikey': 'API_KEY'
}

r = requests.delete('http://localhost:8004/tokens/{token}', headers = headers)

print(r.json())

```

`DELETE /tokens/{token}`

The method allows to deactivate the token.
But a sale channel should have as minimum one 
token for production environment and one for sandbox.
They can't be revoked.

<h3 id="revoke-the-token.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|token|path|string|true|none|

> Example responses

> 200 Response

```json
{
  "type": "sandbox",
  "token": "1324325543234324",
  "created": "2019-08-23T12:23:56TZ2"
}
```

<h3 id="revoke-the-token.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|OK|The token revoken successfully.|[Token](#schematoken)|
|404|Not Found|Unable to revoke token.|[Errors](#schemaerrors)|
|409|Conflict|Unable to revoke the last token.|[Errors](#schemaerrors)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKeyAuth
</aside>

<h1 id="api-for-tax-calculator-contact-information">Contact Information</h1>

## Get contact information.

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'apikey' => 'API_KEY'
}

result = RestClient.get 'http://localhost:8004/contacts',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'apikey': 'API_KEY'
}

r = requests.get('http://localhost:8004/contacts', headers = headers)

print(r.json())

```

`GET /contacts`

The endpoint returns contact information.

> Example responses

> 200 Response

```json
{
  "location": {
    "id": 653,
    "type": "administrative",
    "city": "KNG OF PRUSSA",
    "state": "PA",
    "zip": "19406",
    "zipExt": "1101",
    "addressLine1": "875 MANCILL MILL RD"
  },
  "emails": [
    "string"
  ],
  "phones": [
    "string"
  ],
  "id": 464,
  "title": "Mr",
  "name": "Oleksiy",
  "lastName": "Luchkovskiy"
}
```

<h3 id="get-contact-information.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|OK|Returns contact information.|[ContactInfo](#schemacontactinfo)|
|404|Not Found|Contact information not found.|[Errors](#schemaerrors)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKeyAuth
</aside>

## Add contact information.

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'apikey' => 'API_KEY'
}

result = RestClient.post 'http://localhost:8004/contacts',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'apikey': 'API_KEY'
}

r = requests.post('http://localhost:8004/contacts', headers = headers)

print(r.json())

```

`POST /contacts`

The endpoint is used to add contact information.

> Body parameter

```json
{
  "location": {
    "id": 653,
    "type": "administrative",
    "city": "KNG OF PRUSSA",
    "state": "PA",
    "zip": "19406",
    "zipExt": "1101",
    "addressLine1": "875 MANCILL MILL RD"
  },
  "emails": [
    "string"
  ],
  "phones": [
    "string"
  ],
  "id": 464,
  "title": "Mr",
  "name": "Oleksiy",
  "lastName": "Luchkovskiy"
}
```

<h3 id="add-contact-information.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[ContactInfo](#schemacontactinfo)|true|none|

> Example responses

> 201 Response

```json
{
  "location": {
    "id": 653,
    "type": "administrative",
    "city": "KNG OF PRUSSA",
    "state": "PA",
    "zip": "19406",
    "zipExt": "1101",
    "addressLine1": "875 MANCILL MILL RD"
  },
  "emails": [
    "string"
  ],
  "phones": [
    "string"
  ],
  "id": 464,
  "title": "Mr",
  "name": "Oleksiy",
  "lastName": "Luchkovskiy"
}
```

<h3 id="add-contact-information.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|Created|Contact information added successfully.|[ContactInfo](#schemacontactinfo)|
|400|Bad Request|Unable to add contact information.|[Errors](#schemaerrors)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKeyAuth
</aside>

## Get contact information

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'apikey' => 'API_KEY'
}

result = RestClient.get 'http://localhost:8004/contacts/{contactId}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'apikey': 'API_KEY'
}

r = requests.get('http://localhost:8004/contacts/{contactId}', headers = headers)

print(r.json())

```

`GET /contacts/{contactId}`

The endpoint returns contact information.

<h3 id="get-contact-information-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|contactId|path|integer|true|none|

> Example responses

> 200 Response

```json
{
  "location": {
    "id": 653,
    "type": "administrative",
    "city": "KNG OF PRUSSA",
    "state": "PA",
    "zip": "19406",
    "zipExt": "1101",
    "addressLine1": "875 MANCILL MILL RD"
  },
  "emails": [
    "string"
  ],
  "phones": [
    "string"
  ],
  "id": 464,
  "title": "Mr",
  "name": "Oleksiy",
  "lastName": "Luchkovskiy"
}
```

<h3 id="get-contact-information-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|OK|Returns contact information.|[ContactInfo](#schemacontactinfo)|
|404|Not Found|Unable to add contact information.|[Errors](#schemaerrors)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKeyAuth
</aside>

## Update contact information

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'apikey' => 'API_KEY'
}

result = RestClient.patch 'http://localhost:8004/contacts/{contactId}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'apikey': 'API_KEY'
}

r = requests.patch('http://localhost:8004/contacts/{contactId}', headers = headers)

print(r.json())

```

`PATCH /contacts/{contactId}`

The endpoint is used to update contact information.

> Body parameter

```json
{
  "location": {
    "id": 653,
    "type": "administrative",
    "city": "KNG OF PRUSSA",
    "state": "PA",
    "zip": "19406",
    "zipExt": "1101",
    "addressLine1": "875 MANCILL MILL RD"
  },
  "emails": [
    "string"
  ],
  "phones": [
    "string"
  ],
  "id": 464,
  "title": "Mr",
  "name": "Oleksiy",
  "lastName": "Luchkovskiy"
}
```

<h3 id="update-contact-information-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|contactId|path|string|true|none|
|body|body|[ContactInfo](#schemacontactinfo)|true|none|

> Example responses

> 204 Response

```json
{
  "location": {
    "id": 653,
    "type": "administrative",
    "city": "KNG OF PRUSSA",
    "state": "PA",
    "zip": "19406",
    "zipExt": "1101",
    "addressLine1": "875 MANCILL MILL RD"
  },
  "emails": [
    "string"
  ],
  "phones": [
    "string"
  ],
  "id": 464,
  "title": "Mr",
  "name": "Oleksiy",
  "lastName": "Luchkovskiy"
}
```

<h3 id="update-contact-information-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|204|No Content|Contact information updated successfully|[ContactInfo](#schemacontactinfo)|
|400|Bad Request|Unable to update contact information.|[Errors](#schemaerrors)|
|404|Not Found|Unable to update contact information, 
account or contact information not found.|[Errors](#schemaerrors)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKeyAuth
</aside>

<h1 id="api-for-tax-calculator-location">Location</h1>

## Get account locations.

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'apikey' => 'API_KEY'
}

result = RestClient.get 'http://localhost:8004/locations',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'apikey': 'API_KEY'
}

r = requests.get('http://localhost:8004/locations', headers = headers)

print(r.json())

```

`GET /locations`

The endpoint is used to fetch locations 
for current sale point.

> Example responses

> 200 Response

```json
{
  "locations": [
    {
      "id": 653,
      "type": "administrative",
      "city": "KNG OF PRUSSA",
      "state": "PA",
      "zip": "19406",
      "zipExt": "1101",
      "addressLine1": "875 MANCILL MILL RD"
    }
  ]
}
```

<h3 id="get-account-locations.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|OK|Returns location collection|[Locations](#schemalocations)|
|404|Not Found|Locations not found.|[Errors](#schemaerrors)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKeyAuth
</aside>

## Add location.

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'apikey' => 'API_KEY'
}

result = RestClient.post 'http://localhost:8004/locations',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'apikey': 'API_KEY'
}

r = requests.post('http://localhost:8004/locations', headers = headers)

print(r.json())

```

`POST /locations`

The endpoint is used to add location, place
where the sale poit is operated.

Any number of phisical locations and 
only one adminisrative location are possible.

> Body parameter

```json
{
  "id": 653,
  "type": "administrative",
  "city": "KNG OF PRUSSA",
  "state": "PA",
  "zip": "19406",
  "zipExt": "1101",
  "addressLine1": "875 MANCILL MILL RD"
}
```

<h3 id="add-location.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[Location](#schemalocation)|true|none|

> Example responses

> 400 Response

```json
{
  "errors": [
    {
      "code": 1234,
      "message": "Illegal request parameter",
      "details": [
        "details string1",
        "details string2"
      ]
    }
  ]
}
```

<h3 id="add-location.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|Created|Location added successfully|None|
|400|Bad Request|Unable to add location.|[Errors](#schemaerrors)|
|404|Not Found|Unable to add location. 
Location is already added.|[Errors](#schemaerrors)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKeyAuth
</aside>

## Get location.

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'apikey' => 'API_KEY'
}

result = RestClient.get 'http://localhost:8004/locations/{locationId}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'apikey': 'API_KEY'
}

r = requests.get('http://localhost:8004/locations/{locationId}', headers = headers)

print(r.json())

```

`GET /locations/{locationId}`

Returns location with defined id.

<h3 id="get-location.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|locationId|path|string|true|Location Id.|

#### Detailed descriptions

**locationId**: Location Id.

> Example responses

> 200 Response

```json
{
  "id": 653,
  "type": "administrative",
  "city": "KNG OF PRUSSA",
  "state": "PA",
  "zip": "19406",
  "zipExt": "1101",
  "addressLine1": "875 MANCILL MILL RD"
}
```

<h3 id="get-location.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|OK|Returns location|[Location](#schemalocation)|
|404|Not Found|Location not found.|[Errors](#schemaerrors)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKeyAuth
</aside>

## Update location.

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'apikey' => 'API_KEY'
}

result = RestClient.patch 'http://localhost:8004/locations/{locationId}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'apikey': 'API_KEY'
}

r = requests.patch('http://localhost:8004/locations/{locationId}', headers = headers)

print(r.json())

```

`PATCH /locations/{locationId}`

The endpoint is used to update location.

> Body parameter

```json
{
  "id": 653,
  "type": "administrative",
  "city": "KNG OF PRUSSA",
  "state": "PA",
  "zip": "19406",
  "zipExt": "1101",
  "addressLine1": "875 MANCILL MILL RD"
}
```

<h3 id="update-location.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|locationId|path|integer|true|Location Id. |
|body|body|[Location](#schemalocation)|true|none|

#### Detailed descriptions

**locationId**: Location Id. 

> Example responses

> 204 Response

```json
{
  "id": 653,
  "type": "administrative",
  "city": "KNG OF PRUSSA",
  "state": "PA",
  "zip": "19406",
  "zipExt": "1101",
  "addressLine1": "875 MANCILL MILL RD"
}
```

<h3 id="update-location.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|204|No Content|Location is updated successfully.|[Location](#schemalocation)|
|400|Bad Request|Unable to update location.|[Errors](#schemaerrors)|
|404|Not Found|Unable to update location. 
Location not found.|[Errors](#schemaerrors)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKeyAuth
</aside>

## Delete location.

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'apikey' => 'API_KEY'
}

result = RestClient.delete 'http://localhost:8004/locations/{locationId}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'apikey': 'API_KEY'
}

r = requests.delete('http://localhost:8004/locations/{locationId}', headers = headers)

print(r.json())

```

`DELETE /locations/{locationId}`

The endpoint is used to delete location.
If account should have one location as minimum.
It can't be removed.

<h3 id="delete-location.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|locationId|path|string|true|Location Id. |

#### Detailed descriptions

**locationId**: Location Id. 

> Example responses

> 200 Response

```json
{
  "id": 653,
  "type": "administrative",
  "city": "KNG OF PRUSSA",
  "state": "PA",
  "zip": "19406",
  "zipExt": "1101",
  "addressLine1": "875 MANCILL MILL RD"
}
```

<h3 id="delete-location.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|OK|Location deleted successfully.|[Location](#schemalocation)|
|404|Not Found|Location not found.|[Errors](#schemaerrors)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKeyAuth
</aside>

## Standartize location

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'apikey' => 'API_KEY'
}

result = RestClient.post 'http://localhost:8004/locations/standartize',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'apikey': 'API_KEY'
}

r = requests.post('http://localhost:8004/locations/standartize', headers = headers)

print(r.json())

```

`POST /locations/standartize`

Validates location and return result in strandart format.
It helps to keep addresses in unified format and 
find zip extension.

> Body parameter

```json
{
  "id": 653,
  "type": "administrative",
  "city": "KNG OF PRUSSA",
  "state": "PA",
  "zip": "19406",
  "zipExt": "1101",
  "addressLine1": "875 MANCILL MILL RD"
}
```

<h3 id="standartize-location-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[Location](#schemalocation)|false|none|

> Example responses

> 200 Response

```json
{
  "id": 653,
  "type": "administrative",
  "city": "KNG OF PRUSSA",
  "state": "PA",
  "zip": "19406",
  "zipExt": "1101",
  "addressLine1": "875 MANCILL MILL RD"
}
```

<h3 id="standartize-location-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|OK|Returns location is standart format.|[Location](#schemalocation)|
|400|Bad Request|Unable to validate defined location.|[Errors](#schemaerrors)|
|404|Not Found|Unable to validate defined location.
Location has invalid format.|[Errors](#schemaerrors)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKeyAuth
</aside>

<h1 id="api-for-tax-calculator-business-info">Business Info</h1>

## Get business information.

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'apikey' => 'API_KEY'
}

result = RestClient.get 'http://localhost:8004/businessInfo',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'apikey': 'API_KEY'
}

r = requests.get('http://localhost:8004/businessInfo', headers = headers)

print(r.json())

```

`GET /businessInfo`

Returns business information with for current sales point.

> Example responses

> 200 Response

```json
{
  "id": 234,
  "businessName": "Cofe shop LTD",
  "fedTaxId": "2321-2323-2132"
}
```

<h3 id="get-business-information.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|OK|Returns business information.|[BusinessInfo](#schemabusinessinfo)|
|404|Not Found|Business information not found.|[Errors](#schemaerrors)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKeyAuth
</aside>

## Update business information.

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'apikey' => 'API_KEY'
}

result = RestClient.put 'http://localhost:8004/businessInfo',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'apikey': 'API_KEY'
}

r = requests.put('http://localhost:8004/businessInfo', headers = headers)

print(r.json())

```

`PUT /businessInfo`

The endpoint is used to update business information.

> Body parameter

```json
{
  "id": 234,
  "businessName": "Cofe shop LTD",
  "fedTaxId": "2321-2323-2132"
}
```

<h3 id="update-business-information.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[BusinessInfo](#schemabusinessinfo)|true|none|

> Example responses

> 204 Response

```json
{
  "id": 234,
  "businessName": "Cofe shop LTD",
  "fedTaxId": "2321-2323-2132"
}
```

<h3 id="update-business-information.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|204|No Content|Business information updated sucessfully.|[BusinessInfo](#schemabusinessinfo)|
|400|Bad Request|Unable to update business information.|[Errors](#schemaerrors)|
|404|Not Found|Unable to update business information.
Business information not found.|[Errors](#schemaerrors)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKeyAuth
</aside>

## Add business information.

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'apikey' => 'API_KEY'
}

result = RestClient.post 'http://localhost:8004/businessInfo',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'apikey': 'API_KEY'
}

r = requests.post('http://localhost:8004/businessInfo', headers = headers)

print(r.json())

```

`POST /businessInfo`

The endpoint is used to add business information.

> Body parameter

```json
{
  "id": 234,
  "businessName": "Cofe shop LTD",
  "fedTaxId": "2321-2323-2132"
}
```

<h3 id="add-business-information.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[BusinessInfo](#schemabusinessinfo)|true|none|

> Example responses

> 201 Response

```json
{
  "id": 234,
  "businessName": "Cofe shop LTD",
  "fedTaxId": "2321-2323-2132"
}
```

<h3 id="add-business-information.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|Created|Business information added successfully.|[BusinessInfo](#schemabusinessinfo)|
|400|Bad Request|Unable to add business information.|[Errors](#schemaerrors)|
|404|Not Found|Unable to add business information.
Business infomatin aleready added.|[Errors](#schemaerrors)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKeyAuth
</aside>

<h1 id="api-for-tax-calculator-product-catalog">Product Catalog</h1>

## Return available product catalogs.

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'apikey' => 'API_KEY'
}

result = RestClient.get 'http://localhost:8004/catalogs',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'apikey': 'API_KEY'
}

r = requests.get('http://localhost:8004/catalogs', headers = headers)

print(r.json())

```

`GET /catalogs`

Returns product catalogs for current sale point.
Usually it one.

> Example responses

> 200 Response

```json
{
  "catalogs": [
    {
      "name": "string",
      "merchantId": 0,
      "platformId": 0,
      "id": 0
    }
  ]
}
```

<h3 id="return-available-product-catalogs.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|OK|Returns product catalog.|[ProductCatalogs](#schemaproductcatalogs)|
|404|Not Found|Unable to find product calalog.|[Errors](#schemaerrors)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKeyAuth
</aside>

## Upload and validate product catalog. 
Return a process status.

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'apikey' => 'API_KEY'
}

result = RestClient.post 'http://localhost:8004/catalogs',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'apikey': 'API_KEY'
}

r = requests.post('http://localhost:8004/catalogs', headers = headers)

print(r.json())

```

`POST /catalogs`

Uploads and validtes product catalog. 
Processing product catalog is an asynchronous process.
Endpoint returns a link for checking process status.

> Example responses

> 201 Response

```json
"http://192.168.0.17/api/v1.2/nextPage?size=12"
```

<h3 id="upload-and-validate-product-catalog.-
return-a-process-status.
-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|Created|Returns a link which is used for checking upload 
processing status.|[Link](#schemalink)|
|400|Bad Request|Unable to upload catalog.|[Errors](#schemaerrors)|
|404|Not Found|Catalog has invalid structure.|[Errors](#schemaerrors)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKeyAuth
</aside>

## Return product catalog

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'apikey' => 'API_KEY'
}

result = RestClient.get 'http://localhost:8004/catalogs/{catalogId}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'apikey': 'API_KEY'
}

r = requests.get('http://localhost:8004/catalogs/{catalogId}', headers = headers)

print(r.json())

```

`GET /catalogs/{catalogId}`

Returns product catalog with defined id. 

<h3 id="return-product-catalog-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|catalogId|path|integer|true|Catalog id.|

#### Detailed descriptions

**catalogId**: Catalog id.

> Example responses

> 200 Response

```json
{
  "name": "string",
  "merchantId": 0,
  "platformId": 0,
  "id": 0
}
```

<h3 id="return-product-catalog-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|OK|Return product catalog|[ProductCatalog](#schemaproductcatalog)|
|404|Not Found|Unable to find product catalog.|[Errors](#schemaerrors)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKeyAuth
</aside>

## Remap tax categories.

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'apikey' => 'API_KEY'
}

result = RestClient.post 'http://localhost:8004/catalogs/{catalogId}/map',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'apikey': 'API_KEY'
}

r = requests.post('http://localhost:8004/catalogs/{catalogId}/map', headers = headers)

print(r.json())

```

`POST /catalogs/{catalogId}/map`

Remaps/Maps tax categories for new/updated products only.
Processing product catalog is an asynchronous process.
Endpoint returns a link for checking process status.

<h3 id="remap-tax-categories.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|catalogId|path|string|true|Catalog id.|

#### Detailed descriptions

**catalogId**: Catalog id.

> Example responses

> 201 Response

```json
"http://192.168.0.17/api/v1.2/nextPage?size=12"
```

<h3 id="remap-tax-categories.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|Created|Returns a link which for checking process status.|[Link](#schemalink)|
|404|Not Found|Unable to find catalog.|[Errors](#schemaerrors)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKeyAuth
</aside>

## Get product catalog processing status

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'apikey' => 'API_KEY'
}

result = RestClient.get 'http://localhost:8004/catalogs/{processId}/status',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'apikey': 'API_KEY'
}

r = requests.get('http://localhost:8004/catalogs/{processId}/status', headers = headers)

print(r.json())

```

`GET /catalogs/{processId}/status`

Processing product catalog is an asynchronous process.
The endpoint returns product catalog processing status.

<h3 id="get-product-catalog-processing-status-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|processId|path|integer|true|Process id. |

#### Detailed descriptions

**processId**: Process id. 

> Example responses

> 200 Response

```json
{
  "id": 0,
  "link": "http://192.168.0.17/api/v1.2/nextPage?size=12",
  "status": "processing"
}
```

<h3 id="get-product-catalog-processing-status-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|OK|Returns processing status.|[ProcessingStatus](#schemaprocessingstatus)|
|404|Not Found|Unable to return processing status.
Invalid process identifier.|[Errors](#schemaerrors)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKeyAuth
</aside>

## Accept product catalog categorization.

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'apikey' => 'API_KEY'
}

result = RestClient.post 'http://localhost:8004/catalogs/{catalogId}/accept',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'apikey': 'API_KEY'
}

r = requests.post('http://localhost:8004/catalogs/{catalogId}/accept', headers = headers)

print(r.json())

```

`POST /catalogs/{catalogId}/accept`

Accept product catalog categorization. 

<h3 id="accept-product-catalog-categorization.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|catalogId|path|integer|true|Catalog Id. |

#### Detailed descriptions

**catalogId**: Catalog Id. 

> Example responses

> 404 Response

```json
{
  "errors": [
    {
      "code": 1234,
      "message": "Illegal request parameter",
      "details": [
        "details string1",
        "details string2"
      ]
    }
  ]
}
```

<h3 id="accept-product-catalog-categorization.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|Created|Customer is agree with tax categorization.|None|
|404|Not Found|Invalid identifier, catalog not found
or processing is not finished.|[Errors](#schemaerrors)|

<h3 id="accept-product-catalog-categorization.-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKeyAuth
</aside>

## Download product catalog.

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'apikey' => 'API_KEY'
}

result = RestClient.post 'http://localhost:8004/catalogs/{catalogId}/load',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'apikey': 'API_KEY'
}

r = requests.post('http://localhost:8004/catalogs/{catalogId}/load', headers = headers)

print(r.json())

```

`POST /catalogs/{catalogId}/load`

Allows to download product catalogue for 
new/updated products only.

<h3 id="download-product-catalog.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|catalogId|path|integer|true|Catalog Id.|

#### Detailed descriptions

**catalogId**: Catalog Id.

> Example responses

> 201 Response

```json
{
  "name": "string",
  "merchantId": 0,
  "platformId": 0,
  "id": 0
}
```

<h3 id="download-product-catalog.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|Created|Returns a product catalog.|[ProductCatalog](#schemaproductcatalog)|
|400|Bad Request|Unable to return catalogue.|[Errors](#schemaerrors)|
|404|Not Found|Invalid product catalog identifier.|[Errors](#schemaerrors)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKeyAuth
</aside>

<h1 id="api-for-tax-calculator-product">Product</h1>

## Lookup products from the defined catalog.

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'apikey' => 'API_KEY'
}

result = RestClient.get 'http://localhost:8004/catalogs/{catalogId}/products',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'apikey': 'API_KEY'
}

r = requests.get('http://localhost:8004/catalogs/{catalogId}/products', headers = headers)

print(r.json())

```

`GET /catalogs/{catalogId}/products`

Returns products from the specified catalog. 
Filtering is avilable by
  * product name  
  * product category  
  * product identifier (MasterId/SKU/UPC)
  Product contains tax categories. 
  One of them is sellected. 
  By default, it has max confidence level.
  Other ones are alternative. 

<h3 id="lookup-products-from-the-defined-catalog.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|catalogId|path|integer|true|Catalog id.|
|page|query|integer|false|Page number|
|size|query|integer|false|Record number for single page.|
|name|query|string|false|Filtering by product name. |
|category|query|string|false|Filtering by product category. |
|label|query|string|false|Filtering by label which could be MasterId/SKU/UPC.|
|mappingType|query|string|false|Filtering by product mapping type.|

#### Detailed descriptions

**catalogId**: Catalog id.

**page**: Page number

**size**: Record number for single page.

**name**: Filtering by product name. 

**category**: Filtering by product category. 

**label**: Filtering by label which could be MasterId/SKU/UPC.

**mappingType**: Filtering by product mapping type.

> Example responses

> 201 Response

```json
{
  "pagination": {
    "self": "http://vertex.com/api/v1.2/logs?page=30&size=10",
    "prev": "http://vertex.com/api/v1.2/logs?page=29&size=10",
    "next": "http://vertex.com/api/v1.2/logs?page=31&size=10",
    "first": "http://vertex.com/api/v1.2/logs?page=1&size=10",
    "last": "http://vertex.com/api/v1.2/logs?page=80&size=10"
  },
  "fetchInfo": {
    "totalElements": 5000,
    "size": 10,
    "totslPages": 500,
    "page": 3
  },
  "products": [
    {
      "masterId": "string",
      "name": "string",
      "shortDescription": "string",
      "description": "string",
      "sku": [
        {
          "id": 566,
          "name": "Video Streaming Service",
          "description": "Video streaming service",
          "shortDescription": "Video streaming service",
          "sku": "3423-23423",
          "upc": "2323-234-343",
          "taxCategories": [
            {
              "id": 556,
              "name": "software",
              "confidence": 90,
              "isSelected": "true"
            },
            {
              "id": 557,
              "name": "hardware",
              "confidence": 80,
              "isSelected": "false"
            }
          ]
        }
      ],
      "inActive": true,
      "timestamp": "2019-12-12T13:19:09Z",
      "mappingType": "autoMapped",
      "effectivePeriod": {
        "fromDate": "2019-12-12",
        "toDate": "2019-12-12"
      },
      "taxCategories": [
        {
          "id": 556,
          "name": "sugar contains",
          "confidence": 90,
          "isManually": "true",
          "isSelected": "true"
        }
      ],
      "categories": [
        "Videoserver"
      ],
      "id": 0
    }
  ]
}
```

<h3 id="lookup-products-from-the-defined-catalog.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|Created|Returns collection of the products.|[Products](#schemaproducts)|
|404|Not Found|Product catalog not found.|[Errors](#schemaerrors)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKeyAuth
</aside>

## Add product to the catalog.

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'apikey' => 'API_KEY'
}

result = RestClient.put 'http://localhost:8004/catalogs/{catalogId}/products',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'apikey': 'API_KEY'
}

r = requests.put('http://localhost:8004/catalogs/{catalogId}/products', headers = headers)

print(r.json())

```

`PUT /catalogs/{catalogId}/products`

Adds product to the catalog. 

> Body parameter

```json
{
  "masterId": "string",
  "name": "string",
  "shortDescription": "string",
  "description": "string",
  "sku": [
    {
      "id": 566,
      "name": "Video Streaming Service",
      "description": "Video streaming service",
      "shortDescription": "Video streaming service",
      "sku": "3423-23423",
      "upc": "2323-234-343",
      "taxCategories": [
        {
          "id": 556,
          "name": "software",
          "confidence": 90,
          "isSelected": "true"
        },
        {
          "id": 557,
          "name": "hardware",
          "confidence": 80,
          "isSelected": "false"
        }
      ]
    }
  ],
  "inActive": true,
  "timestamp": "2019-12-12T13:19:09Z",
  "mappingType": "autoMapped",
  "effectivePeriod": {
    "fromDate": "2019-12-12",
    "toDate": "2019-12-12"
  },
  "taxCategories": [
    {
      "id": 556,
      "name": "sugar contains",
      "confidence": 90,
      "isManually": "true",
      "isSelected": "true"
    }
  ],
  "categories": [
    "Videoserver"
  ],
  "id": 0
}
```

<h3 id="add-product-to-the-catalog.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|catalogId|path|integer|true|Catalog Id. |
|body|body|[Product](#schemaproduct)|false|Product definition.|

#### Detailed descriptions

**catalogId**: Catalog Id. 

**body**: Product definition.

> Example responses

> 201 Response

```json
{
  "masterId": "string",
  "name": "string",
  "shortDescription": "string",
  "description": "string",
  "sku": [
    {
      "id": 566,
      "name": "Video Streaming Service",
      "description": "Video streaming service",
      "shortDescription": "Video streaming service",
      "sku": "3423-23423",
      "upc": "2323-234-343",
      "taxCategories": [
        {
          "id": 556,
          "name": "software",
          "confidence": 90,
          "isSelected": "true"
        },
        {
          "id": 557,
          "name": "hardware",
          "confidence": 80,
          "isSelected": "false"
        }
      ]
    }
  ],
  "inActive": true,
  "timestamp": "2019-12-12T13:19:09Z",
  "mappingType": "autoMapped",
  "effectivePeriod": {
    "fromDate": "2019-12-12",
    "toDate": "2019-12-12"
  },
  "taxCategories": [
    {
      "id": 556,
      "name": "sugar contains",
      "confidence": 90,
      "isManually": "true",
      "isSelected": "true"
    }
  ],
  "categories": [
    "Videoserver"
  ],
  "id": 0
}
```

<h3 id="add-product-to-the-catalog.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|Created|Product added successfully.|[Product](#schemaproduct)|
|404|Not Found|Unable to add product to catalog.|[Errors](#schemaerrors)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKeyAuth
</aside>

## Return the product from the catalog.

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'apikey' => 'API_KEY'
}

result = RestClient.get 'http://localhost:8004/products/{productId}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'apikey': 'API_KEY'
}

r = requests.get('http://localhost:8004/products/{productId}', headers = headers)

print(r.json())

```

`GET /products/{productId}`

Returns the productby product id.

<h3 id="return-the-product-from-the-catalog.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|productId|path|integer|true|Product Id. |

#### Detailed descriptions

**productId**: Product Id. 

> Example responses

> 201 Response

```json
{
  "masterId": "string",
  "name": "string",
  "shortDescription": "string",
  "description": "string",
  "sku": [
    {
      "id": 566,
      "name": "Video Streaming Service",
      "description": "Video streaming service",
      "shortDescription": "Video streaming service",
      "sku": "3423-23423",
      "upc": "2323-234-343",
      "taxCategories": [
        {
          "id": 556,
          "name": "software",
          "confidence": 90,
          "isSelected": "true"
        },
        {
          "id": 557,
          "name": "hardware",
          "confidence": 80,
          "isSelected": "false"
        }
      ]
    }
  ],
  "inActive": true,
  "timestamp": "2019-12-12T13:19:09Z",
  "mappingType": "autoMapped",
  "effectivePeriod": {
    "fromDate": "2019-12-12",
    "toDate": "2019-12-12"
  },
  "taxCategories": [
    {
      "id": 556,
      "name": "sugar contains",
      "confidence": 90,
      "isManually": "true",
      "isSelected": "true"
    }
  ],
  "categories": [
    "Videoserver"
  ],
  "id": 0
}
```

<h3 id="return-the-product-from-the-catalog.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|Created|Returns the product|[Product](#schemaproduct)|
|404|Not Found|The product not found.|[Errors](#schemaerrors)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKeyAuth
</aside>

## Update the product.

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'apikey' => 'API_KEY'
}

result = RestClient.patch 'http://localhost:8004/products/{productId}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'apikey': 'API_KEY'
}

r = requests.patch('http://localhost:8004/products/{productId}', headers = headers)

print(r.json())

```

`PATCH /products/{productId}`

Make same changes in the product.

<h3 id="update-the-product.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|productId|path|integer|true|Product id.|

#### Detailed descriptions

**productId**: Product id.

> Example responses

> 204 Response

```json
{
  "masterId": "string",
  "name": "string",
  "shortDescription": "string",
  "description": "string",
  "sku": [
    {
      "id": 566,
      "name": "Video Streaming Service",
      "description": "Video streaming service",
      "shortDescription": "Video streaming service",
      "sku": "3423-23423",
      "upc": "2323-234-343",
      "taxCategories": [
        {
          "id": 556,
          "name": "software",
          "confidence": 90,
          "isSelected": "true"
        },
        {
          "id": 557,
          "name": "hardware",
          "confidence": 80,
          "isSelected": "false"
        }
      ]
    }
  ],
  "inActive": true,
  "timestamp": "2019-12-12T13:19:09Z",
  "mappingType": "autoMapped",
  "effectivePeriod": {
    "fromDate": "2019-12-12",
    "toDate": "2019-12-12"
  },
  "taxCategories": [
    {
      "id": 556,
      "name": "sugar contains",
      "confidence": 90,
      "isManually": "true",
      "isSelected": "true"
    }
  ],
  "categories": [
    "Videoserver"
  ],
  "id": 0
}
```

<h3 id="update-the-product.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|204|No Content|The product updated successfully.|[Product](#schemaproduct)|
|400|Bad Request|Unable to updateproduct.|[Errors](#schemaerrors)|
|404|Not Found|The product not found.|[Errors](#schemaerrors)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKeyAuth
</aside>

<h1 id="api-for-tax-calculator-logging">Logging</h1>

## Return API call logs.

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'apikey' => 'API_KEY'
}

result = RestClient.get 'http://localhost:8004/logs',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'apikey': 'API_KEY'
}

r = requests.get('http://localhost:8004/logs', headers = headers)

print(r.json())

```

`GET /logs`

Returns API call logs for current sale point.

<h3 id="return-api-call-logs.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|page|query|integer|false|Specified page number.|
|size|query|integer|false|Specified number of the logs for single page.|
|fromDate|query|[DateTime](#schemadatetime)|false|Specified period, from date. |
|toDate|query|[DateTime](#schemadatetime)|false|Specified period, to date.|

#### Detailed descriptions

**page**: Specified page number.

**size**: Specified number of the logs for single page.

**fromDate**: Specified period, from date. 

**toDate**: Specified period, to date.

> Example responses

> 200 Response

```json
{
  "logs": [
    {
      "request": {
        "url": "http://vertex.com/api/v1.2/transactions/123?page=1",
        "uri": "api/v1.2/transactions/123",
        "query": "page=1",
        "method": "GET"
      },
      "response": {
        "code": "200",
        "content": "log trace"
      },
      "date": "2019-12-12T13:19:09Z",
      "correlationId": "string"
    }
  ]
}
```

<h3 id="return-api-call-logs.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|OK|Returns logs|[Logs](#schemalogs)|
|404|Not Found|Unable to get logs by defined criterias.|[Errors](#schemaerrors)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKeyAuth
</aside>

<h1 id="api-for-tax-calculator-transaction-journal">Transaction Journal</h1>

## Get transactions.

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'apikey' => 'API_KEY'
}

result = RestClient.get 'http://localhost:8004/transactions',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'apikey': 'API_KEY'
}

r = requests.get('http://localhost:8004/transactions', headers = headers)

print(r.json())

```

`GET /transactions`

Returns transactions for current sale point.
Trnsactions can be selected by specified criteria.

<h3 id="get-transactions.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|page|query|integer|false|Page number.|
|size|query|integer|false|Number of the transactions for single page.|
|states|query|string|false|Specified list of the states with comma delimitter.|
|fromDate|query|[DateTime](#schemadatetime)|false|Specified period, from date.|
|toDate|query|[DateTime](#schemadatetime)|false|Specified period, to date.|

#### Detailed descriptions

**page**: Page number.

**size**: Number of the transactions for single page.

**states**: Specified list of the states with comma delimitter.

**fromDate**: Specified period, from date.

**toDate**: Specified period, to date.

> Example responses

> 200 Response

```json
{
  "pagination": {
    "self": "http://vertex.com/api/v1.2/logs?page=30&size=10",
    "prev": "http://vertex.com/api/v1.2/logs?page=29&size=10",
    "next": "http://vertex.com/api/v1.2/logs?page=31&size=10",
    "first": "http://vertex.com/api/v1.2/logs?page=1&size=10",
    "last": "http://vertex.com/api/v1.2/logs?page=80&size=10"
  },
  "fetchInfo": {
    "totalElements": 5000,
    "size": 10,
    "totslPages": 500,
    "page": 3
  },
  "transactions": [
    {
      "masterId": 0,
      "type": "new",
      "status": "preview",
      "order": {
        "masterId": 0,
        "timestamp": "2019-12-12T13:19:09Z",
        "items": [
          {
            "id": 12,
            "productId": 23,
            "masterId": 643,
            "count": 2,
            "name": "t-short",
            "price": 55.44
          }
        ],
        "total": {
          "total": "string",
          "subTotal": "string",
          "totalTax": "string",
          "taxDetails": [
            {
              "rates": [
                {
                  "id": 54,
                  "description": "VAT",
                  "name": "VAT",
                  "taxLevel": "jurisdiction",
                  "rules": [
                    "s56",
                    "s55"
                  ],
                  "percentage": 7
                }
              ],
              "amount": "string"
            }
          ]
        },
        "id": 0
      },
      "id": 0
    }
  ]
}
```

<h3 id="get-transactions.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|OK|Returns transactions|[Transactions](#schematransactions)|
|404|Not Found|Unable to get transactions with defined criterias.|[Errors](#schemaerrors)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKeyAuth
</aside>

## Get Transaction Summary.

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'apikey' => 'API_KEY'
}

result = RestClient.get 'http://localhost:8004/transactions/summary',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'apikey': 'API_KEY'
}

r = requests.get('http://localhost:8004/transactions/summary', headers = headers)

print(r.json())

```

`GET /transactions/summary`

Returns summary for transactions for current 
sale point which are selected by defined criterias.

<h3 id="get-transaction-summary.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|states|query|string|false|List of the states. |
|fromDate|query|[DateTime](#schemadatetime)|false|Specified period of time. From date.|
|toDate|query|[DateTime](#schemadatetime)|false|Specified period of time. To date.|

#### Detailed descriptions

**states**: List of the states. 
Comma is used as a delimiter.

**fromDate**: Specified period of time. From date.

**toDate**: Specified period of time. To date.

> Example responses

> 200 Response

```json
{
  "countTrans": 343,
  "totalSales": 6565.9,
  "totalTax": 34.3
}
```

<h3 id="get-transaction-summary.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|OK|Returns transaction summary|[TransactionSummary](#schematransactionsummary)|
|404|Not Found|Unable to get transaction summary.|[Errors](#schemaerrors)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKeyAuth
</aside>

## Download journal in CVS.

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'apikey' => 'API_KEY'
}

result = RestClient.get 'http://localhost:8004/transactions/cvs',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'apikey': 'API_KEY'
}

r = requests.get('http://localhost:8004/transactions/cvs', headers = headers)

print(r.json())

```

`GET /transactions/cvs`

This endpoint is used by customers if they want to download transaction journal in CVS format.

<h3 id="download-journal-in-cvs.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|states|query|string|false|List of the states with comma delimiter.|
|fromDate|query|[DateTime](#schemadatetime)|false|Specified period of time. From date.|
|toDate|query|[DateTime](#schemadatetime)|false|Specified period of time. To date.|

#### Detailed descriptions

**states**: List of the states with comma delimiter.

**fromDate**: Specified period of time. From date.

**toDate**: Specified period of time. To date.

> Example responses

> 404 Response

```json
{
  "errors": [
    {
      "code": 1234,
      "message": "Illegal request parameter",
      "details": [
        "details string1",
        "details string2"
      ]
    }
  ]
}
```

<h3 id="download-journal-in-cvs.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|OK|Returns journal in CVS format.|None|
|404|Not Found|Unable to create transaction journal.|[Errors](#schemaerrors)|

<h3 id="download-journal-in-cvs.-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKeyAuth
</aside>

<h1 id="api-for-tax-calculator-transaction-management">Transaction Management</h1>

## Consume transaction.

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'apikey' => 'API_KEY'
}

result = RestClient.post 'http://localhost:8004/transactions',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'apikey': 'API_KEY'
}

r = requests.post('http://localhost:8004/transactions', headers = headers)

print(r.json())

```

`POST /transactions`

Consume merchant transaction. 
If transaction is sale and compeleted it would 
be registered in the tax journal. 
Returns transaction with total.
Total includes collection taxes.

> Body parameter

```json
{
  "masterId": 0,
  "type": "new",
  "status": "preview",
  "order": {
    "masterId": 0,
    "timestamp": "2019-12-12T13:19:09Z",
    "items": [
      {
        "id": 12,
        "productId": 23,
        "masterId": 643,
        "count": 2,
        "name": "t-short",
        "price": 55.44
      }
    ],
    "total": {
      "total": "string",
      "subTotal": "string",
      "totalTax": "string",
      "taxDetails": [
        {
          "rates": [
            {
              "id": 54,
              "description": "VAT",
              "name": "VAT",
              "taxLevel": "jurisdiction",
              "rules": [
                "s56",
                "s55"
              ],
              "percentage": 7
            }
          ],
          "amount": "string"
        }
      ]
    },
    "id": 0
  },
  "id": 0
}
```

<h3 id="consume-transaction.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[Transaction](#schematransaction)|true|none|

> Example responses

> 201 Response

```json
{
  "masterId": 0,
  "type": "new",
  "status": "preview",
  "order": {
    "masterId": 0,
    "timestamp": "2019-12-12T13:19:09Z",
    "items": [
      {
        "id": 12,
        "productId": 23,
        "masterId": 643,
        "count": 2,
        "name": "t-short",
        "price": 55.44
      }
    ],
    "total": {
      "total": "string",
      "subTotal": "string",
      "totalTax": "string",
      "taxDetails": [
        {
          "rates": [
            {
              "id": 54,
              "description": "VAT",
              "name": "VAT",
              "taxLevel": "jurisdiction",
              "rules": [
                "s56",
                "s55"
              ],
              "percentage": 7
            }
          ],
          "amount": "string"
        }
      ]
    },
    "id": 0
  },
  "id": 0
}
```

<h3 id="consume-transaction.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|Created|Returns transaction with total.|[Transaction](#schematransaction)|
|400|Bad Request|Unable to add transaction.|[Errors](#schemaerrors)|
|409|Conflict|Unable to add transaction.
Transactions already registered.|[Errors](#schemaerrors)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKeyAuth
</aside>

## Get transaction.

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'apikey' => 'API_KEY'
}

result = RestClient.get 'http://localhost:8004/transactions/{transactionId}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'apikey': 'API_KEY'
}

r = requests.get('http://localhost:8004/transactions/{transactionId}', headers = headers)

print(r.json())

```

`GET /transactions/{transactionId}`

Get transaction from the tax journal.

<h3 id="get-transaction.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|transactionId|path|string|true|Transaction id.|

#### Detailed descriptions

**transactionId**: Transaction id.

> Example responses

> 200 Response

```json
{
  "masterId": 0,
  "type": "new",
  "status": "preview",
  "order": {
    "masterId": 0,
    "timestamp": "2019-12-12T13:19:09Z",
    "items": [
      {
        "id": 12,
        "productId": 23,
        "masterId": 643,
        "count": 2,
        "name": "t-short",
        "price": 55.44
      }
    ],
    "total": {
      "total": "string",
      "subTotal": "string",
      "totalTax": "string",
      "taxDetails": [
        {
          "rates": [
            {
              "id": 54,
              "description": "VAT",
              "name": "VAT",
              "taxLevel": "jurisdiction",
              "rules": [
                "s56",
                "s55"
              ],
              "percentage": 7
            }
          ],
          "amount": "string"
        }
      ]
    },
    "id": 0
  },
  "id": 0
}
```

<h3 id="get-transaction.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|OK|Returns a transaction.|[Transaction](#schematransaction)|
|404|Not Found|Transaction with specified id not found.|[Errors](#schemaerrors)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKeyAuth
</aside>

## Delete transaction.

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'apikey' => 'API_KEY'
}

result = RestClient.delete 'http://localhost:8004/transactions/{transactionId}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'apikey': 'API_KEY'
}

r = requests.delete('http://localhost:8004/transactions/{transactionId}', headers = headers)

print(r.json())

```

`DELETE /transactions/{transactionId}`

Delete transaction with specified id from
the tax journal.
Soft delete.

<h3 id="delete-transaction.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|transactionId|path|string|true|Transaction id.|

#### Detailed descriptions

**transactionId**: Transaction id.

> Example responses

> 200 Response

```json
{
  "masterId": 0,
  "type": "new",
  "status": "preview",
  "order": {
    "masterId": 0,
    "timestamp": "2019-12-12T13:19:09Z",
    "items": [
      {
        "id": 12,
        "productId": 23,
        "masterId": 643,
        "count": 2,
        "name": "t-short",
        "price": 55.44
      }
    ],
    "total": {
      "total": "string",
      "subTotal": "string",
      "totalTax": "string",
      "taxDetails": [
        {
          "rates": [
            {
              "id": 54,
              "description": "VAT",
              "name": "VAT",
              "taxLevel": "jurisdiction",
              "rules": [
                "s56",
                "s55"
              ],
              "percentage": 7
            }
          ],
          "amount": "string"
        }
      ]
    },
    "id": 0
  },
  "id": 0
}
```

<h3 id="delete-transaction.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|OK|Transaction deleted successfully.|[Transaction](#schematransaction)|
|404|Not Found|Unable to delete transaction.
Transaction with specified id not found.|[Errors](#schemaerrors)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKeyAuth
</aside>

## Update specified transaction.

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'apikey' => 'API_KEY'
}

result = RestClient.patch 'http://localhost:8004/transactions/{transactionId}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'apikey': 'API_KEY'
}

r = requests.patch('http://localhost:8004/transactions/{transactionId}', headers = headers)

print(r.json())

```

`PATCH /transactions/{transactionId}`

Update specified transaction.
Safe operation. 

> Body parameter

```json
{
  "masterId": 0,
  "type": "new",
  "status": "preview",
  "order": {
    "masterId": 0,
    "timestamp": "2019-12-12T13:19:09Z",
    "items": [
      {
        "id": 12,
        "productId": 23,
        "masterId": 643,
        "count": 2,
        "name": "t-short",
        "price": 55.44
      }
    ],
    "total": {
      "total": "string",
      "subTotal": "string",
      "totalTax": "string",
      "taxDetails": [
        {
          "rates": [
            {
              "id": 54,
              "description": "VAT",
              "name": "VAT",
              "taxLevel": "jurisdiction",
              "rules": [
                "s56",
                "s55"
              ],
              "percentage": 7
            }
          ],
          "amount": "string"
        }
      ]
    },
    "id": 0
  },
  "id": 0
}
```

<h3 id="update-specified-transaction.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|transactionId|path|string|true|Specified transaction id.|
|body|body|[Transaction](#schematransaction)|true|none|

#### Detailed descriptions

**transactionId**: Specified transaction id.

> Example responses

> 204 Response

```json
{
  "masterId": 0,
  "type": "new",
  "status": "preview",
  "order": {
    "masterId": 0,
    "timestamp": "2019-12-12T13:19:09Z",
    "items": [
      {
        "id": 12,
        "productId": 23,
        "masterId": 643,
        "count": 2,
        "name": "t-short",
        "price": 55.44
      }
    ],
    "total": {
      "total": "string",
      "subTotal": "string",
      "totalTax": "string",
      "taxDetails": [
        {
          "rates": [
            {
              "id": 54,
              "description": "VAT",
              "name": "VAT",
              "taxLevel": "jurisdiction",
              "rules": [
                "s56",
                "s55"
              ],
              "percentage": 7
            }
          ],
          "amount": "string"
        }
      ]
    },
    "id": 0
  },
  "id": 0
}
```

<h3 id="update-specified-transaction.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|204|No Content|Transaction updated successfully.|[Transaction](#schematransaction)|
|404|Not Found|Unable to update transaction. 
Transaction with specified id not found.|[Errors](#schemaerrors)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKeyAuth
</aside>

# Schemas

<h2 id="tocS_Link">Link</h2>
<!-- backwards compatibility -->
<a id="schemalink"></a>
<a id="schema_Link"></a>
<a id="tocSlink"></a>
<a id="tocslink"></a>

```json
"http://192.168.0.17/api/v1.2/nextPage?size=12"

```

Link

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|href|string|false|none|none|

<h2 id="tocS_Pagination">Pagination</h2>
<!-- backwards compatibility -->
<a id="schemapagination"></a>
<a id="schema_Pagination"></a>
<a id="tocSpagination"></a>
<a id="tocspagination"></a>

```json
{
  "self": "http://vertex.com/api/v1.2/logs?page=30&size=10",
  "prev": "http://vertex.com/api/v1.2/logs?page=29&size=10",
  "next": "http://vertex.com/api/v1.2/logs?page=31&size=10",
  "first": "http://vertex.com/api/v1.2/logs?page=1&size=10",
  "last": "http://vertex.com/api/v1.2/logs?page=80&size=10"
}

```

Pagination

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|self|[Link](#schemalink)|false|none|Absolute URI. <br>Used for implementing UI on hypermedia way.|
|prev|[Link](#schemalink)|false|none|Absolute URI. <br>Used for implementing UI on hypermedia way.|
|next|[Link](#schemalink)|false|none|Absolute URI. <br>Used for implementing UI on hypermedia way.|
|first|[Link](#schemalink)|false|none|Absolute URI. <br>Used for implementing UI on hypermedia way.|
|last|[Link](#schemalink)|false|none|Absolute URI. <br>Used for implementing UI on hypermedia way.|

<h2 id="tocS_FetchInfo">FetchInfo</h2>
<!-- backwards compatibility -->
<a id="schemafetchinfo"></a>
<a id="schema_FetchInfo"></a>
<a id="tocSfetchinfo"></a>
<a id="tocsfetchinfo"></a>

```json
{
  "totalElements": 5000,
  "size": 10,
  "totslPages": 500,
  "page": 3
}

```

Fetch info

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|size|integer|false|none|Chunk size.|
|totalElelments|integer|false|none|Total elements count.|
|totalPages|integer|false|none|Total page count.|
|page|integer|false|none|Current page.|

<h2 id="tocS_Entity">Entity</h2>
<!-- backwards compatibility -->
<a id="schemaentity"></a>
<a id="schema_Entity"></a>
<a id="tocSentity"></a>
<a id="tocsentity"></a>

```json
{
  "id": 0
}

```

Entity

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|integer|false|none|Entity identifier.|

<h2 id="tocS_Error">Error</h2>
<!-- backwards compatibility -->
<a id="schemaerror"></a>
<a id="schema_Error"></a>
<a id="tocSerror"></a>
<a id="tocserror"></a>

```json
{
  "code": 1234,
  "message": "Illegal request parameter",
  "details": [
    "details string1",
    "details string2"
  ]
}

```

Error

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|code|integer|false|none|Error code|
|message|string|false|none|Error message|
|details|[string]|false|none|none|

<h2 id="tocS_Errors">Errors</h2>
<!-- backwards compatibility -->
<a id="schemaerrors"></a>
<a id="schema_Errors"></a>
<a id="tocSerrors"></a>
<a id="tocserrors"></a>

```json
{
  "errors": [
    {
      "code": 1234,
      "message": "Illegal request parameter",
      "details": [
        "details string1",
        "details string2"
      ]
    }
  ]
}

```

Errors

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|errors|[[Error](#schemaerror)]|false|none|[Error message<br>]|

<h2 id="tocS_Amount">Amount</h2>
<!-- backwards compatibility -->
<a id="schemaamount"></a>
<a id="schema_Amount"></a>
<a id="tocSamount"></a>
<a id="tocsamount"></a>

```json
"string"

```

Amount

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|Amount|string|false|none|Amont in format is [ISO 20022]. <br>The decimal separator is a dot. NNNN.NN|

<h2 id="tocS_Date">Date</h2>
<!-- backwards compatibility -->
<a id="schemadate"></a>
<a id="schema_Date"></a>
<a id="tocSdate"></a>
<a id="tocsdate"></a>

```json
"2019-12-12"

```

Date

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|Date|string(date)|false|none|Date in format [ISO-8601], YYYY-MM-DD|

<h2 id="tocS_DateTime">DateTime</h2>
<!-- backwards compatibility -->
<a id="schemadatetime"></a>
<a id="schema_DateTime"></a>
<a id="tocSdatetime"></a>
<a id="tocsdatetime"></a>

```json
"2019-12-12T13:19:09Z"

```

Date-time

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|Date-time|string(date-time)|false|none|Date-time in format [ISO-8601], YYYY-MM-DDThh:mm:ssTZD|

<h2 id="tocS_Email">Email</h2>
<!-- backwards compatibility -->
<a id="schemaemail"></a>
<a id="schema_Email"></a>
<a id="tocSemail"></a>
<a id="tocsemail"></a>

```json
"string"

```

Email address

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|Email address|string|false|none|none|

<h2 id="tocS_Phone">Phone</h2>
<!-- backwards compatibility -->
<a id="schemaphone"></a>
<a id="schema_Phone"></a>
<a id="tocSphone"></a>
<a id="tocsphone"></a>

```json
"string"

```

Phone number

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|Phone number|string|false|none|none|

<h2 id="tocS_Period">Period</h2>
<!-- backwards compatibility -->
<a id="schemaperiod"></a>
<a id="schema_Period"></a>
<a id="tocSperiod"></a>
<a id="tocsperiod"></a>

```json
{
  "fromDate": "2019-12-12",
  "toDate": "2019-12-12"
}

```

Period

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|fromDate|[Date](#schemadate)|true|none|Date in format [ISO-8601], YYYY-MM-DD|
|toDate|[Date](#schemadate)|true|none|Date in format [ISO-8601], YYYY-MM-DD|

<h2 id="tocS_ProcessingStatus">ProcessingStatus</h2>
<!-- backwards compatibility -->
<a id="schemaprocessingstatus"></a>
<a id="schema_ProcessingStatus"></a>
<a id="tocSprocessingstatus"></a>
<a id="tocsprocessingstatus"></a>

```json
{
  "id": 0,
  "link": "http://192.168.0.17/api/v1.2/nextPage?size=12",
  "status": "processing"
}

```

Processing status

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|integer|false|none|Identifier|
|link|[Link](#schemalink)|false|none|Absolute URI. <br>Used for implementing UI on hypermedia way.|
|status|string|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|status|processing|
|status|error|
|status|done|

<h2 id="tocS_Message">Message</h2>
<!-- backwards compatibility -->
<a id="schemamessage"></a>
<a id="schema_Message"></a>
<a id="tocSmessage"></a>
<a id="tocsmessage"></a>

```json
{
  "email": "user@vertex.com",
  "subject": "Account confirmation",
  "parameters": [
    {
      "name": "name",
      "value": "value"
    }
  ]
}

```

Email message

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|email|string|true|none|User email address.|
|subject|string|true|none|Message subject.|
|parameters|[[Parameter](#schemaparameter)]|false|none|[Definition of the notification parameter. <br>Notification service uses parameters to fulfil <br>defined template by values.<br>]|

<h2 id="tocS_Template">Template</h2>
<!-- backwards compatibility -->
<a id="schematemplate"></a>
<a id="schema_Template"></a>
<a id="tocStemplate"></a>
<a id="tocstemplate"></a>

```json
{
  "id": 624,
  "name": "email",
  "body": " Dear {name}, Your account is activated."
}

```

Template

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|Template|[Entity](#schemaentity)|false|none|Definition of the notification template.|
|name|string|false|none|Unique template name.|
|body|string|false|none|Template body which should be HTML with data fileds placeholders.|

<h2 id="tocS_Templates">Templates</h2>
<!-- backwards compatibility -->
<a id="schematemplates"></a>
<a id="schema_Templates"></a>
<a id="tocStemplates"></a>
<a id="tocstemplates"></a>

```json
{
  "templates": [
    {
      "id": 624,
      "name": "email",
      "body": " Dear {name}, Your account is activated."
    }
  ]
}

```

Template collection

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|templates|[[Template](#schematemplate)]|false|none|[Definition of the notification template.<br>]|

<h2 id="tocS_Parameter">Parameter</h2>
<!-- backwards compatibility -->
<a id="schemaparameter"></a>
<a id="schema_Parameter"></a>
<a id="tocSparameter"></a>
<a id="tocsparameter"></a>

```json
{
  "name": "string",
  "value": "string"
}

```

Notification Parameter

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|name|string|false|none|Parameter name.|
|value|string|false|none|Parameter value.|

<h2 id="tocS_LocationType">LocationType</h2>
<!-- backwards compatibility -->
<a id="schemalocationtype"></a>
<a id="schema_LocationType"></a>
<a id="tocSlocationtype"></a>
<a id="tocslocationtype"></a>

```json
"administrative"

```

Location Type

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|Location Type|string|false|none|An enumeration that represents available Location Types.<br>| value          | description                              |<br>|----------------|------------------------------------------|<br>| administrative | It means store regisgtration place       |<br>| phisical       | Store phosical prenets                   ||

#### Enumerated Values

|Property|Value|
|---|---|
|Location Type|administrative|
|Location Type|phisical|

<h2 id="tocS_Location">Location</h2>
<!-- backwards compatibility -->
<a id="schemalocation"></a>
<a id="schema_Location"></a>
<a id="tocSlocation"></a>
<a id="tocslocation"></a>

```json
{
  "id": 653,
  "type": "administrative",
  "city": "KNG OF PRUSSA",
  "state": "PA",
  "zip": "19406",
  "zipExt": "1101",
  "addressLine1": "875 MANCILL MILL RD"
}

```

Location

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|Location|[Entity](#schemaentity)|false|none|none|
|type|[LocationType](#schemalocationtype)|true|none|An enumeration that represents available Location Types.<br>| value          | description                              |<br>|----------------|------------------------------------------|<br>| administrative | It means store regisgtration place       |<br>| phisical       | Store phosical prenets                   ||
|city|string|true|none|none|
|state|[State](#schemastate)|true|none|State in format [ISO 3166-2]|
|zip|string|true|none|none|
|zipExt|string|false|none|none|
|addressLine1|string|false|none|none|
|addressLine2|string|false|none|none|

<h2 id="tocS_Locations">Locations</h2>
<!-- backwards compatibility -->
<a id="schemalocations"></a>
<a id="schema_Locations"></a>
<a id="tocSlocations"></a>
<a id="tocslocations"></a>

```json
{
  "locations": [
    {
      "id": 653,
      "type": "administrative",
      "city": "KNG OF PRUSSA",
      "state": "PA",
      "zip": "19406",
      "zipExt": "1101",
      "addressLine1": "875 MANCILL MILL RD"
    }
  ]
}

```

Location collection

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|locations|[[Location](#schemalocation)]|false|none|none|

<h2 id="tocS_Contact">Contact</h2>
<!-- backwards compatibility -->
<a id="schemacontact"></a>
<a id="schema_Contact"></a>
<a id="tocScontact"></a>
<a id="tocscontact"></a>

```json
{
  "id": 464,
  "title": "Mr",
  "name": "Oleksiy",
  "lastName": "Luchkovskiy"
}

```

Contact person

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|Contact person|[Entity](#schemaentity)|false|none|none|
|title|string|true|none|Contact title.|
|name|string|true|none|Contact name.|
|lastName|string|true|none|Contact last name.|

<h2 id="tocS_ContactInfo">ContactInfo</h2>
<!-- backwards compatibility -->
<a id="schemacontactinfo"></a>
<a id="schema_ContactInfo"></a>
<a id="tocScontactinfo"></a>
<a id="tocscontactinfo"></a>

```json
{
  "location": {
    "id": 653,
    "type": "administrative",
    "city": "KNG OF PRUSSA",
    "state": "PA",
    "zip": "19406",
    "zipExt": "1101",
    "addressLine1": "875 MANCILL MILL RD"
  },
  "emails": [
    "string"
  ],
  "phones": [
    "string"
  ],
  "id": 464,
  "title": "Mr",
  "name": "Oleksiy",
  "lastName": "Luchkovskiy"
}

```

Contact information

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|Contact information|[Contact](#schemacontact)|false|none|none|
|location|[Location](#schemalocation)|false|none|none|
|emails|[[Email](#schemaemail)]|false|none|none|
|phones|[[Phone](#schemaphone)]|false|none|none|

<h2 id="tocS_State">State</h2>
<!-- backwards compatibility -->
<a id="schemastate"></a>
<a id="schema_State"></a>
<a id="tocSstate"></a>
<a id="tocsstate"></a>

```json
"string"

```

State

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|State|string|false|none|State in format [ISO 3166-2]|

<h2 id="tocS_Account">Account</h2>
<!-- backwards compatibility -->
<a id="schemaaccount"></a>
<a id="schema_Account"></a>
<a id="tocSaccount"></a>
<a id="tocsaccount"></a>

```json
{
  "id": 656,
  "name": "Cofe shop",
  "email": "shop@vertex.com",
  "password": "password"
}

```

Account

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|Account|[Entity](#schemaentity)|false|none|none|
|name|string|false|none|Account name.|
|email|[Email](#schemaemail)|true|none|none|
|password|string(password)|true|none|Account password.|

<h2 id="tocS_AccountInfo">AccountInfo</h2>
<!-- backwards compatibility -->
<a id="schemaaccountinfo"></a>
<a id="schema_AccountInfo"></a>
<a id="tocSaccountinfo"></a>
<a id="tocsaccountinfo"></a>

```json
{
  "account": {
    "id": 656,
    "name": "Cofe shop",
    "email": "shop@vertex.com",
    "password": "password"
  },
  "businessInfo": {
    "id": 234,
    "businessName": "Cofe shop LTD",
    "fedTaxId": "2321-2323-2132"
  },
  "locations": {
    "locations": [
      {
        "id": 653,
        "type": "administrative",
        "city": "KNG OF PRUSSA",
        "state": "PA",
        "zip": "19406",
        "zipExt": "1101",
        "addressLine1": "875 MANCILL MILL RD"
      }
    ]
  }
}

```

Account Info

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|account|[Account](#schemaaccount)|false|none|none|
|businessInfo|[BusinessInfo](#schemabusinessinfo)|false|none|Account business information. <br>This information includes business name and tax identifier.|
|locations|[Locations](#schemalocations)|false|none|none|

<h2 id="tocS_TokenType">TokenType</h2>
<!-- backwards compatibility -->
<a id="schematokentype"></a>
<a id="schema_TokenType"></a>
<a id="tocStokentype"></a>
<a id="tocstokentype"></a>

```json
{
  "type": "public"
}

```

Token Type

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|type|string|true|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|type|public|
|type|private|

<h2 id="tocS_Token">Token</h2>
<!-- backwards compatibility -->
<a id="schematoken"></a>
<a id="schema_Token"></a>
<a id="tocStoken"></a>
<a id="tocstoken"></a>

```json
{
  "type": "sandbox",
  "token": "1324325543234324",
  "created": "2019-08-23T12:23:56TZ2"
}

```

Token

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|type|[TokenType](#schematokentype)|true|none|An enumeration that represents available Token Types.<br>| value    | description                                    |<br>|----------|------------------------------------------------|<br>| public   | This token gives acces to the sandbox          |<br>| private  | This token gives acces to the production env   ||
|token|string|true|none|API Authentication token.|
|created|[DateTime](#schemadatetime)|true|none|Date-time in format [ISO-8601], YYYY-MM-DDThh:mm:ssTZD|

<h2 id="tocS_Tokens">Tokens</h2>
<!-- backwards compatibility -->
<a id="schematokens"></a>
<a id="schema_Tokens"></a>
<a id="tocStokens"></a>
<a id="tocstokens"></a>

```json
{
  "pagination": {
    "self": "http://vertex.com/api/v1.2/logs?page=30&size=10",
    "prev": "http://vertex.com/api/v1.2/logs?page=29&size=10",
    "next": "http://vertex.com/api/v1.2/logs?page=31&size=10",
    "first": "http://vertex.com/api/v1.2/logs?page=1&size=10",
    "last": "http://vertex.com/api/v1.2/logs?page=80&size=10"
  },
  "fetchInfo": {
    "totalElements": 5000,
    "size": 10,
    "totslPages": 500,
    "page": 3
  },
  "tokens": [
    {
      "type": "sandbox",
      "token": "1324325543234324",
      "created": "2019-08-23T12:23:56TZ2"
    }
  ]
}

```

Token collection

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|pagination|[Pagination](#schemapagination)|false|none|Hypermedia approach for pagination, contains links<br>for current, previous and next pages.|
|fetchInfo|[FetchInfo](#schemafetchinfo)|false|none|Data fetch info.<br>Used for implementing data pagination.|
|tokens|[[Token](#schematoken)]|false|none|none|

<h2 id="tocS_BusinessInfo">BusinessInfo</h2>
<!-- backwards compatibility -->
<a id="schemabusinessinfo"></a>
<a id="schema_BusinessInfo"></a>
<a id="tocSbusinessinfo"></a>
<a id="tocsbusinessinfo"></a>

```json
{
  "id": 234,
  "businessName": "Cofe shop LTD",
  "fedTaxId": "2321-2323-2132"
}

```

Business information

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|Business information|[Entity](#schemaentity)|false|none|Account business information. <br>This information includes business name and tax identifier.|
|businessName|string|true|none|Business name.|
|fedTaxId|string|true|none|Federal tax identifier.|

<h2 id="tocS_TaxCategory">TaxCategory</h2>
<!-- backwards compatibility -->
<a id="schemataxcategory"></a>
<a id="schema_TaxCategory"></a>
<a id="tocStaxcategory"></a>
<a id="tocstaxcategory"></a>

```json
{
  "id": 556,
  "name": "sugar contains",
  "confidence": 90,
  "isManually": "true",
  "isSelected": "true"
}

```

Tax Category

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|Tax Category|[Entity](#schemaentity)|false|none|none|
|name|string|false|none|Tax category name.|
|confidence|integer|false|none|Prediction categorization confidence.|
|isManualy|boolean|false|none|Flag indicates that the tax category is defined manually.|
|isSelected|boolean|false|none|Flag indicates that the tax category is selected.|

<h2 id="tocS_TaxCategories">TaxCategories</h2>
<!-- backwards compatibility -->
<a id="schemataxcategories"></a>
<a id="schema_TaxCategories"></a>
<a id="tocStaxcategories"></a>
<a id="tocstaxcategories"></a>

```json
[
  {
    "id": 556,
    "name": "sugar contains",
    "confidence": 90,
    "isManually": "true",
    "isSelected": "true"
  }
]

```

Tax Category collection

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|Tax Category collection|[[TaxCategory](#schemataxcategory)]|false|none|none|

<h2 id="tocS_ProductCatalog">ProductCatalog</h2>
<!-- backwards compatibility -->
<a id="schemaproductcatalog"></a>
<a id="schema_ProductCatalog"></a>
<a id="tocSproductcatalog"></a>
<a id="tocsproductcatalog"></a>

```json
{
  "name": "string",
  "merchantId": 0,
  "platformId": 0,
  "id": 0
}

```

Product Catalog

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|Product Catalog|[Entity](#schemaentity)|false|none|none|
|name|string|false|none|Product name.|
|merchantId|integer|false|none|Sale point/merchnt identifier.|
|platformId|integer|false|none|Platform identifier.|

<h2 id="tocS_ProductCatalogs">ProductCatalogs</h2>
<!-- backwards compatibility -->
<a id="schemaproductcatalogs"></a>
<a id="schema_ProductCatalogs"></a>
<a id="tocSproductcatalogs"></a>
<a id="tocsproductcatalogs"></a>

```json
{
  "catalogs": [
    {
      "name": "string",
      "merchantId": 0,
      "platformId": 0,
      "id": 0
    }
  ]
}

```

Product Catalog сollection

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|catalogs|[[ProductCatalog](#schemaproductcatalog)]|false|none|none|

<h2 id="tocS_Category">Category</h2>
<!-- backwards compatibility -->
<a id="schemacategory"></a>
<a id="schema_Category"></a>
<a id="tocScategory"></a>
<a id="tocscategory"></a>

```json
"Videoserver"

```

Product Catalog category

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|Product Catalog category|string|false|none|none|

<h2 id="tocS_Categories">Categories</h2>
<!-- backwards compatibility -->
<a id="schemacategories"></a>
<a id="schema_Categories"></a>
<a id="tocScategories"></a>
<a id="tocscategories"></a>

```json
[
  "Videoserver"
]

```

Catalog Category collection

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|Catalog Category collection|[[Category](#schemacategory)]|false|none|none|

<h2 id="tocS_MappingType">MappingType</h2>
<!-- backwards compatibility -->
<a id="schemamappingtype"></a>
<a id="schema_MappingType"></a>
<a id="tocSmappingtype"></a>
<a id="tocsmappingtype"></a>

```json
"autoMapped"

```

Product Mapping Type

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|Product Mapping Type|string|false|none|An enumeration that represents Product Mapping Types<br>| value      | description                                    |<br>|------------|------------------------------------------------|<br>| autoMapped | For this product mapping has been done by ML   |<br>| new        | This product has been added                    |<br>| udated     | This product has been updated/changed          |<br>| remapped   | This product categoy has been remapped         ||

#### Enumerated Values

|Property|Value|
|---|---|
|Product Mapping Type|autoMapped|
|Product Mapping Type|new|
|Product Mapping Type|udated|
|Product Mapping Type|remapped|

<h2 id="tocS_Product">Product</h2>
<!-- backwards compatibility -->
<a id="schemaproduct"></a>
<a id="schema_Product"></a>
<a id="tocSproduct"></a>
<a id="tocsproduct"></a>

```json
{
  "masterId": "string",
  "name": "string",
  "shortDescription": "string",
  "description": "string",
  "sku": [
    {
      "id": 566,
      "name": "Video Streaming Service",
      "description": "Video streaming service",
      "shortDescription": "Video streaming service",
      "sku": "3423-23423",
      "upc": "2323-234-343",
      "taxCategories": [
        {
          "id": 556,
          "name": "software",
          "confidence": 90,
          "isSelected": "true"
        },
        {
          "id": 557,
          "name": "hardware",
          "confidence": 80,
          "isSelected": "false"
        }
      ]
    }
  ],
  "inActive": true,
  "timestamp": "2019-12-12T13:19:09Z",
  "mappingType": "autoMapped",
  "effectivePeriod": {
    "fromDate": "2019-12-12",
    "toDate": "2019-12-12"
  },
  "taxCategories": [
    {
      "id": 556,
      "name": "sugar contains",
      "confidence": 90,
      "isManually": "true",
      "isSelected": "true"
    }
  ],
  "categories": [
    "Videoserver"
  ],
  "id": 0
}

```

Product

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|Product|[Entity](#schemaentity)|false|none|none|
|masterId|string|false|none|Product master id.<br>Product identifier in exernal system.|
|name|string|true|none|Product name.|
|shortDescription|string|false|none|Short product description.|
|description|string|false|none|Product description.|
|sku|[[StockUnit](#schemastockunit)]|false|none|none|
|inActive|boolean|false|none|The flag indicates that the product<br>is available now.|
|timestamp|[DateTime](#schemadatetime)|false|none|Date-time in format [ISO-8601], YYYY-MM-DDThh:mm:ssTZD|
|mappingType|[MappingType](#schemamappingtype)|false|none|An enumeration that represents Product Mapping Types<br>| value      | description                                    |<br>|------------|------------------------------------------------|<br>| autoMapped | For this product mapping has been done by ML   |<br>| new        | This product has been added                    |<br>| udated     | This product has been updated/changed          |<br>| remapped   | This product categoy has been remapped         ||
|effectivePeriod|[Period](#schemaperiod)|false|none|none|
|taxCategories|[TaxCategories](#schemataxcategories)|false|none|none|
|categories|[Categories](#schemacategories)|false|none|none|

<h2 id="tocS_StockUnit">StockUnit</h2>
<!-- backwards compatibility -->
<a id="schemastockunit"></a>
<a id="schema_StockUnit"></a>
<a id="tocSstockunit"></a>
<a id="tocsstockunit"></a>

```json
{
  "id": 566,
  "name": "Video Streaming Service",
  "description": "Video streaming service",
  "shortDescription": "Video streaming service",
  "sku": "3423-23423",
  "upc": "2323-234-343",
  "taxCategories": [
    {
      "id": 556,
      "name": "software",
      "confidence": 90,
      "isSelected": "true"
    },
    {
      "id": 557,
      "name": "hardware",
      "confidence": 80,
      "isSelected": "false"
    }
  ]
}

```

Stock Keeping Unit

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|Stock Keeping Unit|[Entity](#schemaentity)|false|none|none|
|sku|string|false|none|Stock Keeping Unit.|
|name|string|false|none|Name.|
|shortDescription|string|false|none|Short description.|
|description|string|false|none|Description.|
|upc|string|false|none|UPC code.|
|taxCategories|[TaxCategories](#schemataxcategories)|false|none|none|

<h2 id="tocS_Products">Products</h2>
<!-- backwards compatibility -->
<a id="schemaproducts"></a>
<a id="schema_Products"></a>
<a id="tocSproducts"></a>
<a id="tocsproducts"></a>

```json
{
  "pagination": {
    "self": "http://vertex.com/api/v1.2/logs?page=30&size=10",
    "prev": "http://vertex.com/api/v1.2/logs?page=29&size=10",
    "next": "http://vertex.com/api/v1.2/logs?page=31&size=10",
    "first": "http://vertex.com/api/v1.2/logs?page=1&size=10",
    "last": "http://vertex.com/api/v1.2/logs?page=80&size=10"
  },
  "fetchInfo": {
    "totalElements": 5000,
    "size": 10,
    "totslPages": 500,
    "page": 3
  },
  "products": [
    {
      "masterId": "string",
      "name": "string",
      "shortDescription": "string",
      "description": "string",
      "sku": [
        {
          "id": 566,
          "name": "Video Streaming Service",
          "description": "Video streaming service",
          "shortDescription": "Video streaming service",
          "sku": "3423-23423",
          "upc": "2323-234-343",
          "taxCategories": [
            {
              "id": 556,
              "name": "software",
              "confidence": 90,
              "isSelected": "true"
            },
            {
              "id": 557,
              "name": "hardware",
              "confidence": 80,
              "isSelected": "false"
            }
          ]
        }
      ],
      "inActive": true,
      "timestamp": "2019-12-12T13:19:09Z",
      "mappingType": "autoMapped",
      "effectivePeriod": {
        "fromDate": "2019-12-12",
        "toDate": "2019-12-12"
      },
      "taxCategories": [
        {
          "id": 556,
          "name": "sugar contains",
          "confidence": 90,
          "isManually": "true",
          "isSelected": "true"
        }
      ],
      "categories": [
        "Videoserver"
      ],
      "id": 0
    }
  ]
}

```

Product collection

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|pagination|[Pagination](#schemapagination)|false|none|Hypermedia approach for pagination, contains links<br>for current, previous and next pages.|
|fetchInfo|[FetchInfo](#schemafetchinfo)|false|none|Data fetch info.<br>Used for implementing data pagination.|
|products|[[Product](#schemaproduct)]|false|none|none|

<h2 id="tocS_TaxLevel">TaxLevel</h2>
<!-- backwards compatibility -->
<a id="schemataxlevel"></a>
<a id="schema_TaxLevel"></a>
<a id="tocStaxlevel"></a>
<a id="tocstaxlevel"></a>

```json
"state"

```

Tax level

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|Tax level|string|false|none|An enumeration that represents available Tax levels<br>| value        |  description                                |<br>|--------------|---------------------------------------------|<br>| state        | State tax                                   |<br>| country      | Country level tax                           |<br>| jurisdiction | Tax for particullar jurisdiction            ||

#### Enumerated Values

|Property|Value|
|---|---|
|Tax level|state|
|Tax level|country|
|Tax level|jurisdiction|

<h2 id="tocS_TaxRate">TaxRate</h2>
<!-- backwards compatibility -->
<a id="schemataxrate"></a>
<a id="schema_TaxRate"></a>
<a id="tocStaxrate"></a>
<a id="tocstaxrate"></a>

```json
{
  "id": 54,
  "description": "VAT",
  "name": "VAT",
  "taxLevel": "jurisdiction",
  "rules": [
    "s56",
    "s55"
  ],
  "percentage": 7
}

```

Tax rate

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|Tax rate|[Entity](#schemaentity)|false|none|none|
|name|string|false|none|Tax name.|
|description|string|false|none|Tax description.|
|taxLevel|[TaxLevel](#schemataxlevel)|false|none|An enumeration that represents available Tax levels<br>| value        |  description                                |<br>|--------------|---------------------------------------------|<br>| state        | State tax                                   |<br>| country      | Country level tax                           |<br>| jurisdiction | Tax for particullar jurisdiction            ||
|rules|[string]|false|none|none|
|percentage|integer|false|none|Tax percentage.|

<h2 id="tocS_Tax">Tax</h2>
<!-- backwards compatibility -->
<a id="schematax"></a>
<a id="schema_Tax"></a>
<a id="tocStax"></a>
<a id="tocstax"></a>

```json
{
  "rates": [
    {
      "id": 54,
      "description": "VAT",
      "name": "VAT",
      "taxLevel": "jurisdiction",
      "rules": [
        "s56",
        "s55"
      ],
      "percentage": 7
    }
  ],
  "amount": "string"
}

```

Tax

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|rates|[[TaxRate](#schemataxrate)]|false|none|none|
|amount|[Amount](#schemaamount)|false|none|Amont in format is [ISO 20022]. <br>The decimal separator is a dot. NNNN.NN|

<h2 id="tocS_TransactionType">TransactionType</h2>
<!-- backwards compatibility -->
<a id="schematransactiontype"></a>
<a id="schema_TransactionType"></a>
<a id="tocStransactiontype"></a>
<a id="tocstransactiontype"></a>

```json
"new"

```

Transaction Types

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|Transaction Types|string|false|none|Enumeration that represnts supportable Transaction Types <br> | value    | description                                    |<br> |----------|------------------------------------------------|<br> | new      | Default transaction type                       |<br> | complete | Complete                                       |<br> | return   | Return                                         |<br> | cancel   | Transaction  cancelled                         |<br> | adjust   | Transaction is used for price adjustment       ||

#### Enumerated Values

|Property|Value|
|---|---|
|Transaction Types|new|
|Transaction Types|complete|
|Transaction Types|return|
|Transaction Types|cancel|
|Transaction Types|adjustment|

<h2 id="tocS_TransactionStatus">TransactionStatus</h2>
<!-- backwards compatibility -->
<a id="schematransactionstatus"></a>
<a id="schema_TransactionStatus"></a>
<a id="tocStransactionstatus"></a>
<a id="tocstransactionstatus"></a>

```json
"preview"

```

Transaction Status

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|Transaction Status|string|false|none|Enumeration that represnts available Transaction Statuses <br>| value   | description                                   |<br>|---------|-----------------------------------------------|<br>| preview | Precalculation                                |<br>| order   | Order                                         ||

#### Enumerated Values

|Property|Value|
|---|---|
|Transaction Status|preview|
|Transaction Status|order|

<h2 id="tocS_Transaction">Transaction</h2>
<!-- backwards compatibility -->
<a id="schematransaction"></a>
<a id="schema_Transaction"></a>
<a id="tocStransaction"></a>
<a id="tocstransaction"></a>

```json
{
  "masterId": 0,
  "type": "new",
  "status": "preview",
  "order": {
    "masterId": 0,
    "timestamp": "2019-12-12T13:19:09Z",
    "items": [
      {
        "id": 12,
        "productId": 23,
        "masterId": 643,
        "count": 2,
        "name": "t-short",
        "price": 55.44
      }
    ],
    "total": {
      "total": "string",
      "subTotal": "string",
      "totalTax": "string",
      "taxDetails": [
        {
          "rates": [
            {
              "id": 54,
              "description": "VAT",
              "name": "VAT",
              "taxLevel": "jurisdiction",
              "rules": [
                "s56",
                "s55"
              ],
              "percentage": 7
            }
          ],
          "amount": "string"
        }
      ]
    },
    "id": 0
  },
  "id": 0
}

```

Transaction

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|Transaction|[Entity](#schemaentity)|false|none|none|
|masterId|integer|false|none|Transaction unique identifier in master system.|
|type|[TransactionType](#schematransactiontype)|true|none|Enumeration that represnts supportable Transaction Types <br> | value    | description                                    |<br> |----------|------------------------------------------------|<br> | new      | Default transaction type                       |<br> | complete | Complete                                       |<br> | return   | Return                                         |<br> | cancel   | Transaction  cancelled                         |<br> | adjust   | Transaction is used for price adjustment       ||
|status|[TransactionStatus](#schematransactionstatus)|false|none|Enumeration that represnts available Transaction Statuses <br>| value   | description                                   |<br>|---------|-----------------------------------------------|<br>| preview | Precalculation                                |<br>| order   | Order                                         ||
|order|[Order](#schemaorder)|false|none|none|

<h2 id="tocS_Transactions">Transactions</h2>
<!-- backwards compatibility -->
<a id="schematransactions"></a>
<a id="schema_Transactions"></a>
<a id="tocStransactions"></a>
<a id="tocstransactions"></a>

```json
{
  "pagination": {
    "self": "http://vertex.com/api/v1.2/logs?page=30&size=10",
    "prev": "http://vertex.com/api/v1.2/logs?page=29&size=10",
    "next": "http://vertex.com/api/v1.2/logs?page=31&size=10",
    "first": "http://vertex.com/api/v1.2/logs?page=1&size=10",
    "last": "http://vertex.com/api/v1.2/logs?page=80&size=10"
  },
  "fetchInfo": {
    "totalElements": 5000,
    "size": 10,
    "totslPages": 500,
    "page": 3
  },
  "transactions": [
    {
      "masterId": 0,
      "type": "new",
      "status": "preview",
      "order": {
        "masterId": 0,
        "timestamp": "2019-12-12T13:19:09Z",
        "items": [
          {
            "id": 12,
            "productId": 23,
            "masterId": 643,
            "count": 2,
            "name": "t-short",
            "price": 55.44
          }
        ],
        "total": {
          "total": "string",
          "subTotal": "string",
          "totalTax": "string",
          "taxDetails": [
            {
              "rates": [
                {
                  "id": 54,
                  "description": "VAT",
                  "name": "VAT",
                  "taxLevel": "jurisdiction",
                  "rules": [
                    "s56",
                    "s55"
                  ],
                  "percentage": 7
                }
              ],
              "amount": "string"
            }
          ]
        },
        "id": 0
      },
      "id": 0
    }
  ]
}

```

Transaction collection

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|pagination|[Pagination](#schemapagination)|false|none|Hypermedia approach for pagination, contains links<br>for current, previous and next pages.|
|fetchInfo|[FetchInfo](#schemafetchinfo)|false|none|Data fetch info.<br>Used for implementing data pagination.|
|transactions|[[Transaction](#schematransaction)]|false|none|none|

<h2 id="tocS_OrderItem">OrderItem</h2>
<!-- backwards compatibility -->
<a id="schemaorderitem"></a>
<a id="schema_OrderItem"></a>
<a id="tocSorderitem"></a>
<a id="tocsorderitem"></a>

```json
{
  "id": 12,
  "productId": 23,
  "masterId": 643,
  "count": 2,
  "name": "t-short",
  "price": 55.44
}

```

Order Item

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|Order Item|[Entity](#schemaentity)|false|none|none|
|masterId|integer|false|none|An item unique identifier in external system.|
|productId|integer|false|none|Product id.|
|name|string|false|none|Item name.|
|count|integer|false|none|Item count.|
|sku|string|false|none|Stock Keeping Unit.|
|price|[Amount](#schemaamount)|false|none|Amont in format is [ISO 20022]. <br>The decimal separator is a dot. NNNN.NN|

<h2 id="tocS_OrderTotal">OrderTotal</h2>
<!-- backwards compatibility -->
<a id="schemaordertotal"></a>
<a id="schema_OrderTotal"></a>
<a id="tocSordertotal"></a>
<a id="tocsordertotal"></a>

```json
{
  "total": "string",
  "subTotal": "string",
  "totalTax": "string",
  "taxDetails": [
    {
      "rates": [
        {
          "id": 54,
          "description": "VAT",
          "name": "VAT",
          "taxLevel": "jurisdiction",
          "rules": [
            "s56",
            "s55"
          ],
          "percentage": 7
        }
      ],
      "amount": "string"
    }
  ]
}

```

Order Total

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|total|[Amount](#schemaamount)|false|none|Amont in format is [ISO 20022]. <br>The decimal separator is a dot. NNNN.NN|
|subTotal|[Amount](#schemaamount)|false|none|Amont in format is [ISO 20022]. <br>The decimal separator is a dot. NNNN.NN|
|totalTax|[Amount](#schemaamount)|false|none|Amont in format is [ISO 20022]. <br>The decimal separator is a dot. NNNN.NN|
|taxDetails|[[Tax](#schematax)]|false|none|none|

<h2 id="tocS_Order">Order</h2>
<!-- backwards compatibility -->
<a id="schemaorder"></a>
<a id="schema_Order"></a>
<a id="tocSorder"></a>
<a id="tocsorder"></a>

```json
{
  "masterId": 0,
  "timestamp": "2019-12-12T13:19:09Z",
  "items": [
    {
      "id": 12,
      "productId": 23,
      "masterId": 643,
      "count": 2,
      "name": "t-short",
      "price": 55.44
    }
  ],
  "total": {
    "total": "string",
    "subTotal": "string",
    "totalTax": "string",
    "taxDetails": [
      {
        "rates": [
          {
            "id": 54,
            "description": "VAT",
            "name": "VAT",
            "taxLevel": "jurisdiction",
            "rules": [
              "s56",
              "s55"
            ],
            "percentage": 7
          }
        ],
        "amount": "string"
      }
    ]
  },
  "id": 0
}

```

Order

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|Order|[Entity](#schemaentity)|false|none|none|
|masterId|integer|false|none|An order unique identifier in external system.|
|timestamp|[DateTime](#schemadatetime)|false|none|Date-time in format [ISO-8601], YYYY-MM-DDThh:mm:ssTZD|
|items|[[OrderItem](#schemaorderitem)]|false|none|none|
|total|[OrderTotal](#schemaordertotal)|false|none|Order total.|

<h2 id="tocS_TransactionSummary">TransactionSummary</h2>
<!-- backwards compatibility -->
<a id="schematransactionsummary"></a>
<a id="schema_TransactionSummary"></a>
<a id="tocStransactionsummary"></a>
<a id="tocstransactionsummary"></a>

```json
{
  "countTrans": 343,
  "totalSales": 6565.9,
  "totalTax": 34.3
}

```

Transaction Summary

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|countTrans|integer|false|none|Number of the transactions.|
|totalSales|[Amount](#schemaamount)|false|none|Amont in format is [ISO 20022]. <br>The decimal separator is a dot. NNNN.NN|
|totalTax|[Amount](#schemaamount)|false|none|Amont in format is [ISO 20022]. <br>The decimal separator is a dot. NNNN.NN|

<h2 id="tocS_LogRequest">LogRequest</h2>
<!-- backwards compatibility -->
<a id="schemalogrequest"></a>
<a id="schema_LogRequest"></a>
<a id="tocSlogrequest"></a>
<a id="tocslogrequest"></a>

```json
{
  "url": "http://vertex.com/api/v1.2/transactions/123?page=1",
  "uri": "api/v1.2/transactions/123",
  "query": "page=1",
  "method": "GET"
}

```

Log Request

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|query|string|false|none|Request query.|
|uri|string|false|none|Request uri.|
|url|string|false|none|Request url.|
|body|string|false|none|Request body.|
|method|string|false|none|Request method.|

<h2 id="tocS_LogResponse">LogResponse</h2>
<!-- backwards compatibility -->
<a id="schemalogresponse"></a>
<a id="schema_LogResponse"></a>
<a id="tocSlogresponse"></a>
<a id="tocslogresponse"></a>

```json
{
  "code": "200",
  "content": "log trace"
}

```

Log Response

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|code|string|false|none|Response code.|
|content|string|false|none|Response content.|

<h2 id="tocS_Log">Log</h2>
<!-- backwards compatibility -->
<a id="schemalog"></a>
<a id="schema_Log"></a>
<a id="tocSlog"></a>
<a id="tocslog"></a>

```json
{
  "request": {
    "url": "http://vertex.com/api/v1.2/transactions/123?page=1",
    "uri": "api/v1.2/transactions/123",
    "query": "page=1",
    "method": "GET"
  },
  "response": {
    "code": "200",
    "content": "log trace"
  },
  "date": "2019-12-12T13:19:09Z",
  "correlationId": "string"
}

```

Log

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|request|[LogRequest](#schemalogrequest)|false|none|none|
|response|[LogResponse](#schemalogresponse)|false|none|none|
|date|[DateTime](#schemadatetime)|false|none|Date-time in format [ISO-8601], YYYY-MM-DDThh:mm:ssTZD|
|correlationId|string|false|none|Unique identifier that helps to trace request.|

<h2 id="tocS_Logs">Logs</h2>
<!-- backwards compatibility -->
<a id="schemalogs"></a>
<a id="schema_Logs"></a>
<a id="tocSlogs"></a>
<a id="tocslogs"></a>

```json
{
  "logs": [
    {
      "request": {
        "url": "http://vertex.com/api/v1.2/transactions/123?page=1",
        "uri": "api/v1.2/transactions/123",
        "query": "page=1",
        "method": "GET"
      },
      "response": {
        "code": "200",
        "content": "log trace"
      },
      "date": "2019-12-12T13:19:09Z",
      "correlationId": "string"
    }
  ]
}

```

Log collection

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|logs|[[Log](#schemalog)]|false|none|[API request log.<br>]|

