---
title: API for Tax Calculator v0.0.2 alfa, Dec 2019
language_tabs:
  - shell: Curl
  - java: Unirest
toc_footers: []
includes: []
search: false
highlight_theme: darkula
headingLevel: 2

---

<!-- Generator: Widdershins v3.6.6 -->

<h1 id="api-for-tax-calculator">API for Tax Calculator v0.0.2 alfa, Dec 2019</h1>

> Scroll down for code samples, example requests and responses. Select a language for code samples from the tabs above or the mobile navigation menu.

Vertex API for Tax Calculator.

Base URLs:

* <a href="/api/v1.2/saletax">/api/v1.2/saletax</a>

Web: <a href="http://www.vertex.com">API Support</a> 
License: <a href="https://www.apache.org/licenses/LICENSE-2.0.html">Apache 2.0</a>

# Authentication

- HTTP Authentication, scheme: bearer 

* API Key (apiKeyAuth)
    - Parameter Name: **apikey**, in: header. API key to authorize requests.

<div class="total">
<h1 id="api-for-tax-calculator-notification-template">Notification template</h1>

<div class="operation">

## GET/Return registered templates.

> Code samples

```shell
# You can also use wget
curl -X GET /api/v1.2/saletax/templates \
  -H 'Accept: application/json' \
  -H 'apikey: API_KEY'

```

```java
URL obj = new URL("/api/v1.2/saletax/templates");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

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
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Returns collectin of the templates for 
current sale channel.|[Templates](#schematemplates)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Unable to find any template.|[Errors](#schemaerrors)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKeyAuth
</aside>

</div>

<div class="operation">

## POST/Register new template.

> Code samples

```shell
# You can also use wget
curl -X POST /api/v1.2/saletax/templates \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'apikey: API_KEY'

```

```java
URL obj = new URL("/api/v1.2/saletax/templates");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

`POST /templates`

The endpoint is used to register new template
for current sale channel.

> Body parameter

```json
{
  "name": "email",
  "body": " Dear {name}, Your account is activated."
}
```

<h3 id="register-new-template.-parameters">Parameters</h3>

|Name|In|Type|Required|Description3|
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
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|Template is added successfully.|[TemplateEntity](#schematemplateentity)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Unable to register template.|[Errors](#schemaerrors)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Unable to register template. 
Template with the same name is already registered.|[Errors](#schemaerrors)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKeyAuth
</aside>

</div>

<div class="operation">

## GET/Get template.

> Code samples

```shell
# You can also use wget
curl -X GET /api/v1.2/saletax/templates/{templateId} \
  -H 'Accept: application/json' \
  -H 'apikey: API_KEY'

```

```java
URL obj = new URL("/api/v1.2/saletax/templates/{templateId}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

`GET /templates/{templateId}`

Returns template with defined id. 

<h3 id="get-template.-parameters">Parameters</h3>

|Name|In|Type|Required|Description3|
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
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Template|[TemplateEntity](#schematemplateentity)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Unable to find template.|[Errors](#schemaerrors)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKeyAuth
</aside>

</div>

<div class="operation">

## PATCH/Update template.

> Code samples

```shell
# You can also use wget
curl -X PATCH /api/v1.2/saletax/templates/{templateId} \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'apikey: API_KEY'

```

```java
URL obj = new URL("/api/v1.2/saletax/templates/{templateId}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("PATCH");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

`PATCH /templates/{templateId}`

Makes changes in the defined template.

> Body parameter

```json
{
  "name": "email",
  "body": " Dear {name}, Your account is activated."
}
```

<h3 id="update-template.-parameters">Parameters</h3>

|Name|In|Type|Required|Description3|
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
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|Template is updated successfully.|[TemplateEntity](#schematemplateentity)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Unable to update template.|[Errors](#schemaerrors)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKeyAuth
</aside>

</div>

<div class="operation">

## DELETE/Delete template.

> Code samples

```shell
# You can also use wget
curl -X DELETE /api/v1.2/saletax/templates/{templateId} \
  -H 'Accept: application/json' \
  -H 'apikey: API_KEY'

```

```java
URL obj = new URL("/api/v1.2/saletax/templates/{templateId}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("DELETE");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

`DELETE /templates/{templateId}`

Deletes the defined template. 

<h3 id="delete-template.-parameters">Parameters</h3>

|Name|In|Type|Required|Description3|
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
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Template is deleted successfully.|[TemplateEntity](#schematemplateentity)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Template not found.|[Errors](#schemaerrors)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKeyAuth
</aside>

</div>

<div class="operation">

## POST/Send notification.

> Code samples

```shell
# You can also use wget
curl -X POST /api/v1.2/saletax/templates/{templateId}/send \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'apikey: API_KEY'

```

```java
URL obj = new URL("/api/v1.2/saletax/templates/{templateId}/send");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

`POST /templates/{templateId}/send`

The endpoint is used to notify current 
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

|Name|In|Type|Required|Description3|
|---|---|---|---|---|
|templateId|path|string|true|Template id.|
|body|body|[Message](#schemamessage)|true|none|

#### Detailed descriptions

**templateId**: Template id.

> Example responses

> 201 Response

```json
{
  "id": 624,
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
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|Notification sent successfully.
Returns fulfilled message.|[MessageEntity](#schemamessageentity)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Unable to send notification.|[Errors](#schemaerrors)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKeyAuth
</aside>

</div>

</div>

<div class="total">
<h1 id="api-for-tax-calculator-account-management">Account Management</h1>

<div class="operation">

## POST/Create new account.

> Code samples

```shell
# You can also use wget
curl -X POST /api/v1.2/saletax/accounts \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'platform: string'

```

```java
URL obj = new URL("/api/v1.2/saletax/accounts");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

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
  "name": "Cofe shop",
  "email": "shop@vertex.com",
  "password": "password"
}
```

<h3 id="create-new-account.-parameters">Parameters</h3>

|Name|In|Type|Required|Description3|
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
  "email": "shop@vertex.com"
}
```

<h3 id="create-new-account.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|Account created successfully.|[AccountEntity](#schemaaccountentity)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Unable to create account.|[Errors](#schemaerrors)|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|Account already exists.|[Errors](#schemaerrors)|

<aside class="success">
This operation does not require authentication
</aside>

</div>

<div class="operation">

## GET/Get account information.

> Code samples

```shell
# You can also use wget
curl -X GET /api/v1.2/saletax/accounts/info \
  -H 'Accept: application/json' \
  -H 'apikey: API_KEY'

```

```java
URL obj = new URL("/api/v1.2/saletax/accounts/info");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

`GET /accounts/info`

Returns all account information which 
tax calculation requires for defined account.
For sale platform email as a query can be 
used as an account identifier.

<h3 id="get-account-information.-parameters">Parameters</h3>

|Name|In|Type|Required|Description3|
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
    "email": "shop@vertex.com"
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

<h3 id="get-account-information.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Returns account information.|[AccountInfo](#schemaaccountinfo)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Unable to find an account.|[Errors](#schemaerrors)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKeyAuth
</aside>

</div>

<div class="operation">

## PATCH/Update an account.

> Code samples

```shell
# You can also use wget
curl -X PATCH /api/v1.2/saletax/accounts/{email} \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```java
URL obj = new URL("/api/v1.2/saletax/accounts/{email}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("PATCH");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

`PATCH /accounts/{email}`

Updates account password.

> Body parameter

```json
{
  "name": "Cofe shop",
  "email": "shop@vertex.com",
  "password": "password"
}
```

<h3 id="update-an-account.-parameters">Parameters</h3>

|Name|In|Type|Required|Description3|
|---|---|---|---|---|
|body|body|[Account](#schemaaccount)|true|none|
|email|path|string|true|Account identifier.|

#### Detailed descriptions

**email**: Account identifier.

> Example responses

> 204 Response

```json
{
  "id": 656,
  "name": "Cofe shop",
  "email": "shop@vertex.com"
}
```

<h3 id="update-an-account.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|204|[No Content](https://tools.ietf.org/html/rfc7231#section-6.3.5)|Account updated successfully.|[AccountEntity](#schemaaccountentity)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Unable to update account.|[Errors](#schemaerrors)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Account not found.|[Errors](#schemaerrors)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
jwtAuth, apiKeyAuth
</aside>

</div>

<div class="operation">

## DELETE/Make an account inactive.

> Code samples

```shell
# You can also use wget
curl -X DELETE /api/v1.2/saletax/accounts/{email} \
  -H 'Accept: application/json' \
  -H 'apikey: API_KEY'

```

```java
URL obj = new URL("/api/v1.2/saletax/accounts/{email}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("DELETE");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

`DELETE /accounts/{email}`

"Make defined account inactive.

<h3 id="make-an-account-inactive.-parameters">Parameters</h3>

|Name|In|Type|Required|Description3|
|---|---|---|---|---|
|email|path|string|true|Account identifier.|

#### Detailed descriptions

**email**: Account identifier.

> Example responses

> 200 Response

```json
{
  "id": 656,
  "name": "Cofe shop",
  "email": "shop@vertex.com"
}
```

<h3 id="make-an-account-inactive.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Account updated successfully.|[AccountEntity](#schemaaccountentity)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Unable to make an account inactive.|[Errors](#schemaerrors)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKeyAuth
</aside>

</div>

<div class="operation">

## POST/Get a link for resetting account password.

> Code samples

```shell
# You can also use wget
curl -X POST /api/v1.2/saletax/accounts/{email}/resetPassword \
  -H 'Accept: application/json'

```

```java
URL obj = new URL("/api/v1.2/saletax/accounts/{email}/resetPassword");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

`POST /accounts/{email}/resetPassword`

The endpoint is used to generate temporary link which 
can be used for resetting account password.

<h3 id="get-a-link-for-resetting-account-password.-parameters">Parameters</h3>

|Name|In|Type|Required|Description3|
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
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|Link created successfully.|[Link](#schemalink)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Unable to create a link.|[Errors](#schemaerrors)|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|Unble to find account.|[Errors](#schemaerrors)|

<aside class="success">
This operation does not require authentication
</aside>

</div>

</div>

<div class="total">
<h1 id="api-for-tax-calculator-token-management">Token Management</h1>

<div class="operation">

## GET/Get active tokens

> Code samples

```shell
# You can also use wget
curl -X GET /api/v1.2/saletax/tokens \
  -H 'Accept: application/json' \
  -H 'apikey: API_KEY'

```

```java
URL obj = new URL("/api/v1.2/saletax/tokens");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

`GET /tokens`

Returns collection of active tokens for current sale point.

<h3 id="get-active-tokens-parameters">Parameters</h3>

|Name|In|Type|Required|Description3|
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
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Returns token.|[Tokens](#schematokens)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Unable to return tokens.|[Errors](#schemaerrors)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKeyAuth
</aside>

</div>

<div class="operation">

## POST/Generate token.

> Code samples

```shell
# You can also use wget
curl -X POST /api/v1.2/saletax/tokens \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'apikey: API_KEY'

```

```java
URL obj = new URL("/api/v1.2/saletax/tokens");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

`POST /tokens`

Creates a new token for API call.

> Body parameter

```json
{
  "type": "public"
}
```

<h3 id="generate-token.-parameters">Parameters</h3>

|Name|In|Type|Required|Description3|
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

<h3 id="generate-token.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|Returns a token.|[Token](#schematoken)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Unable to create token.|[Errors](#schemaerrors)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKeyAuth, jwtAuth
</aside>

</div>

<div class="operation">

## DELETE/Revoke the token.

> Code samples

```shell
# You can also use wget
curl -X DELETE /api/v1.2/saletax/tokens/{token} \
  -H 'Accept: application/json' \
  -H 'apikey: API_KEY'

```

```java
URL obj = new URL("/api/v1.2/saletax/tokens/{token}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("DELETE");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

`DELETE /tokens/{token}`

The method allows to deactivate the token.
But a sale channel should have as minimum one 
token for production environment and one for sandbox.
They can't be revoked.

<h3 id="revoke-the-token.-parameters">Parameters</h3>

|Name|In|Type|Required|Description3|
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
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|The token revoken successfully.|[Token](#schematoken)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Unable to revoke token.|[Errors](#schemaerrors)|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|Unable to revoke the last token.|[Errors](#schemaerrors)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKeyAuth
</aside>

</div>

</div>

<div class="total">
<h1 id="api-for-tax-calculator-contact-information">Contact Information</h1>

<div class="operation">

## GET/Get contact information.

> Code samples

```shell
# You can also use wget
curl -X GET /api/v1.2/saletax/contacts/{contactId} \
  -H 'Accept: application/json' \
  -H 'apikey: API_KEY'

```

```java
URL obj = new URL("/api/v1.2/saletax/contacts/{contactId}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

`GET /contacts/{contactId}`

The endpoint returns contact information.

<h3 id="get-contact-information.-parameters">Parameters</h3>

|Name|In|Type|Required|Description3|
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
    "code@vertex.com"
  ],
  "phones": [
    "444-333-888"
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
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Returns contact information.|[ContactInfoEntity](#schemacontactinfoentity)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Unable to add contact information.|[Errors](#schemaerrors)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKeyAuth
</aside>

</div>

<div class="operation">

## POST/Add contact information.

> Code samples

```shell
# You can also use wget
curl -X POST /api/v1.2/saletax/contacts \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'apikey: API_KEY'

```

```java
URL obj = new URL("/api/v1.2/saletax/contacts");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

`POST /contacts`

The endpoint is used to add contact information.

> Body parameter

```json
{
  "location": {
    "type": "administrative",
    "city": "KNG OF PRUSSA",
    "state": "PA",
    "zip": "19406",
    "zipExt": "1101",
    "addressLine1": "875 MANCILL MILL RD"
  },
  "emails": [
    "code@vertex.com"
  ],
  "phones": [
    "444-333-888"
  ],
  "id": 464,
  "title": "Mr",
  "name": "Oleksiy",
  "lastName": "Luchkovskiy"
}
```

<h3 id="add-contact-information.-parameters">Parameters</h3>

|Name|In|Type|Required|Description3|
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
    "code@vertex.com"
  ],
  "phones": [
    "444-333-888"
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
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|Contact information added successfully.|[ContactInfoEntity](#schemacontactinfoentity)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Unable to add contact information.|[Errors](#schemaerrors)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKeyAuth
</aside>

</div>

<div class="operation">

## PATCH/Update contact information.

> Code samples

```shell
# You can also use wget
curl -X PATCH /api/v1.2/saletax/contacts/{contactId} \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'apikey: API_KEY'

```

```java
URL obj = new URL("/api/v1.2/saletax/contacts/{contactId}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("PATCH");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

`PATCH /contacts/{contactId}`

The endpoint is used to update contact information.

> Body parameter

```json
{
  "location": {
    "type": "administrative",
    "city": "KNG OF PRUSSA",
    "state": "PA",
    "zip": "19406",
    "zipExt": "1101",
    "addressLine1": "875 MANCILL MILL RD"
  },
  "emails": [
    "code@vertex.com"
  ],
  "phones": [
    "444-333-888"
  ],
  "id": 464,
  "title": "Mr",
  "name": "Oleksiy",
  "lastName": "Luchkovskiy"
}
```

<h3 id="update-contact-information.-parameters">Parameters</h3>

|Name|In|Type|Required|Description3|
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
    "code@vertex.com"
  ],
  "phones": [
    "444-333-888"
  ],
  "id": 464,
  "title": "Mr",
  "name": "Oleksiy",
  "lastName": "Luchkovskiy"
}
```

<h3 id="update-contact-information.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|204|[No Content](https://tools.ietf.org/html/rfc7231#section-6.3.5)|Contact information updated successfully|[ContactInfoEntity](#schemacontactinfoentity)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Unable to update contact information.|[Errors](#schemaerrors)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Unable to update contact information, 
account or contact information not found.|[Errors](#schemaerrors)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKeyAuth
</aside>

</div>

</div>

<div class="total">
<h1 id="api-for-tax-calculator-location">Location</h1>

<div class="operation">

## GET/Get account locations.

> Code samples

```shell
# You can also use wget
curl -X GET /api/v1.2/saletax/locations \
  -H 'Accept: application/json' \
  -H 'apikey: API_KEY'

```

```java
URL obj = new URL("/api/v1.2/saletax/locations");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

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
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Returns location collection|[Locations](#schemalocations)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Locations not found.|[Errors](#schemaerrors)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKeyAuth
</aside>

</div>

<div class="operation">

## POST/Add location.

> Code samples

```shell
# You can also use wget
curl -X POST /api/v1.2/saletax/locations \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'apikey: API_KEY'

```

```java
URL obj = new URL("/api/v1.2/saletax/locations");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

`POST /locations`

The endpoint is used to add location, place
where the sale poit is operated.

Any number of phisical locations and 
only one adminisrative location are possible.

> Body parameter

```json
{
  "type": "administrative",
  "city": "KNG OF PRUSSA",
  "state": "PA",
  "zip": "19406",
  "zipExt": "1101",
  "addressLine1": "875 MANCILL MILL RD"
}
```

<h3 id="add-location.-parameters">Parameters</h3>

|Name|In|Type|Required|Description3|
|---|---|---|---|---|
|body|body|[Location](#schemalocation)|true|none|

> Example responses

> 201 Response

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

<h3 id="add-location.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|Location added successfully|[LocationEntity](#schemalocationentity)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Unable to add location. 
Location is already added.|[Errors](#schemaerrors)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKeyAuth
</aside>

</div>

<div class="operation">

## GET/Get location.

> Code samples

```shell
# You can also use wget
curl -X GET /api/v1.2/saletax/locations/{locationId} \
  -H 'Accept: application/json' \
  -H 'apikey: API_KEY'

```

```java
URL obj = new URL("/api/v1.2/saletax/locations/{locationId}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

`GET /locations/{locationId}`

Returns location with defined id.

<h3 id="get-location.-parameters">Parameters</h3>

|Name|In|Type|Required|Description3|
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
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Returns location|[LocationEntity](#schemalocationentity)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Location not found.|[Errors](#schemaerrors)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKeyAuth
</aside>

</div>

<div class="operation">

## PATCH/Update location.

> Code samples

```shell
# You can also use wget
curl -X PATCH /api/v1.2/saletax/locations/{locationId} \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'apikey: API_KEY'

```

```java
URL obj = new URL("/api/v1.2/saletax/locations/{locationId}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("PATCH");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

`PATCH /locations/{locationId}`

The endpoint is used to update location.

> Body parameter

```json
{
  "type": "administrative",
  "city": "KNG OF PRUSSA",
  "state": "PA",
  "zip": "19406",
  "zipExt": "1101",
  "addressLine1": "875 MANCILL MILL RD"
}
```

<h3 id="update-location.-parameters">Parameters</h3>

|Name|In|Type|Required|Description3|
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
|204|[No Content](https://tools.ietf.org/html/rfc7231#section-6.3.5)|Location is updated successfully.|[LocationEntity](#schemalocationentity)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Unable to update location.|[Errors](#schemaerrors)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Unable to update location. 
Location not found.|[Errors](#schemaerrors)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKeyAuth
</aside>

</div>

<div class="operation">

## DELETE/Delete location.

> Code samples

```shell
# You can also use wget
curl -X DELETE /api/v1.2/saletax/locations/{locationId} \
  -H 'Accept: application/json' \
  -H 'apikey: API_KEY'

```

```java
URL obj = new URL("/api/v1.2/saletax/locations/{locationId}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("DELETE");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

`DELETE /locations/{locationId}`

The endpoint is used to delete location.
If account should have one location as minimum.
It can't be removed.

<h3 id="delete-location.-parameters">Parameters</h3>

|Name|In|Type|Required|Description3|
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
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Location deleted successfully.|[LocationEntity](#schemalocationentity)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Location not found.|[Errors](#schemaerrors)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKeyAuth
</aside>

</div>

<div class="operation">

## POST/Standardize a location.

> Code samples

```shell
# You can also use wget
curl -X POST /api/v1.2/saletax/locations/standardize \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'apikey: API_KEY'

```

```java
URL obj = new URL("/api/v1.2/saletax/locations/standardize");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

`POST /locations/standardize`

Validates location and return result in standard format.
It helps to keep addresses in unified format and 
find zip extension.

> Body parameter

```json
{
  "type": "administrative",
  "city": "KNG OF PRUSSA",
  "state": "PA",
  "zip": "19406",
  "zipExt": "1101",
  "addressLine1": "875 MANCILL MILL RD"
}
```

<h3 id="standardize-a-location.-parameters">Parameters</h3>

|Name|In|Type|Required|Description3|
|---|---|---|---|---|
|body|body|[Location](#schemalocation)|false|none|

> Example responses

> 200 Response

```json
{
  "type": "administrative",
  "city": "KNG OF PRUSSA",
  "state": "PA",
  "zip": "19406",
  "zipExt": "1101",
  "addressLine1": "875 MANCILL MILL RD"
}
```

<h3 id="standardize-a-location.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Returns location is standard format.|[Location](#schemalocation)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Unable to validate defined location.|[Errors](#schemaerrors)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Unable to validate defined location.
Location has invalid format.|[Errors](#schemaerrors)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKeyAuth
</aside>

</div>

</div>

<div class="total">
<h1 id="api-for-tax-calculator-business-info">Business Info</h1>

<div class="operation">

## GET/Get business information.

> Code samples

```shell
# You can also use wget
curl -X GET /api/v1.2/saletax/businessInfos \
  -H 'Accept: application/json' \
  -H 'apikey: API_KEY'

```

```java
URL obj = new URL("/api/v1.2/saletax/businessInfos");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

`GET /businessInfos`

Returns business information 
for current sales point.

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
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Returns business information.|[BusinessInfoEntity](#schemabusinessinfoentity)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Business information not found.|[Errors](#schemaerrors)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKeyAuth
</aside>

</div>

<div class="operation">

## POST/Add business information.

> Code samples

```shell
# You can also use wget
curl -X POST /api/v1.2/saletax/businessInfos \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'apikey: API_KEY'

```

```java
URL obj = new URL("/api/v1.2/saletax/businessInfos");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

`POST /businessInfos`

The endpoint is used to add business information.

> Body parameter

```json
{
  "businessName": "Cofe shop LTD",
  "fedTaxId": "2321-2323-2132"
}
```

<h3 id="add-business-information.-parameters">Parameters</h3>

|Name|In|Type|Required|Description3|
|---|---|---|---|---|
|body|body|[BusinessInfo](#schemabusinessinfo)|true|none|

> Example responses

> 201 Response

```json
{
  "businessName": "Cofe shop LTD",
  "fedTaxId": "2321-2323-2132"
}
```

<h3 id="add-business-information.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|Business information added successfully.|[BusinessInfo](#schemabusinessinfo)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Unable to add business information.|[Errors](#schemaerrors)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Unable to add business information.
Business infomatin aleready added.|[Errors](#schemaerrors)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKeyAuth
</aside>

</div>

<div class="operation">

## PATCH/Update business information.

> Code samples

```shell
# You can also use wget
curl -X PATCH /api/v1.2/saletax/businessInfos/{businessInfoId} \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'apikey: API_KEY'

```

```java
URL obj = new URL("/api/v1.2/saletax/businessInfos/{businessInfoId}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("PATCH");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

`PATCH /businessInfos/{businessInfoId}`

Update business information.

> Body parameter

```json
{
  "businessName": "Cofe shop LTD",
  "fedTaxId": "2321-2323-2132"
}
```

<h3 id="update-business-information.-parameters">Parameters</h3>

|Name|In|Type|Required|Description3|
|---|---|---|---|---|
|body|body|[BusinessInfo](#schemabusinessinfo)|true|none|
|businessInfoId|path|string|true|Business Info Id. |

#### Detailed descriptions

**businessInfoId**: Business Info Id. 

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
|204|[No Content](https://tools.ietf.org/html/rfc7231#section-6.3.5)|Business information updated sucessfully.|[BusinessInfoEntity](#schemabusinessinfoentity)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Unable to update business information.|[Errors](#schemaerrors)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Unable to update business information.
Business information not found.|[Errors](#schemaerrors)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKeyAuth
</aside>

</div>

</div>

<div class="total">
<h1 id="api-for-tax-calculator-product-catalog">Product Catalog</h1>

<div class="operation">

## GET/Return available product catalogs.

> Code samples

```shell
# You can also use wget
curl -X GET /api/v1.2/saletax/catalogs \
  -H 'Accept: application/json' \
  -H 'apikey: API_KEY'

```

```java
URL obj = new URL("/api/v1.2/saletax/catalogs");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

`GET /catalogs`

Returns product catalogs for current sale point.
SBT has only one catalog.
Partner is able to get set of the catalogs. 

> Example responses

> 200 Response

```json
{
  "catalogs": [
    {
      "id": 0,
      "salePoint": "string",
      "name": "string",
      "merchantId": 0,
      "platformId": 0
    }
  ]
}
```

<h3 id="return-available-product-catalogs.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Returns product catalog.|[ProductCatalogs](#schemaproductcatalogs)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Unable to find product calalog.|[Errors](#schemaerrors)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKeyAuth
</aside>

</div>

<div class="operation">

## POST/Upload and validate product catalog. 
Return a process status.

> Code samples

```shell
# You can also use wget
curl -X POST /api/v1.2/saletax/catalogs \
  -H 'Accept: application/json' \
  -H 'apikey: API_KEY'

```

```java
URL obj = new URL("/api/v1.2/saletax/catalogs");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

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
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|Returns a link which is used for checking upload 
processing status.|[Link](#schemalink)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Unable to upload catalog.|[Errors](#schemaerrors)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Catalog has invalid structure.|[Errors](#schemaerrors)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKeyAuth
</aside>

</div>

<div class="operation">

## GET/Return product catalog

> Code samples

```shell
# You can also use wget
curl -X GET /api/v1.2/saletax/catalogs/{catalogId} \
  -H 'Accept: application/json' \
  -H 'apikey: API_KEY'

```

```java
URL obj = new URL("/api/v1.2/saletax/catalogs/{catalogId}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

`GET /catalogs/{catalogId}`

Returns product catalog with defined id. 

<h3 id="return-product-catalog-parameters">Parameters</h3>

|Name|In|Type|Required|Description3|
|---|---|---|---|---|
|catalogId|path|integer|true|Catalog id.|

#### Detailed descriptions

**catalogId**: Catalog id.

> Example responses

> 200 Response

```json
{
  "id": 0,
  "salePoint": "string",
  "name": "string",
  "merchantId": 0,
  "platformId": 0
}
```

<h3 id="return-product-catalog-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Return product catalog|[ProductCatalogEntity](#schemaproductcatalogentity)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Unable to find product catalog.|[Errors](#schemaerrors)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKeyAuth
</aside>

</div>

<div class="operation">

## POST/Remap tax categories.

> Code samples

```shell
# You can also use wget
curl -X POST /api/v1.2/saletax/catalogs/{catalogId}/map \
  -H 'Accept: application/json' \
  -H 'apikey: API_KEY'

```

```java
URL obj = new URL("/api/v1.2/saletax/catalogs/{catalogId}/map");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

`POST /catalogs/{catalogId}/map`

Remaps/Maps tax categories for new/updated products only.
Processing product catalog is an asynchronous process.
Endpoint returns a link for checking process status.

<h3 id="remap-tax-categories.-parameters">Parameters</h3>

|Name|In|Type|Required|Description3|
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
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|Returns a link which for checking process status.|[Link](#schemalink)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Unable to find catalog.|[Errors](#schemaerrors)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKeyAuth
</aside>

</div>

<div class="operation">

## GET/Get product catalog processing status

> Code samples

```shell
# You can also use wget
curl -X GET /api/v1.2/saletax/catalogs/{processId}/status \
  -H 'Accept: application/json' \
  -H 'apikey: API_KEY'

```

```java
URL obj = new URL("/api/v1.2/saletax/catalogs/{processId}/status");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

`GET /catalogs/{processId}/status`

Processing product catalog is an asynchronous process.
The endpoint returns product catalog processing status.

<h3 id="get-product-catalog-processing-status-parameters">Parameters</h3>

|Name|In|Type|Required|Description3|
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
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Returns processing status.|[ProcessingStatus](#schemaprocessingstatus)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Unable to return processing status.
Invalid process identifier.|[Errors](#schemaerrors)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKeyAuth
</aside>

</div>

<div class="operation">

## POST/Accept product catalog categorization.

> Code samples

```shell
# You can also use wget
curl -X POST /api/v1.2/saletax/catalogs/{catalogId}/accept \
  -H 'Accept: application/json' \
  -H 'apikey: API_KEY'

```

```java
URL obj = new URL("/api/v1.2/saletax/catalogs/{catalogId}/accept");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

`POST /catalogs/{catalogId}/accept`

Accept product catalog categorization. 

<h3 id="accept-product-catalog-categorization.-parameters">Parameters</h3>

|Name|In|Type|Required|Description3|
|---|---|---|---|---|
|catalogId|path|integer|true|Catalog Id. |

#### Detailed descriptions

**catalogId**: Catalog Id. 

> Example responses

> 201 Response

```json
{}
```

<h3 id="accept-product-catalog-categorization.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|Customer is agree with tax categorization.|[Object](#schemaobject)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Invalid identifier, catalog not found
or processing is not finished.|[Errors](#schemaerrors)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKeyAuth
</aside>

</div>

<div class="operation">

## POST/Download product catalog.

> Code samples

```shell
# You can also use wget
curl -X POST /api/v1.2/saletax/catalogs/{catalogId}/load \
  -H 'Accept: application/json' \
  -H 'apikey: API_KEY'

```

```java
URL obj = new URL("/api/v1.2/saletax/catalogs/{catalogId}/load");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

`POST /catalogs/{catalogId}/load`

Allows to download product catalogue for 
new/updated products only.

<h3 id="download-product-catalog.-parameters">Parameters</h3>

|Name|In|Type|Required|Description3|
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
  "platformId": 0
}
```

<h3 id="download-product-catalog.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|Returns a product catalog.|[ProductCatalog](#schemaproductcatalog)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Unable to return catalogue.|[Errors](#schemaerrors)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Invalid product catalog identifier.|[Errors](#schemaerrors)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKeyAuth
</aside>

</div>

</div>

<div class="total">
<h1 id="api-for-tax-calculator-product">Product</h1>

<div class="operation">

## GET/Lookup products from the defined catalog.

> Code samples

```shell
# You can also use wget
curl -X GET /api/v1.2/saletax/catalogs/{catalogId}/products \
  -H 'Accept: application/json' \
  -H 'apikey: API_KEY'

```

```java
URL obj = new URL("/api/v1.2/saletax/catalogs/{catalogId}/products");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

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

|Name|In|Type|Required|Description3|
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
      "id": 0,
      "salePoint": "string",
      "masterId": "string",
      "name": "string",
      "image": {
        "url": "https//stripe.com/images/img.png",
        "width": 32,
        "height": 32
      },
      "shortDescription": "string",
      "description": "string",
      "inActive": true,
      "timestamp": "2010-10-11T21:44:22Z2",
      "mappingType": "autoMapped",
      "effectivePeriod": {
        "fromDate": "2010-10-11",
        "toDate": "2010-10-11"
      }
    }
  ]
}
```

<h3 id="lookup-products-from-the-defined-catalog.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|Returns collection of the products.|[Products](#schemaproducts)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Product catalog not found.|[Errors](#schemaerrors)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKeyAuth
</aside>

</div>

<div class="operation">

## POST/Add product to the catalog.

> Code samples

```shell
# You can also use wget
curl -X POST /api/v1.2/saletax/catalogs/{catalogId}/products \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'apikey: API_KEY'

```

```java
URL obj = new URL("/api/v1.2/saletax/catalogs/{catalogId}/products");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

`POST /catalogs/{catalogId}/products`

Add product to the catalog. 

> Body parameter

```json
{
  "masterId": "string",
  "name": "string",
  "image": {
    "url": "https//stripe.com/images/img.png",
    "width": 32,
    "height": 32
  },
  "shortDescription": "string",
  "description": "string",
  "sku": [
    {
      "name": "Video Streaming Service",
      "description": "Video streaming service",
      "shortDescription": "Video streaming service",
      "sku": "3423-23423",
      "upc": "2323-234-343",
      "taxCategories": [
        {
          "name": "software",
          "confidence": 90,
          "isSelected": "true"
        },
        {
          "name": "hardware",
          "confidence": 80,
          "isSelected": "false"
        }
      ]
    }
  ],
  "inActive": true,
  "timestamp": "2010-10-11T21:44:22Z2",
  "mappingType": "autoMapped",
  "effectivePeriod": {
    "fromDate": "2010-10-11",
    "toDate": "2010-10-11"
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
  ]
}
```

<h3 id="add-product-to-the-catalog.-parameters">Parameters</h3>

|Name|In|Type|Required|Description3|
|---|---|---|---|---|
|catalogId|path|integer|true|Catalog Id. |
|body|body|[Product](#schemaproduct)|true|Product definition.|

#### Detailed descriptions

**catalogId**: Catalog Id. 

**body**: Product definition.

> Example responses

> 201 Response

```json
{
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
  "id": 0,
  "salePoint": "string",
  "masterId": "string",
  "name": "string",
  "image": {
    "url": "https//stripe.com/images/img.png",
    "width": 32,
    "height": 32
  },
  "shortDescription": "string",
  "description": "string",
  "inActive": true,
  "timestamp": "2010-10-11T21:44:22Z2",
  "mappingType": "autoMapped",
  "effectivePeriod": {
    "fromDate": "2010-10-11",
    "toDate": "2010-10-11"
  }
}
```

<h3 id="add-product-to-the-catalog.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|Product added successfully.|[ProductEntity](#schemaproductentity)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Unable to add product to catalog.|[Errors](#schemaerrors)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKeyAuth
</aside>

</div>

<div class="operation">

## GET/Return the product from the catalog.

> Code samples

```shell
# You can also use wget
curl -X GET /api/v1.2/saletax/products/{productId} \
  -H 'Accept: application/json' \
  -H 'apikey: API_KEY'

```

```java
URL obj = new URL("/api/v1.2/saletax/products/{productId}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

`GET /products/{productId}`

Returns the productby product id.

<h3 id="return-the-product-from-the-catalog.-parameters">Parameters</h3>

|Name|In|Type|Required|Description3|
|---|---|---|---|---|
|productId|path|integer|true|Product Id. |

#### Detailed descriptions

**productId**: Product Id. 

> Example responses

> 201 Response

```json
{
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
  "id": 0,
  "salePoint": "string",
  "masterId": "string",
  "name": "string",
  "image": {
    "url": "https//stripe.com/images/img.png",
    "width": 32,
    "height": 32
  },
  "shortDescription": "string",
  "description": "string",
  "inActive": true,
  "timestamp": "2010-10-11T21:44:22Z2",
  "mappingType": "autoMapped",
  "effectivePeriod": {
    "fromDate": "2010-10-11",
    "toDate": "2010-10-11"
  }
}
```

<h3 id="return-the-product-from-the-catalog.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|Returns the product|[ProductEntity](#schemaproductentity)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|The product not found.|[Errors](#schemaerrors)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKeyAuth
</aside>

</div>

<div class="operation">

## PATCH/Update the product.

> Code samples

```shell
# You can also use wget
curl -X PATCH /api/v1.2/saletax/products/{productId} \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'apikey: API_KEY'

```

```java
URL obj = new URL("/api/v1.2/saletax/products/{productId}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("PATCH");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

`PATCH /products/{productId}`

Make same changes in the product.

> Body parameter

```json
{
  "masterId": "string",
  "name": "string",
  "image": {
    "url": "https//stripe.com/images/img.png",
    "width": 32,
    "height": 32
  },
  "shortDescription": "string",
  "description": "string",
  "sku": [
    {
      "name": "Video Streaming Service",
      "description": "Video streaming service",
      "shortDescription": "Video streaming service",
      "sku": "3423-23423",
      "upc": "2323-234-343",
      "taxCategories": [
        {
          "name": "software",
          "confidence": 90,
          "isSelected": "true"
        },
        {
          "name": "hardware",
          "confidence": 80,
          "isSelected": "false"
        }
      ]
    }
  ],
  "inActive": true,
  "timestamp": "2010-10-11T21:44:22Z2",
  "mappingType": "autoMapped",
  "effectivePeriod": {
    "fromDate": "2010-10-11",
    "toDate": "2010-10-11"
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
  ]
}
```

<h3 id="update-the-product.-parameters">Parameters</h3>

|Name|In|Type|Required|Description3|
|---|---|---|---|---|
|productId|path|integer|true|Product id.|
|body|body|[Product](#schemaproduct)|true|Product definition.|

#### Detailed descriptions

**productId**: Product id.

**body**: Product definition.

> Example responses

> 204 Response

```json
{
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
  "id": 0,
  "salePoint": "string",
  "masterId": "string",
  "name": "string",
  "image": {
    "url": "https//stripe.com/images/img.png",
    "width": 32,
    "height": 32
  },
  "shortDescription": "string",
  "description": "string",
  "inActive": true,
  "timestamp": "2010-10-11T21:44:22Z2",
  "mappingType": "autoMapped",
  "effectivePeriod": {
    "fromDate": "2010-10-11",
    "toDate": "2010-10-11"
  }
}
```

<h3 id="update-the-product.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|204|[No Content](https://tools.ietf.org/html/rfc7231#section-6.3.5)|The product updated successfully.|[ProductEntity](#schemaproductentity)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Unable to updateproduct.|[Errors](#schemaerrors)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|The product not found.|[Errors](#schemaerrors)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKeyAuth
</aside>

</div>

</div>

<div class="total">
<h1 id="api-for-tax-calculator-logging">Logging</h1>

<div class="operation">

## GET/Return tax calculation call logs.

> Code samples

```shell
# You can also use wget
curl -X GET /api/v1.2/saletax/logs \
  -H 'Accept: application/json' \
  -H 'apikey: API_KEY'

```

```java
URL obj = new URL("/api/v1.2/saletax/logs");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

`GET /logs`

Returns tax calculation call logs 
for current sale point.

<h3 id="return-tax-calculation-call-logs.-parameters">Parameters</h3>

|Name|In|Type|Required|Description3|
|---|---|---|---|---|
|fromDate|query|[Date](#schemadate)|false|Specified period, from date. |
|toDate|query|[Date](#schemadate)|false|Specified period, to date.|

#### Detailed descriptions

**fromDate**: Specified period, from date. 

**toDate**: Specified period, to date.

> Example responses

> 200 Response

```json
{
  "logs": [
    {
      "request": "http://192.168.0.17/api/v1.2/nextPage?size=12",
      "response": "http://192.168.0.17/api/v1.2/nextPage?size=12",
      "date": "2010-10-11",
      "salePoint": "string"
    }
  ]
}
```

<h3 id="return-tax-calculation-call-logs.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Returns logs|[Logs](#schemalogs)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Unable to find logs by defined criterias.|[Errors](#schemaerrors)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKeyAuth
</aside>

</div>

</div>

<div class="total">
<h1 id="api-for-tax-calculator-transaction-journal">Transaction Journal</h1>

<div class="operation">

## GET/Get transactions.

> Code samples

```shell
# You can also use wget
curl -X GET /api/v1.2/saletax/transactions \
  -H 'Accept: application/json' \
  -H 'apikey: API_KEY'

```

```java
URL obj = new URL("/api/v1.2/saletax/transactions");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

`GET /transactions`

Returns transactions for current sale point.
Trnsactions can be selected by specified criteria.

<h3 id="get-transactions.-parameters">Parameters</h3>

|Name|In|Type|Required|Description3|
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
      "id": 0,
      "salePoint": "string",
      "masterId": 0,
      "type": "new",
      "status": "preview",
      "order": {
        "masterId": 0,
        "timestamp": "2010-10-11T21:44:22Z2",
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
          "total": 153.55,
          "subtotal": 148.35,
          "totalTax": 7.2,
          "taxDetails": [
            {
              "rate": {
                "id": 54,
                "description": "VAT",
                "name": "VAT",
                "taxLevel": "jurisdiction",
                "rules": [
                  "s56",
                  "s55"
                ],
                "percentage": 7
              },
              "amount": 7.2
            }
          ]
        },
        "id": 0,
        "salePoint": "string"
      }
    }
  ]
}
```

<h3 id="get-transactions.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Returns transactions|[Transactions](#schematransactions)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Unable to get transactions with defined criterias.|[Errors](#schemaerrors)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKeyAuth
</aside>

</div>

<div class="operation">

## GET/Get Transaction Summary.

> Code samples

```shell
# You can also use wget
curl -X GET /api/v1.2/saletax/transactions/summary \
  -H 'Accept: application/json' \
  -H 'apikey: API_KEY'

```

```java
URL obj = new URL("/api/v1.2/saletax/transactions/summary");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

`GET /transactions/summary`

Returns summary for transactions for current 
sale point which are selected by defined criterias.

<h3 id="get-transaction-summary.-parameters">Parameters</h3>

|Name|In|Type|Required|Description3|
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
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Returns transaction summary|[TransactionSummary](#schematransactionsummary)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Unable to get transaction summary.|[Errors](#schemaerrors)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKeyAuth
</aside>

</div>

<div class="operation">

## GET/Download journal in CVS.

> Code samples

```shell
# You can also use wget
curl -X GET /api/v1.2/saletax/transactions/cvs \
  -H 'Accept: application/json' \
  -H 'apikey: API_KEY'

```

```java
URL obj = new URL("/api/v1.2/saletax/transactions/cvs");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

`GET /transactions/cvs`

This endpoint is used by customers if they want to download transaction journal in CVS format.

<h3 id="download-journal-in-cvs.-parameters">Parameters</h3>

|Name|In|Type|Required|Description3|
|---|---|---|---|---|
|states|query|string|false|List of the states with comma delimiter.|
|fromDate|query|[DateTime](#schemadatetime)|false|Specified period of time. From date.|
|toDate|query|[DateTime](#schemadatetime)|false|Specified period of time. To date.|

#### Detailed descriptions

**states**: List of the states with comma delimiter.

**fromDate**: Specified period of time. From date.

**toDate**: Specified period of time. To date.

> Example responses

> 200 Response

```json
{}
```

<h3 id="download-journal-in-cvs.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Returns journal in CVS format.|[Object](#schemaobject)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Unable to create transaction journal.|[Errors](#schemaerrors)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKeyAuth
</aside>

</div>

</div>

<div class="total">
<h1 id="api-for-tax-calculator-transaction-management">Transaction Management</h1>

<div class="operation">

## POST/Consume transaction.

> Code samples

```shell
# You can also use wget
curl -X POST /api/v1.2/saletax/transactions \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'apikey: API_KEY'

```

```java
URL obj = new URL("/api/v1.2/saletax/transactions");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

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
    "timestamp": "2010-10-11T21:44:22Z2",
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
      "total": 153.55,
      "subtotal": 148.35,
      "totalTax": 7.2,
      "taxDetails": [
        {
          "rate": {
            "id": 54,
            "description": "VAT",
            "name": "VAT",
            "taxLevel": "jurisdiction",
            "rules": [
              "s56",
              "s55"
            ],
            "percentage": 7
          },
          "amount": 7.2
        }
      ]
    },
    "id": 0,
    "salePoint": "string"
  },
  "id": 0,
  "salePoint": "string"
}
```

<h3 id="consume-transaction.-parameters">Parameters</h3>

|Name|In|Type|Required|Description3|
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
    "timestamp": "2010-10-11T21:44:22Z2",
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
      "total": 153.55,
      "subtotal": 148.35,
      "totalTax": 7.2,
      "taxDetails": [
        {
          "rate": {
            "id": 54,
            "description": "VAT",
            "name": "VAT",
            "taxLevel": "jurisdiction",
            "rules": [
              "s56",
              "s55"
            ],
            "percentage": 7
          },
          "amount": 7.2
        }
      ]
    },
    "id": 0,
    "salePoint": "string"
  },
  "id": 0,
  "salePoint": "string"
}
```

<h3 id="consume-transaction.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|Returns transaction with total.|[Transaction](#schematransaction)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Unable to add transaction.|[Errors](#schemaerrors)|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|Unable to add transaction.
Transactions already registered.|[Errors](#schemaerrors)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKeyAuth
</aside>

</div>

<div class="operation">

## GET/Get transaction.

> Code samples

```shell
# You can also use wget
curl -X GET /api/v1.2/saletax/transactions/{transactionId} \
  -H 'Accept: application/json' \
  -H 'apikey: API_KEY'

```

```java
URL obj = new URL("/api/v1.2/saletax/transactions/{transactionId}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

`GET /transactions/{transactionId}`

Get transaction from the tax journal.

<h3 id="get-transaction.-parameters">Parameters</h3>

|Name|In|Type|Required|Description3|
|---|---|---|---|---|
|transactionId|path|string|true|Transaction id.|

#### Detailed descriptions

**transactionId**: Transaction id.

> Example responses

> 200 Response

```json
{
  "id": 0,
  "salePoint": "string",
  "masterId": 0,
  "type": "new",
  "status": "preview",
  "order": {
    "masterId": 0,
    "timestamp": "2010-10-11T21:44:22Z2",
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
      "total": 153.55,
      "subtotal": 148.35,
      "totalTax": 7.2,
      "taxDetails": [
        {
          "rate": {
            "id": 54,
            "description": "VAT",
            "name": "VAT",
            "taxLevel": "jurisdiction",
            "rules": [
              "s56",
              "s55"
            ],
            "percentage": 7
          },
          "amount": 7.2
        }
      ]
    },
    "id": 0,
    "salePoint": "string"
  }
}
```

<h3 id="get-transaction.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Returns a transaction.|[TransactionEntity](#schematransactionentity)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Transaction with specified id not found.|[Errors](#schemaerrors)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKeyAuth
</aside>

</div>

<div class="operation">

## DELETE/Delete transaction.

> Code samples

```shell
# You can also use wget
curl -X DELETE /api/v1.2/saletax/transactions/{transactionId} \
  -H 'Accept: application/json' \
  -H 'apikey: API_KEY'

```

```java
URL obj = new URL("/api/v1.2/saletax/transactions/{transactionId}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("DELETE");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

`DELETE /transactions/{transactionId}`

Delete transaction with specified id from
the tax journal.
Soft delete.

<h3 id="delete-transaction.-parameters">Parameters</h3>

|Name|In|Type|Required|Description3|
|---|---|---|---|---|
|transactionId|path|string|true|Transaction id.|

#### Detailed descriptions

**transactionId**: Transaction id.

> Example responses

> 200 Response

```json
{
  "id": 0,
  "salePoint": "string",
  "masterId": 0,
  "type": "new",
  "status": "preview",
  "order": {
    "masterId": 0,
    "timestamp": "2010-10-11T21:44:22Z2",
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
      "total": 153.55,
      "subtotal": 148.35,
      "totalTax": 7.2,
      "taxDetails": [
        {
          "rate": {
            "id": 54,
            "description": "VAT",
            "name": "VAT",
            "taxLevel": "jurisdiction",
            "rules": [
              "s56",
              "s55"
            ],
            "percentage": 7
          },
          "amount": 7.2
        }
      ]
    },
    "id": 0,
    "salePoint": "string"
  }
}
```

<h3 id="delete-transaction.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Transaction deleted successfully.|[TransactionEntity](#schematransactionentity)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Unable to delete transaction.
Transaction with specified id not found.|[Errors](#schemaerrors)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKeyAuth
</aside>

</div>

<div class="operation">

## PATCH/Update specified transaction.

> Code samples

```shell
# You can also use wget
curl -X PATCH /api/v1.2/saletax/transactions/{transactionId} \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'apikey: API_KEY'

```

```java
URL obj = new URL("/api/v1.2/saletax/transactions/{transactionId}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("PATCH");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

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
    "timestamp": "2010-10-11T21:44:22Z2",
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
      "total": 153.55,
      "subtotal": 148.35,
      "totalTax": 7.2,
      "taxDetails": [
        {
          "rate": {
            "id": 54,
            "description": "VAT",
            "name": "VAT",
            "taxLevel": "jurisdiction",
            "rules": [
              "s56",
              "s55"
            ],
            "percentage": 7
          },
          "amount": 7.2
        }
      ]
    },
    "id": 0,
    "salePoint": "string"
  },
  "id": 0,
  "salePoint": "string"
}
```

<h3 id="update-specified-transaction.-parameters">Parameters</h3>

|Name|In|Type|Required|Description3|
|---|---|---|---|---|
|transactionId|path|string|true|Specified transaction id.|
|body|body|[Transaction](#schematransaction)|true|none|

#### Detailed descriptions

**transactionId**: Specified transaction id.

> Example responses

> 204 Response

```json
{
  "id": 0,
  "salePoint": "string",
  "masterId": 0,
  "type": "new",
  "status": "preview",
  "order": {
    "masterId": 0,
    "timestamp": "2010-10-11T21:44:22Z2",
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
      "total": 153.55,
      "subtotal": 148.35,
      "totalTax": 7.2,
      "taxDetails": [
        {
          "rate": {
            "id": 54,
            "description": "VAT",
            "name": "VAT",
            "taxLevel": "jurisdiction",
            "rules": [
              "s56",
              "s55"
            ],
            "percentage": 7
          },
          "amount": 7.2
        }
      ]
    },
    "id": 0,
    "salePoint": "string"
  }
}
```

<h3 id="update-specified-transaction.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|204|[No Content](https://tools.ietf.org/html/rfc7231#section-6.3.5)|Transaction updated successfully.|[TransactionEntity](#schematransactionentity)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Unable to update transaction. 
Transaction with specified id not found.|[Errors](#schemaerrors)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKeyAuth
</aside>

</div>

</div>

# Schemas

<div class="operation">

<h2 id="tocS_Object">Object</h2>
<!-- backwards compatibility -->
<a id="schemaobject"></a>
<a id="schema_Object"></a>
<a id="tocSobject"></a>
<a id="tocsobject"></a>

```json
{}

```

Object

### Properties

*None*

</div>

<div class="operation">

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

</div>

<div class="operation">

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
|self|[Link](#schemalink)|false|none|Absolute URI.|
|prev|[Link](#schemalink)|false|none|Absolute URI.|
|next|[Link](#schemalink)|false|none|Absolute URI.|
|first|[Link](#schemalink)|false|none|Absolute URI.|
|last|[Link](#schemalink)|false|none|Absolute URI.|

</div>

<div class="operation">

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

</div>

<div class="operation">

<h2 id="tocS_Entity">Entity</h2>
<!-- backwards compatibility -->
<a id="schemaentity"></a>
<a id="schema_Entity"></a>
<a id="tocSentity"></a>
<a id="tocsentity"></a>

```json
{
  "id": 0,
  "salePoint": "string"
}

```

Entity

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|integer|false|none|Entity identifier.|
|salePoint|string|false|none|Sale point identifier, email.|

</div>

<div class="operation">

<h2 id="tocS_Error">Error</h2>
<!-- backwards compatibility -->
<a id="schemaerror"></a>
<a id="schema_Error"></a>
<a id="tocSerror"></a>
<a id="tocserror"></a>

```json
{
  "code": 1234,
  "traceId": "mm08-9033-9938-90gf",
  "uId": "54544",
  "timeStamp": "2010-10-11T21:44:22Z2",
  "message": "Illegal request parameter",
  "details": [
    "Please use correct company identifier",
    "and try again."
  ]
}

```

Error

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|code|integer|false|none|Error code.|
|uId|string|false|none|Unique identifier that helps to find an error.|
|correlationId|string|false|none|Unique identifier that helps to trace an error.|
|timeStamp|[DateTime](#schemadatetime)|false|none|Date-time in format [ISO-8601], YYYY-MM-DDThh:mm:ssTZD|
|message|string|false|none|Error message.|
|details|[string]|false|none|none|

</div>

<div class="operation">

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
      "traceId": "mm08-9033-9938-90gf",
      "uId": "54544",
      "timeStamp": "2010-10-11T21:44:22Z2",
      "message": "Illegal request parameter",
      "details": [
        "Please use correct company identifier",
        "and try again."
      ]
    }
  ]
}

```

Errors

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|errors|[[Error](#schemaerror)]|false|none|[Error datails which helps understand the error root.  <br>]|

</div>

<div class="operation">

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

</div>

<div class="operation">

<h2 id="tocS_Date">Date</h2>
<!-- backwards compatibility -->
<a id="schemadate"></a>
<a id="schema_Date"></a>
<a id="tocSdate"></a>
<a id="tocsdate"></a>

```json
"2010-10-11"

```

Date

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|Date|string(date)|false|none|Date in format [ISO-8601], YYYY-MM-DD|

</div>

<div class="operation">

<h2 id="tocS_DateTime">DateTime</h2>
<!-- backwards compatibility -->
<a id="schemadatetime"></a>
<a id="schema_DateTime"></a>
<a id="tocSdatetime"></a>
<a id="tocsdatetime"></a>

```json
"2010-10-11T21:44:22Z2"

```

Date-time

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|Date-time|string(date-time)|false|none|Date-time in format [ISO-8601], YYYY-MM-DDThh:mm:ssTZD|

</div>

<div class="operation">

<h2 id="tocS_Email">Email</h2>
<!-- backwards compatibility -->
<a id="schemaemail"></a>
<a id="schema_Email"></a>
<a id="tocSemail"></a>
<a id="tocsemail"></a>

```json
"code@vertex.com"

```

Email address

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|Email address|string|false|none|none|

</div>

<div class="operation">

<h2 id="tocS_Phone">Phone</h2>
<!-- backwards compatibility -->
<a id="schemaphone"></a>
<a id="schema_Phone"></a>
<a id="tocSphone"></a>
<a id="tocsphone"></a>

```json
"444-333-888"

```

Phone number

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|Phone number|string|false|none|none|

</div>

<div class="operation">

<h2 id="tocS_Period">Period</h2>
<!-- backwards compatibility -->
<a id="schemaperiod"></a>
<a id="schema_Period"></a>
<a id="tocSperiod"></a>
<a id="tocsperiod"></a>

```json
{
  "fromDate": "2010-10-11",
  "toDate": "2010-10-11"
}

```

Period

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|fromDate|[Date](#schemadate)|true|none|Date in format [ISO-8601], YYYY-MM-DD|
|toDate|[Date](#schemadate)|true|none|Date in format [ISO-8601], YYYY-MM-DD|

</div>

<div class="operation">

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
|link|[Link](#schemalink)|false|none|Absolute URI.|
|status|string|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|status|processing|
|status|error|
|status|done|

</div>

<div class="operation">

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

</div>

<div class="operation">

<h2 id="tocS_MessageEntity">MessageEntity</h2>
<!-- backwards compatibility -->
<a id="schemamessageentity"></a>
<a id="schema_MessageEntity"></a>
<a id="tocSmessageentity"></a>
<a id="tocsmessageentity"></a>

```json
{
  "id": 624,
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

Email message entity

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|Email message entity|any|false|none|none|

allOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[Entity](#schemaentity)|false|none|none|

and

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[Message](#schemamessage)|false|none|none|

</div>

<div class="operation">

<h2 id="tocS_Template">Template</h2>
<!-- backwards compatibility -->
<a id="schematemplate"></a>
<a id="schema_Template"></a>
<a id="tocStemplate"></a>
<a id="tocstemplate"></a>

```json
{
  "name": "email",
  "body": " Dear {name}, Your account is activated."
}

```

Template

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|name|string|true|none|Unique template name.|
|body|string|true|none|Template body which should be HTML <br>with data fileds placeholders.|

</div>

<div class="operation">

<h2 id="tocS_TemplateEntity">TemplateEntity</h2>
<!-- backwards compatibility -->
<a id="schematemplateentity"></a>
<a id="schema_TemplateEntity"></a>
<a id="tocStemplateentity"></a>
<a id="tocstemplateentity"></a>

```json
{
  "id": 624,
  "name": "email",
  "body": " Dear {name}, Your account is activated."
}

```

Template entity

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|Template entity|any|false|none|none|

allOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[Entity](#schemaentity)|false|none|none|

and

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[Template](#schematemplate)|false|none|none|

</div>

<div class="operation">

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
|templates|[[TemplateEntity](#schematemplateentity)]|false|none|none|

</div>

<div class="operation">

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

</div>

<div class="operation">

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

</div>

<div class="operation">

<h2 id="tocS_Location">Location</h2>
<!-- backwards compatibility -->
<a id="schemalocation"></a>
<a id="schema_Location"></a>
<a id="tocSlocation"></a>
<a id="tocslocation"></a>

```json
{
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
|type|[LocationType](#schemalocationtype)|true|none|An enumeration that represents available Location Types.<br>| value          | description                              |<br>|----------------|------------------------------------------|<br>| administrative | It means store regisgtration place       |<br>| phisical       | Store phosical prenets                   ||
|city|string|true|none|none|
|state|[State](#schemastate)|true|none|State in format [ISO 3166-2]|
|zip|string|true|none|none|
|zipExt|string|false|none|none|
|addressLine1|string|false|none|none|
|addressLine2|string|false|none|none|

</div>

<div class="operation">

<h2 id="tocS_LocationEntity">LocationEntity</h2>
<!-- backwards compatibility -->
<a id="schemalocationentity"></a>
<a id="schema_LocationEntity"></a>
<a id="tocSlocationentity"></a>
<a id="tocslocationentity"></a>

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

Location Entity

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|Location Entity|any|false|none|none|

allOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[Entity](#schemaentity)|false|none|none|

and

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[Location](#schemalocation)|false|none|none|

</div>

<div class="operation">

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
|locations|[[LocationEntity](#schemalocationentity)]|false|none|none|

</div>

<div class="operation">

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

Contact

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|Contact|[Entity](#schemaentity)|false|none|none|
|title|string|true|none|Contact title.|
|name|string|true|none|Contact name.|
|lastName|string|true|none|Contact last name.|

</div>

<div class="operation">

<h2 id="tocS_ContactEntity">ContactEntity</h2>
<!-- backwards compatibility -->
<a id="schemacontactentity"></a>
<a id="schema_ContactEntity"></a>
<a id="tocScontactentity"></a>
<a id="tocscontactentity"></a>

```json
{
  "id": 464,
  "title": "Mr",
  "name": "Oleksiy",
  "lastName": "Luchkovskiy"
}

```

Contact Entity

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|Contact Entity|any|false|none|none|

allOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[Entity](#schemaentity)|false|none|none|

and

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[Contact](#schemacontact)|false|none|none|

</div>

<div class="operation">

<h2 id="tocS_ContactInfo">ContactInfo</h2>
<!-- backwards compatibility -->
<a id="schemacontactinfo"></a>
<a id="schema_ContactInfo"></a>
<a id="tocScontactinfo"></a>
<a id="tocscontactinfo"></a>

```json
{
  "location": {
    "type": "administrative",
    "city": "KNG OF PRUSSA",
    "state": "PA",
    "zip": "19406",
    "zipExt": "1101",
    "addressLine1": "875 MANCILL MILL RD"
  },
  "emails": [
    "code@vertex.com"
  ],
  "phones": [
    "444-333-888"
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

</div>

<div class="operation">

<h2 id="tocS_ContactInfoEntity">ContactInfoEntity</h2>
<!-- backwards compatibility -->
<a id="schemacontactinfoentity"></a>
<a id="schema_ContactInfoEntity"></a>
<a id="tocScontactinfoentity"></a>
<a id="tocscontactinfoentity"></a>

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
    "code@vertex.com"
  ],
  "phones": [
    "444-333-888"
  ],
  "id": 464,
  "title": "Mr",
  "name": "Oleksiy",
  "lastName": "Luchkovskiy"
}

```

Contact information Entity

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|Contact information Entity|[ContactEntity](#schemacontactentity)|false|none|none|
|location|[LocationEntity](#schemalocationentity)|false|none|none|
|emails|[[Email](#schemaemail)]|false|none|none|
|phones|[[Phone](#schemaphone)]|false|none|none|

</div>

<div class="operation">

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

</div>

<div class="operation">

<h2 id="tocS_Account">Account</h2>
<!-- backwards compatibility -->
<a id="schemaaccount"></a>
<a id="schema_Account"></a>
<a id="tocSaccount"></a>
<a id="tocsaccount"></a>

```json
{
  "name": "Cofe shop",
  "email": "shop@vertex.com",
  "password": "password"
}

```

Account

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|name|string|true|none|Account name.|
|email|[Email](#schemaemail)|true|none|none|
|password|string(password)|true|none|Account password.|

</div>

<div class="operation">

<h2 id="tocS_AccountEntity">AccountEntity</h2>
<!-- backwards compatibility -->
<a id="schemaaccountentity"></a>
<a id="schema_AccountEntity"></a>
<a id="tocSaccountentity"></a>
<a id="tocsaccountentity"></a>

```json
{
  "id": 656,
  "name": "Cofe shop",
  "email": "shop@vertex.com"
}

```

Account Entity

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|Account Entity|[Entity](#schemaentity)|false|none|none|
|name|string|true|none|Account name.|
|email|[Email](#schemaemail)|true|none|none|

</div>

<div class="operation">

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
    "email": "shop@vertex.com"
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
|account|[AccountEntity](#schemaaccountentity)|false|none|none|
|businessInfo|[BusinessInfoEntity](#schemabusinessinfoentity)|false|none|Account business information. <br>This information includes business name and tax identifier.|
|locations|[Locations](#schemalocations)|false|none|none|

</div>

<div class="operation">

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

</div>

<div class="operation">

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

</div>

<div class="operation">

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

</div>

<div class="operation">

<h2 id="tocS_BusinessInfo">BusinessInfo</h2>
<!-- backwards compatibility -->
<a id="schemabusinessinfo"></a>
<a id="schema_BusinessInfo"></a>
<a id="tocSbusinessinfo"></a>
<a id="tocsbusinessinfo"></a>

```json
{
  "businessName": "Cofe shop LTD",
  "fedTaxId": "2321-2323-2132"
}

```

Business information

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|businessName|string|true|none|Business name.|
|fedTaxId|string|true|none|Federal tax identifier.|

</div>

<div class="operation">

<h2 id="tocS_BusinessInfoEntity">BusinessInfoEntity</h2>
<!-- backwards compatibility -->
<a id="schemabusinessinfoentity"></a>
<a id="schema_BusinessInfoEntity"></a>
<a id="tocSbusinessinfoentity"></a>
<a id="tocsbusinessinfoentity"></a>

```json
{
  "id": 234,
  "businessName": "Cofe shop LTD",
  "fedTaxId": "2321-2323-2132"
}

```

Business information entity

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|Business information entity|any|false|none|Account business information. <br>This information includes business name and tax identifier.|

allOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[Entity](#schemaentity)|false|none|none|

and

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[BusinessInfo](#schemabusinessinfo)|false|none|Account business information. <br>This information includes business name and tax identifier.|

</div>

<div class="operation">

<h2 id="tocS_TaxCategory">TaxCategory</h2>
<!-- backwards compatibility -->
<a id="schemataxcategory"></a>
<a id="schema_TaxCategory"></a>
<a id="tocStaxcategory"></a>
<a id="tocstaxcategory"></a>

```json
{
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
|name|string|false|none|Tax category name.|
|confidence|integer|false|none|Prediction categorization confidence.|
|isManualy|boolean|false|none|Flag indicates that the tax category is defined manually.|
|isSelected|boolean|false|none|Flag indicates that the tax category is selected.|

</div>

<div class="operation">

<h2 id="tocS_TaxCategoryEntity">TaxCategoryEntity</h2>
<!-- backwards compatibility -->
<a id="schemataxcategoryentity"></a>
<a id="schema_TaxCategoryEntity"></a>
<a id="tocStaxcategoryentity"></a>
<a id="tocstaxcategoryentity"></a>

```json
{
  "id": 556,
  "name": "sugar contains",
  "confidence": 90,
  "isManually": "true",
  "isSelected": "true"
}

```

Tax Category Entity

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|Tax Category Entity|any|false|none|none|

allOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[Entity](#schemaentity)|false|none|none|

and

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[TaxCategory](#schemataxcategory)|false|none|none|

</div>

<div class="operation">

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
|Tax Category collection|[[TaxCategoryEntity](#schemataxcategoryentity)]|false|none|none|

</div>

<div class="operation">

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
  "platformId": 0
}

```

Product Catalog

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|name|string|false|none|Product name.|
|merchantId|integer|false|none|Sale point/merchant identifier.|
|platformId|integer|false|none|Platform identifier.|

</div>

<div class="operation">

<h2 id="tocS_ProductCatalogEntity">ProductCatalogEntity</h2>
<!-- backwards compatibility -->
<a id="schemaproductcatalogentity"></a>
<a id="schema_ProductCatalogEntity"></a>
<a id="tocSproductcatalogentity"></a>
<a id="tocsproductcatalogentity"></a>

```json
{
  "id": 0,
  "salePoint": "string",
  "name": "string",
  "merchantId": 0,
  "platformId": 0
}

```

Product Catalog entity

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|Product Catalog entity|any|false|none|none|

allOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[Entity](#schemaentity)|false|none|none|

and

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[ProductCatalog](#schemaproductcatalog)|false|none|none|

</div>

<div class="operation">

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
      "id": 0,
      "salePoint": "string",
      "name": "string",
      "merchantId": 0,
      "platformId": 0
    }
  ]
}

```

Product Catalog сollection

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|catalogs|[[ProductCatalogEntity](#schemaproductcatalogentity)]|false|none|none|

</div>

<div class="operation">

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

</div>

<div class="operation">

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

</div>

<div class="operation">

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

</div>

<div class="operation">

<h2 id="tocS_Image">Image</h2>
<!-- backwards compatibility -->
<a id="schemaimage"></a>
<a id="schema_Image"></a>
<a id="tocSimage"></a>
<a id="tocsimage"></a>

```json
{
  "url": "https//stripe.com/images/img.png",
  "width": 32,
  "height": 32
}

```

Image

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|url|[Link](#schemalink)|true|none|Absolute URI.|
|width|integer|true|none|Image width.|
|height|integer|false|none|Image height.|

</div>

<div class="operation">

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
  "image": {
    "url": "https//stripe.com/images/img.png",
    "width": 32,
    "height": 32
  },
  "shortDescription": "string",
  "description": "string",
  "sku": [
    {
      "name": "Video Streaming Service",
      "description": "Video streaming service",
      "shortDescription": "Video streaming service",
      "sku": "3423-23423",
      "upc": "2323-234-343",
      "taxCategories": [
        {
          "name": "software",
          "confidence": 90,
          "isSelected": "true"
        },
        {
          "name": "hardware",
          "confidence": 80,
          "isSelected": "false"
        }
      ]
    }
  ],
  "inActive": true,
  "timestamp": "2010-10-11T21:44:22Z2",
  "mappingType": "autoMapped",
  "effectivePeriod": {
    "fromDate": "2010-10-11",
    "toDate": "2010-10-11"
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
  ]
}

```

Product

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|masterId|string|false|none|Product master id.<br>Product identifier in exernal system.|
|name|string|true|none|Product name.|
|image|[Image](#schemaimage)|false|none|none|
|shortDescription|string|false|none|Short product description.|
|description|string|false|none|Product description.|
|sku|[[StockUnit](#schemastockunit)]|false|none|none|
|inActive|boolean|false|none|The flag indicates that the product<br>is available now.|
|timestamp|[DateTime](#schemadatetime)|false|none|Date-time in format [ISO-8601], YYYY-MM-DDThh:mm:ssTZD|
|mappingType|[MappingType](#schemamappingtype)|false|none|An enumeration that represents Product Mapping Types<br>| value      | description                                    |<br>|------------|------------------------------------------------|<br>| autoMapped | For this product mapping has been done by ML   |<br>| new        | This product has been added                    |<br>| udated     | This product has been updated/changed          |<br>| remapped   | This product categoy has been remapped         ||
|effectivePeriod|[Period](#schemaperiod)|false|none|none|
|taxCategories|[TaxCategories](#schemataxcategories)|false|none|none|
|categories|[Categories](#schemacategories)|false|none|none|

</div>

<div class="operation">

<h2 id="tocS_ProductEntity">ProductEntity</h2>
<!-- backwards compatibility -->
<a id="schemaproductentity"></a>
<a id="schema_ProductEntity"></a>
<a id="tocSproductentity"></a>
<a id="tocsproductentity"></a>

```json
{
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
  "id": 0,
  "salePoint": "string",
  "masterId": "string",
  "name": "string",
  "image": {
    "url": "https//stripe.com/images/img.png",
    "width": 32,
    "height": 32
  },
  "shortDescription": "string",
  "description": "string",
  "inActive": true,
  "timestamp": "2010-10-11T21:44:22Z2",
  "mappingType": "autoMapped",
  "effectivePeriod": {
    "fromDate": "2010-10-11",
    "toDate": "2010-10-11"
  }
}

```

ProductEntity

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|sku|[[StockUnitEntity](#schemastockunitentity)]|false|none|none|
|taxCategories|[TaxCategories](#schemataxcategories)|false|none|none|
|categories|[Categories](#schemacategories)|false|none|none|

allOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[Entity](#schemaentity)|false|none|none|

and

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[Product](#schemaproduct)|false|none|none|

</div>

<div class="operation">

<h2 id="tocS_StockUnit">StockUnit</h2>
<!-- backwards compatibility -->
<a id="schemastockunit"></a>
<a id="schema_StockUnit"></a>
<a id="tocSstockunit"></a>
<a id="tocsstockunit"></a>

```json
{
  "name": "Video Streaming Service",
  "description": "Video streaming service",
  "shortDescription": "Video streaming service",
  "sku": "3423-23423",
  "upc": "2323-234-343",
  "taxCategories": [
    {
      "name": "software",
      "confidence": 90,
      "isSelected": "true"
    },
    {
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
|sku|string|false|none|Stock Keeping Unit.|
|name|string|false|none|Name.|
|shortDescription|string|false|none|Short description.|
|description|string|false|none|Description.|
|upc|string|false|none|UPC code.|
|taxCategories|[TaxCategories](#schemataxcategories)|false|none|none|

</div>

<div class="operation">

<h2 id="tocS_StockUnitEntity">StockUnitEntity</h2>
<!-- backwards compatibility -->
<a id="schemastockunitentity"></a>
<a id="schema_StockUnitEntity"></a>
<a id="tocSstockunitentity"></a>
<a id="tocsstockunitentity"></a>

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

Stock Keeping Unit Entity

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|Stock Keeping Unit Entity|any|false|none|none|

allOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[Entity](#schemaentity)|false|none|none|

and

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[StockUnit](#schemastockunit)|false|none|none|

</div>

<div class="operation">

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
      "id": 0,
      "salePoint": "string",
      "masterId": "string",
      "name": "string",
      "image": {
        "url": "https//stripe.com/images/img.png",
        "width": 32,
        "height": 32
      },
      "shortDescription": "string",
      "description": "string",
      "inActive": true,
      "timestamp": "2010-10-11T21:44:22Z2",
      "mappingType": "autoMapped",
      "effectivePeriod": {
        "fromDate": "2010-10-11",
        "toDate": "2010-10-11"
      }
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
|products|[[ProductEntity](#schemaproductentity)]|false|none|none|

</div>

<div class="operation">

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

</div>

<div class="operation">

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

</div>

<div class="operation">

<h2 id="tocS_Tax">Tax</h2>
<!-- backwards compatibility -->
<a id="schematax"></a>
<a id="schema_Tax"></a>
<a id="tocStax"></a>
<a id="tocstax"></a>

```json
{
  "rate": {
    "id": 54,
    "description": "VAT",
    "name": "VAT",
    "taxLevel": "jurisdiction",
    "rules": [
      "s56",
      "s55"
    ],
    "percentage": 7
  },
  "amount": "string"
}

```

Tax

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|rate|[TaxRate](#schemataxrate)|false|none|none|
|amount|[Amount](#schemaamount)|false|none|Amont in format is [ISO 20022]. <br>The decimal separator is a dot. NNNN.NN|

</div>

<div class="operation">

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

</div>

<div class="operation">

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

</div>

<div class="operation">

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
    "timestamp": "2010-10-11T21:44:22Z2",
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
      "total": 153.55,
      "subtotal": 148.35,
      "totalTax": 7.2,
      "taxDetails": [
        {
          "rate": {
            "id": 54,
            "description": "VAT",
            "name": "VAT",
            "taxLevel": "jurisdiction",
            "rules": [
              "s56",
              "s55"
            ],
            "percentage": 7
          },
          "amount": 7.2
        }
      ]
    },
    "id": 0,
    "salePoint": "string"
  },
  "id": 0,
  "salePoint": "string"
}

```

Transaction

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|Transaction|[Entity](#schemaentity)|false|none|none|
|masterId|integer|false|none|Transaction unique identifier in master system.|
|type|[TransactionType](#schematransactiontype)|true|none|Enumeration that represnts supportable Transaction Types <br> | value    | description                                    |<br> |----------|------------------------------------------------|<br> | new      | Default transaction type                       |<br> | complete | Complete                                       |<br> | return   | Return                                         |<br> | cancel   | Transaction  cancelled                         |<br> | adjust   | Transaction is used for price adjustment       ||
|status|[TransactionStatus](#schematransactionstatus)|true|none|Enumeration that represnts available Transaction Statuses <br>| value   | description                                   |<br>|---------|-----------------------------------------------|<br>| preview | Precalculation                                |<br>| order   | Order                                         ||
|order|[Order](#schemaorder)|false|none|none|

</div>

<div class="operation">

<h2 id="tocS_TransactionEntity">TransactionEntity</h2>
<!-- backwards compatibility -->
<a id="schematransactionentity"></a>
<a id="schema_TransactionEntity"></a>
<a id="tocStransactionentity"></a>
<a id="tocstransactionentity"></a>

```json
{
  "id": 0,
  "salePoint": "string",
  "masterId": 0,
  "type": "new",
  "status": "preview",
  "order": {
    "masterId": 0,
    "timestamp": "2010-10-11T21:44:22Z2",
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
      "total": 153.55,
      "subtotal": 148.35,
      "totalTax": 7.2,
      "taxDetails": [
        {
          "rate": {
            "id": 54,
            "description": "VAT",
            "name": "VAT",
            "taxLevel": "jurisdiction",
            "rules": [
              "s56",
              "s55"
            ],
            "percentage": 7
          },
          "amount": 7.2
        }
      ]
    },
    "id": 0,
    "salePoint": "string"
  }
}

```

Transaction entity

### Properties

allOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[Entity](#schemaentity)|false|none|none|

and

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[Transaction](#schematransaction)|false|none|none|

</div>

<div class="operation">

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
      "id": 0,
      "salePoint": "string",
      "masterId": 0,
      "type": "new",
      "status": "preview",
      "order": {
        "masterId": 0,
        "timestamp": "2010-10-11T21:44:22Z2",
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
          "total": 153.55,
          "subtotal": 148.35,
          "totalTax": 7.2,
          "taxDetails": [
            {
              "rate": {
                "id": 54,
                "description": "VAT",
                "name": "VAT",
                "taxLevel": "jurisdiction",
                "rules": [
                  "s56",
                  "s55"
                ],
                "percentage": 7
              },
              "amount": 7.2
            }
          ]
        },
        "id": 0,
        "salePoint": "string"
      }
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
|transactions|[[TransactionEntity](#schematransactionentity)]|false|none|none|

</div>

<div class="operation">

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

</div>

<div class="operation">

<h2 id="tocS_OrderTotal">OrderTotal</h2>
<!-- backwards compatibility -->
<a id="schemaordertotal"></a>
<a id="schema_OrderTotal"></a>
<a id="tocSordertotal"></a>
<a id="tocsordertotal"></a>

```json
{
  "total": 153.55,
  "subtotal": 148.35,
  "totalTax": 7.2,
  "taxDetails": [
    {
      "rate": {
        "id": 54,
        "description": "VAT",
        "name": "VAT",
        "taxLevel": "jurisdiction",
        "rules": [
          "s56",
          "s55"
        ],
        "percentage": 7
      },
      "amount": 7.2
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

</div>

<div class="operation">

<h2 id="tocS_Order">Order</h2>
<!-- backwards compatibility -->
<a id="schemaorder"></a>
<a id="schema_Order"></a>
<a id="tocSorder"></a>
<a id="tocsorder"></a>

```json
{
  "masterId": 0,
  "timestamp": "2010-10-11T21:44:22Z2",
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
    "total": 153.55,
    "subtotal": 148.35,
    "totalTax": 7.2,
    "taxDetails": [
      {
        "rate": {
          "id": 54,
          "description": "VAT",
          "name": "VAT",
          "taxLevel": "jurisdiction",
          "rules": [
            "s56",
            "s55"
          ],
          "percentage": 7
        },
        "amount": 7.2
      }
    ]
  },
  "id": 0,
  "salePoint": "string"
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

</div>

<div class="operation">

<h2 id="tocS_OrderEntity">OrderEntity</h2>
<!-- backwards compatibility -->
<a id="schemaorderentity"></a>
<a id="schema_OrderEntity"></a>
<a id="tocSorderentity"></a>
<a id="tocsorderentity"></a>

```json
{
  "id": 0,
  "salePoint": "string",
  "masterId": 0,
  "timestamp": "2010-10-11T21:44:22Z2",
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
    "total": 153.55,
    "subtotal": 148.35,
    "totalTax": 7.2,
    "taxDetails": [
      {
        "rate": {
          "id": 54,
          "description": "VAT",
          "name": "VAT",
          "taxLevel": "jurisdiction",
          "rules": [
            "s56",
            "s55"
          ],
          "percentage": 7
        },
        "amount": 7.2
      }
    ]
  }
}

```

Order Entity

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|Order Entity|any|false|none|none|

allOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[Entity](#schemaentity)|false|none|none|

and

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[Order](#schemaorder)|false|none|none|

</div>

<div class="operation">

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

</div>

<div class="operation">

<h2 id="tocS_Log">Log</h2>
<!-- backwards compatibility -->
<a id="schemalog"></a>
<a id="schema_Log"></a>
<a id="tocSlog"></a>
<a id="tocslog"></a>

```json
{
  "request": "http://192.168.0.17/api/v1.2/nextPage?size=12",
  "response": "http://192.168.0.17/api/v1.2/nextPage?size=12",
  "date": "2010-10-11",
  "salePoint": "string"
}

```

Log

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|request|[Link](#schemalink)|false|none|Absolute URI.|
|response|[Link](#schemalink)|false|none|Absolute URI.|
|date|[Date](#schemadate)|false|none|Date in format [ISO-8601], YYYY-MM-DD|
|salePoint|string|false|none|Sale point identifier, email.|

</div>

<div class="operation">

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
      "request": "http://192.168.0.17/api/v1.2/nextPage?size=12",
      "response": "http://192.168.0.17/api/v1.2/nextPage?size=12",
      "date": "2010-10-11",
      "salePoint": "string"
    }
  ]
}

```

Log collection

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|logs|[[Log](#schemalog)]|false|none|[Tax calculation log.<br>]|

</div>

