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

<div class="total">
<h1 id="api-for-tax-calculator">API for Tax Calculator v0.0.2 alfa, Dec 2019</h1>
<div class="endpoint-data">
<div class="description">
Vertex API for Tax Calculator.

Base URLs:

* <a href="/api/v1.2/saletax">/api/v1.2/saletax</a>

Web: <a href="http://www.vertex.com">API Support</a> 
License: <a href="https://www.apache.org/licenses/LICENSE-2.0.html">Apache 2.0</a>

</div>
<div class="code-examples">
Scroll down for code samples, example requests and responses. Select a language for code samples from the tabs above or the mobile navigation menu.
</div>
</div>

# Authentication
<div class="endpoint-data">
<div class="description">

- HTTP Authentication, scheme: bearer 

* API Key (apiKeyAuth)
    - Parameter Name: **apikey**, in: header. API key to authorize requests.

</div>
</div>

</div>

<div class="total">
<h1 id="api-for-tax-calculator-notification-template">Notification template</h1>

<div class="endpoint-data">
<div class="description">

## GET/Return registered templates.

`GET /templates`

Returns registered templates for current sale channel.

<h3 id="return-registered-templates.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|OK|Returns collectin of the templates for 
current sale channel.|[Templates](#tocs_templates)|
|404|Not Found|Unable to find any template.|[Errors](#tocs_errors)|

</div>
<div class="code-examples">

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

</div>

</div>

<div class="endpoint-data">
<div class="description">

## POST/Register new template.

`POST /templates`

The endpoint is used to register new template
for current sale channel.

<h3 id="register-new-template.-parameters">Parameters</h3>

|Name|In|Type|Required|Description3|
|---|---|---|---|---|
|body|body|[Template](#schematemplate)|true|none|

<h3 id="register-new-template.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|Created|Template is added successfully.|[TemplateEntity](#tocs_templateentity)|
|400|Bad Request|Unable to register template.|[Errors](#tocs_errors)|
|404|Not Found|Unable to register template. 
Template with the same name is already registered.|[Errors](#tocs_errors)|

</div>
<div class="code-examples">

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

> Body parameter

```json
{
  "name": "email",
  "body": " Dear {name}, Your account is activated."
}
```

> Example responses

> 201 Response

```json
{
  "id": 624,
  "name": "email",
  "body": " Dear {name}, Your account is activated."
}
```

</div>

</div>

<div class="endpoint-data">
<div class="description">

## GET/Get template.

`GET /templates/{templateId}`

Returns template with defined id. 

<h3 id="get-template.-parameters">Parameters</h3>

|Name|In|Type|Required|Description3|
|---|---|---|---|---|
|templateId|path|string|true|Template id.|

#### Detailed descriptions

**templateId**: Template id.

<h3 id="get-template.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|OK|Template|[TemplateEntity](#tocs_templateentity)|
|404|Not Found|Unable to find template.|[Errors](#tocs_errors)|

</div>
<div class="code-examples">

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

> Example responses

> 200 Response

```json
{
  "id": 624,
  "name": "email",
  "body": " Dear {name}, Your account is activated."
}
```

</div>

</div>

<div class="endpoint-data">
<div class="description">

## PATCH/Update template.

`PATCH /templates/{templateId}`

Makes changes in the defined template.

<h3 id="update-template.-parameters">Parameters</h3>

|Name|In|Type|Required|Description3|
|---|---|---|---|---|
|templateId|path|string|true|Template id.|
|body|body|[Template](#schematemplate)|true|none|

#### Detailed descriptions

**templateId**: Template id.

<h3 id="update-template.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|Created|Template is updated successfully.|[TemplateEntity](#tocs_templateentity)|
|404|Not Found|Unable to update template.|[Errors](#tocs_errors)|

</div>
<div class="code-examples">

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

> Body parameter

```json
{
  "name": "email",
  "body": " Dear {name}, Your account is activated."
}
```

> Example responses

> 201 Response

```json
{
  "id": 624,
  "name": "email",
  "body": " Dear {name}, Your account is activated."
}
```

</div>

</div>

<div class="endpoint-data">
<div class="description">

## DELETE/Delete template.

`DELETE /templates/{templateId}`

Deletes the defined template. 

<h3 id="delete-template.-parameters">Parameters</h3>

|Name|In|Type|Required|Description3|
|---|---|---|---|---|
|templateId|path|string|true|Template id.|

#### Detailed descriptions

**templateId**: Template id.

<h3 id="delete-template.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|OK|Template is deleted successfully.|[TemplateEntity](#tocs_templateentity)|
|404|Not Found|Template not found.|[Errors](#tocs_errors)|

</div>
<div class="code-examples">

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

> Example responses

> 200 Response

```json
{
  "id": 624,
  "name": "email",
  "body": " Dear {name}, Your account is activated."
}
```

</div>

</div>

<div class="endpoint-data">
<div class="description">

## POST/Send notification.

`POST /templates/{templateId}/send`

The endpoint is used to notify current 
sale channel by e-mail. 

<h3 id="send-notification.-parameters">Parameters</h3>

|Name|In|Type|Required|Description3|
|---|---|---|---|---|
|templateId|path|string|true|Template id.|
|body|body|[Message](#schemamessage)|true|none|

#### Detailed descriptions

**templateId**: Template id.

<h3 id="send-notification.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|Created|Notification sent successfully.
Returns fulfilled message.|[MessageEntity](#tocs_messageentity)|
|400|Bad Request|Unable to send notification.|[Errors](#tocs_errors)|

</div>
<div class="code-examples">

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

</div>

</div>

</div>

<div class="total">
<h1 id="api-for-tax-calculator-account-management">Account Management</h1>

<div class="endpoint-data">
<div class="description">

## POST/Create new account.

`POST /accounts`

The endpoint is used to create new account.
* The endpoint can be invoked by platform
in this case platform API key should be 
passed as token.
* Either the endpoint can be invoked without 
token. In this case sale channel
creates its own account.

<h3 id="create-new-account.-parameters">Parameters</h3>

|Name|In|Type|Required|Description3|
|---|---|---|---|---|
|platform|header|string|false|Platform API key.|
|body|body|[Account](#schemaaccount)|true|none|

#### Detailed descriptions

**platform**: Platform API key.

<h3 id="create-new-account.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|Created|Account created successfully.|[AccountEntity](#tocs_accountentity)|
|400|Bad Request|Unable to create account.|[Errors](#tocs_errors)|
|409|Conflict|Account already exists.|[Errors](#tocs_errors)|

</div>
<div class="code-examples">

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

> Body parameter

```json
{
  "name": "Cofe shop",
  "email": "shop@vertex.com",
  "password": "password"
}
```

> Example responses

> 201 Response

```json
{
  "id": 656,
  "name": "Cofe shop",
  "email": "shop@vertex.com"
}
```

</div>

</div>

<div class="endpoint-data">
<div class="description">

## GET/Get account information.

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

<h3 id="get-account-information.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|OK|Returns account information.|[AccountInfo](#tocs_accountinfo)|
|404|Not Found|Unable to find an account.|[Errors](#tocs_errors)|

</div>
<div class="code-examples">

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

</div>

</div>

<div class="endpoint-data">
<div class="description">

## PATCH/Update an account.

`PATCH /accounts/{email}`

Updates account password.

<h3 id="update-an-account.-parameters">Parameters</h3>

|Name|In|Type|Required|Description3|
|---|---|---|---|---|
|body|body|[Account](#schemaaccount)|true|none|
|email|path|string|true|Account identifier.|

#### Detailed descriptions

**email**: Account identifier.

<h3 id="update-an-account.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|204|No Content|Account updated successfully.|[AccountEntity](#tocs_accountentity)|
|400|Bad Request|Unable to update account.|[Errors](#tocs_errors)|
|404|Not Found|Account not found.|[Errors](#tocs_errors)|

</div>
<div class="code-examples">

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

> Body parameter

```json
{
  "name": "Cofe shop",
  "email": "shop@vertex.com",
  "password": "password"
}
```

> Example responses

> 204 Response

```json
{
  "id": 656,
  "name": "Cofe shop",
  "email": "shop@vertex.com"
}
```

</div>

</div>

<div class="endpoint-data">
<div class="description">

## DELETE/Make an account inactive.

`DELETE /accounts/{email}`

"Make defined account inactive.

<h3 id="make-an-account-inactive.-parameters">Parameters</h3>

|Name|In|Type|Required|Description3|
|---|---|---|---|---|
|email|path|string|true|Account identifier.|

#### Detailed descriptions

**email**: Account identifier.

<h3 id="make-an-account-inactive.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|OK|Account updated successfully.|[AccountEntity](#tocs_accountentity)|
|404|Not Found|Unable to make an account inactive.|[Errors](#tocs_errors)|

</div>
<div class="code-examples">

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

> Example responses

> 200 Response

```json
{
  "id": 656,
  "name": "Cofe shop",
  "email": "shop@vertex.com"
}
```

</div>

</div>

<div class="endpoint-data">
<div class="description">

## POST/Get a link for resetting account password.

`POST /accounts/{email}/resetPassword`

The endpoint is used to generate temporary link which 
can be used for resetting account password.

<h3 id="get-a-link-for-resetting-account-password.-parameters">Parameters</h3>

|Name|In|Type|Required|Description3|
|---|---|---|---|---|
|email|path|string|true|Account identifier.|

#### Detailed descriptions

**email**: Account identifier.

<h3 id="get-a-link-for-resetting-account-password.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|Created|Link created successfully.|[Link](#tocs_link)|
|400|Bad Request|Unable to create a link.|[Errors](#tocs_errors)|
|409|Conflict|Unble to find account.|[Errors](#tocs_errors)|

</div>
<div class="code-examples">

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

> Example responses

> 201 Response

```json
"http://192.168.0.17/api/v1.2/nextPage?size=12"
```

</div>

</div>

</div>

<div class="total">
<h1 id="api-for-tax-calculator-token-management">Token Management</h1>

<div class="endpoint-data">
<div class="description">

## GET/Get active tokens

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

<h3 id="get-active-tokens-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|OK|Returns token.|[Tokens](#tocs_tokens)|
|404|Not Found|Unable to return tokens.|[Errors](#tocs_errors)|

</div>
<div class="code-examples">

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

</div>

</div>

<div class="endpoint-data">
<div class="description">

## POST/Generate token.

`POST /tokens`

Creates a new token for API call.

<h3 id="generate-token.-parameters">Parameters</h3>

|Name|In|Type|Required|Description3|
|---|---|---|---|---|
|body|body|[TokenType](#schematokentype)|true|none|

<h3 id="generate-token.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|Created|Returns a token.|[Token](#tocs_token)|
|400|Bad Request|Unable to create token.|[Errors](#tocs_errors)|

</div>
<div class="code-examples">

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

> Body parameter

```json
{
  "type": "public"
}
```

> Example responses

> 201 Response

```json
{
  "type": "sandbox",
  "token": "1324325543234324",
  "created": "2019-08-23T12:23:56TZ2"
}
```

</div>

</div>

<div class="endpoint-data">
<div class="description">

## DELETE/Revoke the token.

`DELETE /tokens/{token}`

The method allows to deactivate the token.
But a sale channel should have as minimum one 
token for production environment and one for sandbox.
They can't be revoked.

<h3 id="revoke-the-token.-parameters">Parameters</h3>

|Name|In|Type|Required|Description3|
|---|---|---|---|---|
|token|path|string|true|none|

<h3 id="revoke-the-token.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|OK|The token revoken successfully.|[Token](#tocs_token)|
|404|Not Found|Unable to revoke token.|[Errors](#tocs_errors)|
|409|Conflict|Unable to revoke the last token.|[Errors](#tocs_errors)|

</div>
<div class="code-examples">

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

> Example responses

> 200 Response

```json
{
  "type": "sandbox",
  "token": "1324325543234324",
  "created": "2019-08-23T12:23:56TZ2"
}
```

</div>

</div>

</div>

<div class="total">
<h1 id="api-for-tax-calculator-contact-information">Contact Information</h1>

<div class="endpoint-data">
<div class="description">

## GET/Get contact information.

`GET /contacts/{contactId}`

The endpoint returns contact information.

<h3 id="get-contact-information.-parameters">Parameters</h3>

|Name|In|Type|Required|Description3|
|---|---|---|---|---|
|contactId|path|integer|true|none|

<h3 id="get-contact-information.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|OK|Returns contact information.|[ContactInfoEntity](#tocs_contactinfoentity)|
|404|Not Found|Unable to add contact information.|[Errors](#tocs_errors)|

</div>
<div class="code-examples">

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

</div>

</div>

<div class="endpoint-data">
<div class="description">

## POST/Add contact information.

`POST /contacts`

The endpoint is used to add contact information.

<h3 id="add-contact-information.-parameters">Parameters</h3>

|Name|In|Type|Required|Description3|
|---|---|---|---|---|
|body|body|[ContactInfo](#schemacontactinfo)|true|none|

<h3 id="add-contact-information.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|Created|Contact information added successfully.|[ContactInfoEntity](#tocs_contactinfoentity)|
|400|Bad Request|Unable to add contact information.|[Errors](#tocs_errors)|

</div>
<div class="code-examples">

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

</div>

</div>

<div class="endpoint-data">
<div class="description">

## PATCH/Update contact information.

`PATCH /contacts/{contactId}`

The endpoint is used to update contact information.

<h3 id="update-contact-information.-parameters">Parameters</h3>

|Name|In|Type|Required|Description3|
|---|---|---|---|---|
|contactId|path|string|true|none|
|body|body|[ContactInfo](#schemacontactinfo)|true|none|

<h3 id="update-contact-information.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|204|No Content|Contact information updated successfully|[ContactInfoEntity](#tocs_contactinfoentity)|
|400|Bad Request|Unable to update contact information.|[Errors](#tocs_errors)|
|404|Not Found|Unable to update contact information, 
account or contact information not found.|[Errors](#tocs_errors)|

</div>
<div class="code-examples">

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

</div>

</div>

</div>

<div class="total">
<h1 id="api-for-tax-calculator-location">Location</h1>

<div class="endpoint-data">
<div class="description">

## GET/Get account locations.

`GET /locations`

The endpoint is used to fetch locations 
for current sale point.

<h3 id="get-account-locations.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|OK|Returns location collection|[Locations](#tocs_locations)|
|404|Not Found|Locations not found.|[Errors](#tocs_errors)|

</div>
<div class="code-examples">

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

</div>

</div>

<div class="endpoint-data">
<div class="description">

## POST/Add location.

`POST /locations`

The endpoint is used to add location, place
where the sale poit is operated.

Any number of phisical locations and 
only one adminisrative location are possible.

<h3 id="add-location.-parameters">Parameters</h3>

|Name|In|Type|Required|Description3|
|---|---|---|---|---|
|body|body|[Location](#schemalocation)|true|none|

<h3 id="add-location.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|Created|Location added successfully|[LocationEntity](#tocs_locationentity)|
|404|Not Found|Unable to add location. 
Location is already added.|[Errors](#tocs_errors)|

</div>
<div class="code-examples">

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

</div>

</div>

<div class="endpoint-data">
<div class="description">

## GET/Get location.

`GET /locations/{locationId}`

Returns location with defined id.

<h3 id="get-location.-parameters">Parameters</h3>

|Name|In|Type|Required|Description3|
|---|---|---|---|---|
|locationId|path|string|true|Location Id.|

#### Detailed descriptions

**locationId**: Location Id.

<h3 id="get-location.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|OK|Returns location|[LocationEntity](#tocs_locationentity)|
|404|Not Found|Location not found.|[Errors](#tocs_errors)|

</div>
<div class="code-examples">

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

</div>

</div>

<div class="endpoint-data">
<div class="description">

## PATCH/Update location.

`PATCH /locations/{locationId}`

The endpoint is used to update location.

<h3 id="update-location.-parameters">Parameters</h3>

|Name|In|Type|Required|Description3|
|---|---|---|---|---|
|locationId|path|integer|true|Location Id. |
|body|body|[Location](#schemalocation)|true|none|

#### Detailed descriptions

**locationId**: Location Id. 

<h3 id="update-location.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|204|No Content|Location is updated successfully.|[LocationEntity](#tocs_locationentity)|
|400|Bad Request|Unable to update location.|[Errors](#tocs_errors)|
|404|Not Found|Unable to update location. 
Location not found.|[Errors](#tocs_errors)|

</div>
<div class="code-examples">

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

</div>

</div>

<div class="endpoint-data">
<div class="description">

## DELETE/Delete location.

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

<h3 id="delete-location.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|OK|Location deleted successfully.|[LocationEntity](#tocs_locationentity)|
|404|Not Found|Location not found.|[Errors](#tocs_errors)|

</div>
<div class="code-examples">

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

</div>

</div>

<div class="endpoint-data">
<div class="description">

## POST/Standardize a location.

`POST /locations/standardize`

Validates location and return result in standard format.
It helps to keep addresses in unified format and 
find zip extension.

<h3 id="standardize-a-location.-parameters">Parameters</h3>

|Name|In|Type|Required|Description3|
|---|---|---|---|---|
|body|body|[Location](#schemalocation)|false|none|

<h3 id="standardize-a-location.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|OK|Returns location is standard format.|[Location](#tocs_location)|
|400|Bad Request|Unable to validate defined location.|[Errors](#tocs_errors)|
|404|Not Found|Unable to validate defined location.
Location has invalid format.|[Errors](#tocs_errors)|

</div>
<div class="code-examples">

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

</div>

</div>

</div>

<div class="total">
<h1 id="api-for-tax-calculator-business-info">Business Info</h1>

<div class="endpoint-data">
<div class="description">

## GET/Get business information.

`GET /businessInfos`

Returns business information 
for current sales point.

<h3 id="get-business-information.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|OK|Returns business information.|[BusinessInfoEntity](#tocs_businessinfoentity)|
|404|Not Found|Business information not found.|[Errors](#tocs_errors)|

</div>
<div class="code-examples">

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

> Example responses

> 200 Response

```json
{
  "id": 234,
  "businessName": "Cofe shop LTD",
  "fedTaxId": "2321-2323-2132"
}
```

</div>

</div>

<div class="endpoint-data">
<div class="description">

## POST/Add business information.

`POST /businessInfos`

The endpoint is used to add business information.

<h3 id="add-business-information.-parameters">Parameters</h3>

|Name|In|Type|Required|Description3|
|---|---|---|---|---|
|body|body|[BusinessInfo](#schemabusinessinfo)|true|none|

<h3 id="add-business-information.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|Created|Business information added successfully.|[BusinessInfo](#tocs_businessinfo)|
|400|Bad Request|Unable to add business information.|[Errors](#tocs_errors)|
|404|Not Found|Unable to add business information.
Business infomatin aleready added.|[Errors](#tocs_errors)|

</div>
<div class="code-examples">

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

> Body parameter

```json
{
  "businessName": "Cofe shop LTD",
  "fedTaxId": "2321-2323-2132"
}
```

> Example responses

> 201 Response

```json
{
  "businessName": "Cofe shop LTD",
  "fedTaxId": "2321-2323-2132"
}
```

</div>

</div>

<div class="endpoint-data">
<div class="description">

## PATCH/Update business information.

`PATCH /businessInfos/{businessInfoId}`

Update business information.

<h3 id="update-business-information.-parameters">Parameters</h3>

|Name|In|Type|Required|Description3|
|---|---|---|---|---|
|body|body|[BusinessInfo](#schemabusinessinfo)|true|none|
|businessInfoId|path|string|true|Business Info Id. |

#### Detailed descriptions

**businessInfoId**: Business Info Id. 

<h3 id="update-business-information.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|204|No Content|Business information updated sucessfully.|[BusinessInfoEntity](#tocs_businessinfoentity)|
|400|Bad Request|Unable to update business information.|[Errors](#tocs_errors)|
|404|Not Found|Unable to update business information.
Business information not found.|[Errors](#tocs_errors)|

</div>
<div class="code-examples">

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

> Body parameter

```json
{
  "businessName": "Cofe shop LTD",
  "fedTaxId": "2321-2323-2132"
}
```

> Example responses

> 204 Response

```json
{
  "id": 234,
  "businessName": "Cofe shop LTD",
  "fedTaxId": "2321-2323-2132"
}
```

</div>

</div>

</div>

<div class="total">
<h1 id="api-for-tax-calculator-product-catalog">Product Catalog</h1>

<div class="endpoint-data">
<div class="description">

## GET/Return available product catalogs.

`GET /catalogs`

Returns product catalogs for current sale point.
SBT has only one catalog.
Partner is able to get set of the catalogs. 

<h3 id="return-available-product-catalogs.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|OK|Returns product catalog.|[ProductCatalogs](#tocs_productcatalogs)|
|404|Not Found|Unable to find product calalog.|[Errors](#tocs_errors)|

</div>
<div class="code-examples">

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

</div>

</div>

<div class="endpoint-data">
<div class="description">

## POST/Upload and validate product catalog. 
Return a process status.

`POST /catalogs`

Uploads and validtes product catalog. 
Processing product catalog is an asynchronous process.
Endpoint returns a link for checking process status.

<h3 id="upload-and-validate-product-catalog.-
return-a-process-status.
-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|Created|Returns a link which is used for checking upload 
processing status.|[Link](#tocs_link)|
|400|Bad Request|Unable to upload catalog.|[Errors](#tocs_errors)|
|404|Not Found|Catalog has invalid structure.|[Errors](#tocs_errors)|

</div>
<div class="code-examples">

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

> Example responses

> 201 Response

```json
"http://192.168.0.17/api/v1.2/nextPage?size=12"
```

</div>

</div>

<div class="endpoint-data">
<div class="description">

## GET/Return product catalog

`GET /catalogs/{catalogId}`

Returns product catalog with defined id. 

<h3 id="return-product-catalog-parameters">Parameters</h3>

|Name|In|Type|Required|Description3|
|---|---|---|---|---|
|catalogId|path|integer|true|Catalog id.|

#### Detailed descriptions

**catalogId**: Catalog id.

<h3 id="return-product-catalog-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|OK|Return product catalog|[ProductCatalogEntity](#tocs_productcatalogentity)|
|404|Not Found|Unable to find product catalog.|[Errors](#tocs_errors)|

</div>
<div class="code-examples">

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

</div>

</div>

<div class="endpoint-data">
<div class="description">

## POST/Remap tax categories.

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

<h3 id="remap-tax-categories.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|Created|Returns a link which for checking process status.|[Link](#tocs_link)|
|404|Not Found|Unable to find catalog.|[Errors](#tocs_errors)|

</div>
<div class="code-examples">

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

> Example responses

> 201 Response

```json
"http://192.168.0.17/api/v1.2/nextPage?size=12"
```

</div>

</div>

<div class="endpoint-data">
<div class="description">

## GET/Get product catalog processing status

`GET /catalogs/{processId}/status`

Processing product catalog is an asynchronous process.
The endpoint returns product catalog processing status.

<h3 id="get-product-catalog-processing-status-parameters">Parameters</h3>

|Name|In|Type|Required|Description3|
|---|---|---|---|---|
|processId|path|integer|true|Process id. |

#### Detailed descriptions

**processId**: Process id. 

<h3 id="get-product-catalog-processing-status-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|OK|Returns processing status.|[ProcessingStatus](#tocs_processingstatus)|
|404|Not Found|Unable to return processing status.
Invalid process identifier.|[Errors](#tocs_errors)|

</div>
<div class="code-examples">

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

> Example responses

> 200 Response

```json
{
  "id": 0,
  "link": "http://192.168.0.17/api/v1.2/nextPage?size=12",
  "status": "processing"
}
```

</div>

</div>

<div class="endpoint-data">
<div class="description">

## POST/Accept product catalog categorization.

`POST /catalogs/{catalogId}/accept`

Accept product catalog categorization. 

<h3 id="accept-product-catalog-categorization.-parameters">Parameters</h3>

|Name|In|Type|Required|Description3|
|---|---|---|---|---|
|catalogId|path|integer|true|Catalog Id. |

#### Detailed descriptions

**catalogId**: Catalog Id. 

<h3 id="accept-product-catalog-categorization.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|Created|Customer is agree with tax categorization.|[Object](#tocs_object)|
|404|Not Found|Invalid identifier, catalog not found
or processing is not finished.|[Errors](#tocs_errors)|

</div>
<div class="code-examples">

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

> Example responses

> 201 Response

```json
{}
```

</div>

</div>

<div class="endpoint-data">
<div class="description">

## POST/Download product catalog.

`POST /catalogs/{catalogId}/load`

Allows to download product catalogue for 
new/updated products only.

<h3 id="download-product-catalog.-parameters">Parameters</h3>

|Name|In|Type|Required|Description3|
|---|---|---|---|---|
|catalogId|path|integer|true|Catalog Id.|

#### Detailed descriptions

**catalogId**: Catalog Id.

<h3 id="download-product-catalog.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|Created|Returns a product catalog.|[ProductCatalog](#tocs_productcatalog)|
|400|Bad Request|Unable to return catalogue.|[Errors](#tocs_errors)|
|404|Not Found|Invalid product catalog identifier.|[Errors](#tocs_errors)|

</div>
<div class="code-examples">

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

> Example responses

> 201 Response

```json
{
  "name": "string",
  "merchantId": 0,
  "platformId": 0
}
```

</div>

</div>

</div>

<div class="total">
<h1 id="api-for-tax-calculator-product">Product</h1>

<div class="endpoint-data">
<div class="description">

## GET/Lookup products from the defined catalog.

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

<h3 id="lookup-products-from-the-defined-catalog.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|Created|Returns collection of the products.|[Products](#tocs_products)|
|404|Not Found|Product catalog not found.|[Errors](#tocs_errors)|

</div>
<div class="code-examples">

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

</div>

</div>

<div class="endpoint-data">
<div class="description">

## POST/Add product to the catalog.

`POST /catalogs/{catalogId}/products`

Add product to the catalog. 

<h3 id="add-product-to-the-catalog.-parameters">Parameters</h3>

|Name|In|Type|Required|Description3|
|---|---|---|---|---|
|catalogId|path|integer|true|Catalog Id. |
|body|body|[Product](#schemaproduct)|true|Product definition.|

#### Detailed descriptions

**catalogId**: Catalog Id. 

**body**: Product definition.

<h3 id="add-product-to-the-catalog.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|Created|Product added successfully.|[ProductEntity](#tocs_productentity)|
|404|Not Found|Unable to add product to catalog.|[Errors](#tocs_errors)|

</div>
<div class="code-examples">

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

</div>

</div>

<div class="endpoint-data">
<div class="description">

## GET/Return the product from the catalog.

`GET /products/{productId}`

Returns the productby product id.

<h3 id="return-the-product-from-the-catalog.-parameters">Parameters</h3>

|Name|In|Type|Required|Description3|
|---|---|---|---|---|
|productId|path|integer|true|Product Id. |

#### Detailed descriptions

**productId**: Product Id. 

<h3 id="return-the-product-from-the-catalog.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|Created|Returns the product|[ProductEntity](#tocs_productentity)|
|404|Not Found|The product not found.|[Errors](#tocs_errors)|

</div>
<div class="code-examples">

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

</div>

</div>

<div class="endpoint-data">
<div class="description">

## PATCH/Update the product.

`PATCH /products/{productId}`

Make same changes in the product.

<h3 id="update-the-product.-parameters">Parameters</h3>

|Name|In|Type|Required|Description3|
|---|---|---|---|---|
|productId|path|integer|true|Product id.|
|body|body|[Product](#schemaproduct)|true|Product definition.|

#### Detailed descriptions

**productId**: Product id.

**body**: Product definition.

<h3 id="update-the-product.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|204|No Content|The product updated successfully.|[ProductEntity](#tocs_productentity)|
|400|Bad Request|Unable to updateproduct.|[Errors](#tocs_errors)|
|404|Not Found|The product not found.|[Errors](#tocs_errors)|

</div>
<div class="code-examples">

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

</div>

</div>

</div>

<div class="total">
<h1 id="api-for-tax-calculator-logging">Logging</h1>

<div class="endpoint-data">
<div class="description">

## GET/Return tax calculation call logs.

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

<h3 id="return-tax-calculation-call-logs.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|OK|Returns logs|[Logs](#tocs_logs)|
|404|Not Found|Unable to find logs by defined criterias.|[Errors](#tocs_errors)|

</div>
<div class="code-examples">

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

</div>

</div>

</div>

<div class="total">
<h1 id="api-for-tax-calculator-transaction-journal">Transaction Journal</h1>

<div class="endpoint-data">
<div class="description">

## GET/Get transactions.

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

<h3 id="get-transactions.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|OK|Returns transactions|[Transactions](#tocs_transactions)|
|404|Not Found|Unable to get transactions with defined criterias.|[Errors](#tocs_errors)|

</div>
<div class="code-examples">

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

</div>

</div>

<div class="endpoint-data">
<div class="description">

## GET/Get Transaction Summary.

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

<h3 id="get-transaction-summary.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|OK|Returns transaction summary|[TransactionSummary](#tocs_transactionsummary)|
|404|Not Found|Unable to get transaction summary.|[Errors](#tocs_errors)|

</div>
<div class="code-examples">

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

> Example responses

> 200 Response

```json
{
  "countTrans": 343,
  "totalSales": 6565.9,
  "totalTax": 34.3
}
```

</div>

</div>

<div class="endpoint-data">
<div class="description">

## GET/Download journal in CVS.

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

<h3 id="download-journal-in-cvs.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|OK|Returns journal in CVS format.|[Object](#tocs_object)|
|404|Not Found|Unable to create transaction journal.|[Errors](#tocs_errors)|

</div>
<div class="code-examples">

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

> Example responses

> 200 Response

```json
{}
```

</div>

</div>

</div>

<div class="total">
<h1 id="api-for-tax-calculator-transaction-management">Transaction Management</h1>

<div class="endpoint-data">
<div class="description">

## POST/Consume transaction.

`POST /transactions`

Consume merchant transaction. 
If transaction is sale and compeleted it would 
be registered in the tax journal. 
Returns transaction with total.
Total includes collection taxes.

<h3 id="consume-transaction.-parameters">Parameters</h3>

|Name|In|Type|Required|Description3|
|---|---|---|---|---|
|body|body|[Transaction](#schematransaction)|true|none|

<h3 id="consume-transaction.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|Created|Returns transaction with total.|[Transaction](#tocs_transaction)|
|400|Bad Request|Unable to add transaction.|[Errors](#tocs_errors)|
|409|Conflict|Unable to add transaction.
Transactions already registered.|[Errors](#tocs_errors)|

</div>
<div class="code-examples">

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

</div>

</div>

<div class="endpoint-data">
<div class="description">

## GET/Get transaction.

`GET /transactions/{transactionId}`

Get transaction from the tax journal.

<h3 id="get-transaction.-parameters">Parameters</h3>

|Name|In|Type|Required|Description3|
|---|---|---|---|---|
|transactionId|path|string|true|Transaction id.|

#### Detailed descriptions

**transactionId**: Transaction id.

<h3 id="get-transaction.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|OK|Returns a transaction.|[TransactionEntity](#tocs_transactionentity)|
|404|Not Found|Transaction with specified id not found.|[Errors](#tocs_errors)|

</div>
<div class="code-examples">

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

</div>

</div>

<div class="endpoint-data">
<div class="description">

## DELETE/Delete transaction.

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

<h3 id="delete-transaction.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|OK|Transaction deleted successfully.|[TransactionEntity](#tocs_transactionentity)|
|404|Not Found|Unable to delete transaction.
Transaction with specified id not found.|[Errors](#tocs_errors)|

</div>
<div class="code-examples">

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

</div>

</div>

<div class="endpoint-data">
<div class="description">

## PATCH/Update specified transaction.

`PATCH /transactions/{transactionId}`

Update specified transaction.
Safe operation. 

<h3 id="update-specified-transaction.-parameters">Parameters</h3>

|Name|In|Type|Required|Description3|
|---|---|---|---|---|
|transactionId|path|string|true|Specified transaction id.|
|body|body|[Transaction](#schematransaction)|true|none|

#### Detailed descriptions

**transactionId**: Specified transaction id.

<h3 id="update-specified-transaction.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|204|No Content|Transaction updated successfully.|[TransactionEntity](#tocs_transactionentity)|
|404|Not Found|Unable to update transaction. 
Transaction with specified id not found.|[Errors](#tocs_errors)|

</div>
<div class="code-examples">

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

</div>

</div>

</div>

# Schemas

<div class="schema-data">
<div class="description">

<h2 id="tocS_Object">Object</h2>
<!-- backwards compatibility -->
<a id="schemaobject"></a>
<a id="schema_Object"></a>
<a id="tocSobject"></a>
<a id="tocsobject"></a>

Object

### Properties

*None*

</div>
<div class="code-examples">

```json
{}

```
</div>
</div>

<div class="schema-data">
<div class="description">

<h2 id="tocS_Link">Link</h2>
<!-- backwards compatibility -->
<a id="schemalink"></a>
<a id="schema_Link"></a>
<a id="tocSlink"></a>
<a id="tocslink"></a>

Link

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|href|string|false|none|none|

</div>
<div class="code-examples">

```json
"http://192.168.0.17/api/v1.2/nextPage?size=12"

```
</div>
</div>

<div class="schema-data">
<div class="description">

<h2 id="tocS_Pagination">Pagination</h2>
<!-- backwards compatibility -->
<a id="schemapagination"></a>
<a id="schema_Pagination"></a>
<a id="tocSpagination"></a>
<a id="tocspagination"></a>

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
<div class="code-examples">

```json
{
  "self": "http://vertex.com/api/v1.2/logs?page=30&size=10",
  "prev": "http://vertex.com/api/v1.2/logs?page=29&size=10",
  "next": "http://vertex.com/api/v1.2/logs?page=31&size=10",
  "first": "http://vertex.com/api/v1.2/logs?page=1&size=10",
  "last": "http://vertex.com/api/v1.2/logs?page=80&size=10"
}

```
</div>
</div>

<div class="schema-data">
<div class="description">

<h2 id="tocS_FetchInfo">FetchInfo</h2>
<!-- backwards compatibility -->
<a id="schemafetchinfo"></a>
<a id="schema_FetchInfo"></a>
<a id="tocSfetchinfo"></a>
<a id="tocsfetchinfo"></a>

Fetch info

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|size|integer|false|none|Chunk size.|
|totalElelments|integer|false|none|Total elements count.|
|totalPages|integer|false|none|Total page count.|
|page|integer|false|none|Current page.|

</div>
<div class="code-examples">

```json
{
  "totalElements": 5000,
  "size": 10,
  "totslPages": 500,
  "page": 3
}

```
</div>
</div>

<div class="schema-data">
<div class="description">

<h2 id="tocS_Entity">Entity</h2>
<!-- backwards compatibility -->
<a id="schemaentity"></a>
<a id="schema_Entity"></a>
<a id="tocSentity"></a>
<a id="tocsentity"></a>

Entity

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|integer|false|none|Entity identifier.|
|salePoint|string|false|none|Sale point identifier, email.|

</div>
<div class="code-examples">

```json
{
  "id": 0,
  "salePoint": "string"
}

```
</div>
</div>

<div class="schema-data">
<div class="description">

<h2 id="tocS_Error">Error</h2>
<!-- backwards compatibility -->
<a id="schemaerror"></a>
<a id="schema_Error"></a>
<a id="tocSerror"></a>
<a id="tocserror"></a>

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
<div class="code-examples">

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
</div>
</div>

<div class="schema-data">
<div class="description">

<h2 id="tocS_Errors">Errors</h2>
<!-- backwards compatibility -->
<a id="schemaerrors"></a>
<a id="schema_Errors"></a>
<a id="tocSerrors"></a>
<a id="tocserrors"></a>

Errors

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|errors|[[Error](#schemaerror)]|false|none|[Error datails which helps understand the error root.  <br>]|

</div>
<div class="code-examples">

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
</div>
</div>

<div class="schema-data">
<div class="description">

<h2 id="tocS_Amount">Amount</h2>
<!-- backwards compatibility -->
<a id="schemaamount"></a>
<a id="schema_Amount"></a>
<a id="tocSamount"></a>
<a id="tocsamount"></a>

Amount

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|Amount|string|false|none|Amont in format is [ISO 20022]. <br>The decimal separator is a dot. NNNN.NN|

</div>
<div class="code-examples">

```json
"string"

```
</div>
</div>

<div class="schema-data">
<div class="description">

<h2 id="tocS_Date">Date</h2>
<!-- backwards compatibility -->
<a id="schemadate"></a>
<a id="schema_Date"></a>
<a id="tocSdate"></a>
<a id="tocsdate"></a>

Date

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|Date|string(date)|false|none|Date in format [ISO-8601], YYYY-MM-DD|

</div>
<div class="code-examples">

```json
"2010-10-11"

```
</div>
</div>

<div class="schema-data">
<div class="description">

<h2 id="tocS_DateTime">DateTime</h2>
<!-- backwards compatibility -->
<a id="schemadatetime"></a>
<a id="schema_DateTime"></a>
<a id="tocSdatetime"></a>
<a id="tocsdatetime"></a>

Date-time

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|Date-time|string(date-time)|false|none|Date-time in format [ISO-8601], YYYY-MM-DDThh:mm:ssTZD|

</div>
<div class="code-examples">

```json
"2010-10-11T21:44:22Z2"

```
</div>
</div>

<div class="schema-data">
<div class="description">

<h2 id="tocS_Email">Email</h2>
<!-- backwards compatibility -->
<a id="schemaemail"></a>
<a id="schema_Email"></a>
<a id="tocSemail"></a>
<a id="tocsemail"></a>

Email address

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|Email address|string|false|none|none|

</div>
<div class="code-examples">

```json
"code@vertex.com"

```
</div>
</div>

<div class="schema-data">
<div class="description">

<h2 id="tocS_Phone">Phone</h2>
<!-- backwards compatibility -->
<a id="schemaphone"></a>
<a id="schema_Phone"></a>
<a id="tocSphone"></a>
<a id="tocsphone"></a>

Phone number

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|Phone number|string|false|none|none|

</div>
<div class="code-examples">

```json
"444-333-888"

```
</div>
</div>

<div class="schema-data">
<div class="description">

<h2 id="tocS_Period">Period</h2>
<!-- backwards compatibility -->
<a id="schemaperiod"></a>
<a id="schema_Period"></a>
<a id="tocSperiod"></a>
<a id="tocsperiod"></a>

Period

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|fromDate|[Date](#schemadate)|true|none|Date in format [ISO-8601], YYYY-MM-DD|
|toDate|[Date](#schemadate)|true|none|Date in format [ISO-8601], YYYY-MM-DD|

</div>
<div class="code-examples">

```json
{
  "fromDate": "2010-10-11",
  "toDate": "2010-10-11"
}

```
</div>
</div>

<div class="schema-data">
<div class="description">

<h2 id="tocS_ProcessingStatus">ProcessingStatus</h2>
<!-- backwards compatibility -->
<a id="schemaprocessingstatus"></a>
<a id="schema_ProcessingStatus"></a>
<a id="tocSprocessingstatus"></a>
<a id="tocsprocessingstatus"></a>

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
<div class="code-examples">

```json
{
  "id": 0,
  "link": "http://192.168.0.17/api/v1.2/nextPage?size=12",
  "status": "processing"
}

```
</div>
</div>

<div class="schema-data">
<div class="description">

<h2 id="tocS_Message">Message</h2>
<!-- backwards compatibility -->
<a id="schemamessage"></a>
<a id="schema_Message"></a>
<a id="tocSmessage"></a>
<a id="tocsmessage"></a>

Email message

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|email|string|true|none|User email address.|
|subject|string|true|none|Message subject.|
|parameters|[[Parameter](#schemaparameter)]|false|none|[Definition of the notification parameter. <br>Notification service uses parameters to fulfil <br>defined template by values.<br>]|

</div>
<div class="code-examples">

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
</div>
</div>

<div class="schema-data">
<div class="description">

<h2 id="tocS_MessageEntity">MessageEntity</h2>
<!-- backwards compatibility -->
<a id="schemamessageentity"></a>
<a id="schema_MessageEntity"></a>
<a id="tocSmessageentity"></a>
<a id="tocsmessageentity"></a>

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
<div class="code-examples">

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
</div>
</div>

<div class="schema-data">
<div class="description">

<h2 id="tocS_Template">Template</h2>
<!-- backwards compatibility -->
<a id="schematemplate"></a>
<a id="schema_Template"></a>
<a id="tocStemplate"></a>
<a id="tocstemplate"></a>

Template

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|name|string|true|none|Unique template name.|
|body|string|true|none|Template body which should be HTML <br>with data fileds placeholders.|

</div>
<div class="code-examples">

```json
{
  "name": "email",
  "body": " Dear {name}, Your account is activated."
}

```
</div>
</div>

<div class="schema-data">
<div class="description">

<h2 id="tocS_TemplateEntity">TemplateEntity</h2>
<!-- backwards compatibility -->
<a id="schematemplateentity"></a>
<a id="schema_TemplateEntity"></a>
<a id="tocStemplateentity"></a>
<a id="tocstemplateentity"></a>

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
<div class="code-examples">

```json
{
  "id": 624,
  "name": "email",
  "body": " Dear {name}, Your account is activated."
}

```
</div>
</div>

<div class="schema-data">
<div class="description">

<h2 id="tocS_Templates">Templates</h2>
<!-- backwards compatibility -->
<a id="schematemplates"></a>
<a id="schema_Templates"></a>
<a id="tocStemplates"></a>
<a id="tocstemplates"></a>

Template collection

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|templates|[[TemplateEntity](#schematemplateentity)]|false|none|none|

</div>
<div class="code-examples">

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
</div>
</div>

<div class="schema-data">
<div class="description">

<h2 id="tocS_Parameter">Parameter</h2>
<!-- backwards compatibility -->
<a id="schemaparameter"></a>
<a id="schema_Parameter"></a>
<a id="tocSparameter"></a>
<a id="tocsparameter"></a>

Notification Parameter

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|name|string|false|none|Parameter name.|
|value|string|false|none|Parameter value.|

</div>
<div class="code-examples">

```json
{
  "name": "string",
  "value": "string"
}

```
</div>
</div>

<div class="schema-data">
<div class="description">

<h2 id="tocS_LocationType">LocationType</h2>
<!-- backwards compatibility -->
<a id="schemalocationtype"></a>
<a id="schema_LocationType"></a>
<a id="tocSlocationtype"></a>
<a id="tocslocationtype"></a>

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
<div class="code-examples">

```json
"administrative"

```
</div>
</div>

<div class="schema-data">
<div class="description">

<h2 id="tocS_Location">Location</h2>
<!-- backwards compatibility -->
<a id="schemalocation"></a>
<a id="schema_Location"></a>
<a id="tocSlocation"></a>
<a id="tocslocation"></a>

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
<div class="code-examples">

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
</div>
</div>

<div class="schema-data">
<div class="description">

<h2 id="tocS_LocationEntity">LocationEntity</h2>
<!-- backwards compatibility -->
<a id="schemalocationentity"></a>
<a id="schema_LocationEntity"></a>
<a id="tocSlocationentity"></a>
<a id="tocslocationentity"></a>

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
<div class="code-examples">

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
</div>
</div>

<div class="schema-data">
<div class="description">

<h2 id="tocS_Locations">Locations</h2>
<!-- backwards compatibility -->
<a id="schemalocations"></a>
<a id="schema_Locations"></a>
<a id="tocSlocations"></a>
<a id="tocslocations"></a>

Location collection

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|locations|[[LocationEntity](#schemalocationentity)]|false|none|none|

</div>
<div class="code-examples">

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
</div>
</div>

<div class="schema-data">
<div class="description">

<h2 id="tocS_Contact">Contact</h2>
<!-- backwards compatibility -->
<a id="schemacontact"></a>
<a id="schema_Contact"></a>
<a id="tocScontact"></a>
<a id="tocscontact"></a>

Contact

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|Contact|[Entity](#schemaentity)|false|none|none|
|title|string|true|none|Contact title.|
|name|string|true|none|Contact name.|
|lastName|string|true|none|Contact last name.|

</div>
<div class="code-examples">

```json
{
  "id": 464,
  "title": "Mr",
  "name": "Oleksiy",
  "lastName": "Luchkovskiy"
}

```
</div>
</div>

<div class="schema-data">
<div class="description">

<h2 id="tocS_ContactEntity">ContactEntity</h2>
<!-- backwards compatibility -->
<a id="schemacontactentity"></a>
<a id="schema_ContactEntity"></a>
<a id="tocScontactentity"></a>
<a id="tocscontactentity"></a>

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
<div class="code-examples">

```json
{
  "id": 464,
  "title": "Mr",
  "name": "Oleksiy",
  "lastName": "Luchkovskiy"
}

```
</div>
</div>

<div class="schema-data">
<div class="description">

<h2 id="tocS_ContactInfo">ContactInfo</h2>
<!-- backwards compatibility -->
<a id="schemacontactinfo"></a>
<a id="schema_ContactInfo"></a>
<a id="tocScontactinfo"></a>
<a id="tocscontactinfo"></a>

Contact information

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|Contact information|[Contact](#schemacontact)|false|none|none|
|location|[Location](#schemalocation)|false|none|none|
|emails|[[Email](#schemaemail)]|false|none|none|
|phones|[[Phone](#schemaphone)]|false|none|none|

</div>
<div class="code-examples">

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
</div>
</div>

<div class="schema-data">
<div class="description">

<h2 id="tocS_ContactInfoEntity">ContactInfoEntity</h2>
<!-- backwards compatibility -->
<a id="schemacontactinfoentity"></a>
<a id="schema_ContactInfoEntity"></a>
<a id="tocScontactinfoentity"></a>
<a id="tocscontactinfoentity"></a>

Contact information Entity

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|Contact information Entity|[ContactEntity](#schemacontactentity)|false|none|none|
|location|[LocationEntity](#schemalocationentity)|false|none|none|
|emails|[[Email](#schemaemail)]|false|none|none|
|phones|[[Phone](#schemaphone)]|false|none|none|

</div>
<div class="code-examples">

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
</div>
</div>

<div class="schema-data">
<div class="description">

<h2 id="tocS_State">State</h2>
<!-- backwards compatibility -->
<a id="schemastate"></a>
<a id="schema_State"></a>
<a id="tocSstate"></a>
<a id="tocsstate"></a>

State

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|State|string|false|none|State in format [ISO 3166-2]|

</div>
<div class="code-examples">

```json
"string"

```
</div>
</div>

<div class="schema-data">
<div class="description">

<h2 id="tocS_Account">Account</h2>
<!-- backwards compatibility -->
<a id="schemaaccount"></a>
<a id="schema_Account"></a>
<a id="tocSaccount"></a>
<a id="tocsaccount"></a>

Account

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|name|string|true|none|Account name.|
|email|[Email](#schemaemail)|true|none|none|
|password|string(password)|true|none|Account password.|

</div>
<div class="code-examples">

```json
{
  "name": "Cofe shop",
  "email": "shop@vertex.com",
  "password": "password"
}

```
</div>
</div>

<div class="schema-data">
<div class="description">

<h2 id="tocS_AccountEntity">AccountEntity</h2>
<!-- backwards compatibility -->
<a id="schemaaccountentity"></a>
<a id="schema_AccountEntity"></a>
<a id="tocSaccountentity"></a>
<a id="tocsaccountentity"></a>

Account Entity

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|Account Entity|[Entity](#schemaentity)|false|none|none|
|name|string|true|none|Account name.|
|email|[Email](#schemaemail)|true|none|none|

</div>
<div class="code-examples">

```json
{
  "id": 656,
  "name": "Cofe shop",
  "email": "shop@vertex.com"
}

```
</div>
</div>

<div class="schema-data">
<div class="description">

<h2 id="tocS_AccountInfo">AccountInfo</h2>
<!-- backwards compatibility -->
<a id="schemaaccountinfo"></a>
<a id="schema_AccountInfo"></a>
<a id="tocSaccountinfo"></a>
<a id="tocsaccountinfo"></a>

Account Info

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|account|[AccountEntity](#schemaaccountentity)|false|none|none|
|businessInfo|[BusinessInfoEntity](#schemabusinessinfoentity)|false|none|Account business information. <br>This information includes business name and tax identifier.|
|locations|[Locations](#schemalocations)|false|none|none|

</div>
<div class="code-examples">

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
</div>
</div>

<div class="schema-data">
<div class="description">

<h2 id="tocS_TokenType">TokenType</h2>
<!-- backwards compatibility -->
<a id="schematokentype"></a>
<a id="schema_TokenType"></a>
<a id="tocStokentype"></a>
<a id="tocstokentype"></a>

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
<div class="code-examples">

```json
{
  "type": "public"
}

```
</div>
</div>

<div class="schema-data">
<div class="description">

<h2 id="tocS_Token">Token</h2>
<!-- backwards compatibility -->
<a id="schematoken"></a>
<a id="schema_Token"></a>
<a id="tocStoken"></a>
<a id="tocstoken"></a>

Token

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|type|[TokenType](#schematokentype)|true|none|An enumeration that represents available Token Types.<br>| value    | description                                    |<br>|----------|------------------------------------------------|<br>| public   | This token gives acces to the sandbox          |<br>| private  | This token gives acces to the production env   ||
|token|string|true|none|API Authentication token.|
|created|[DateTime](#schemadatetime)|true|none|Date-time in format [ISO-8601], YYYY-MM-DDThh:mm:ssTZD|

</div>
<div class="code-examples">

```json
{
  "type": "sandbox",
  "token": "1324325543234324",
  "created": "2019-08-23T12:23:56TZ2"
}

```
</div>
</div>

<div class="schema-data">
<div class="description">

<h2 id="tocS_Tokens">Tokens</h2>
<!-- backwards compatibility -->
<a id="schematokens"></a>
<a id="schema_Tokens"></a>
<a id="tocStokens"></a>
<a id="tocstokens"></a>

Token collection

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|pagination|[Pagination](#schemapagination)|false|none|Hypermedia approach for pagination, contains links<br>for current, previous and next pages.|
|fetchInfo|[FetchInfo](#schemafetchinfo)|false|none|Data fetch info.<br>Used for implementing data pagination.|
|tokens|[[Token](#schematoken)]|false|none|none|

</div>
<div class="code-examples">

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
</div>
</div>

<div class="schema-data">
<div class="description">

<h2 id="tocS_BusinessInfo">BusinessInfo</h2>
<!-- backwards compatibility -->
<a id="schemabusinessinfo"></a>
<a id="schema_BusinessInfo"></a>
<a id="tocSbusinessinfo"></a>
<a id="tocsbusinessinfo"></a>

Business information

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|businessName|string|true|none|Business name.|
|fedTaxId|string|true|none|Federal tax identifier.|

</div>
<div class="code-examples">

```json
{
  "businessName": "Cofe shop LTD",
  "fedTaxId": "2321-2323-2132"
}

```
</div>
</div>

<div class="schema-data">
<div class="description">

<h2 id="tocS_BusinessInfoEntity">BusinessInfoEntity</h2>
<!-- backwards compatibility -->
<a id="schemabusinessinfoentity"></a>
<a id="schema_BusinessInfoEntity"></a>
<a id="tocSbusinessinfoentity"></a>
<a id="tocsbusinessinfoentity"></a>

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
<div class="code-examples">

```json
{
  "id": 234,
  "businessName": "Cofe shop LTD",
  "fedTaxId": "2321-2323-2132"
}

```
</div>
</div>

<div class="schema-data">
<div class="description">

<h2 id="tocS_TaxCategory">TaxCategory</h2>
<!-- backwards compatibility -->
<a id="schemataxcategory"></a>
<a id="schema_TaxCategory"></a>
<a id="tocStaxcategory"></a>
<a id="tocstaxcategory"></a>

Tax Category

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|name|string|false|none|Tax category name.|
|confidence|integer|false|none|Prediction categorization confidence.|
|isManualy|boolean|false|none|Flag indicates that the tax category is defined manually.|
|isSelected|boolean|false|none|Flag indicates that the tax category is selected.|

</div>
<div class="code-examples">

```json
{
  "name": "sugar contains",
  "confidence": 90,
  "isManually": "true",
  "isSelected": "true"
}

```
</div>
</div>

<div class="schema-data">
<div class="description">

<h2 id="tocS_TaxCategoryEntity">TaxCategoryEntity</h2>
<!-- backwards compatibility -->
<a id="schemataxcategoryentity"></a>
<a id="schema_TaxCategoryEntity"></a>
<a id="tocStaxcategoryentity"></a>
<a id="tocstaxcategoryentity"></a>

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
<div class="code-examples">

```json
{
  "id": 556,
  "name": "sugar contains",
  "confidence": 90,
  "isManually": "true",
  "isSelected": "true"
}

```
</div>
</div>

<div class="schema-data">
<div class="description">

<h2 id="tocS_TaxCategories">TaxCategories</h2>
<!-- backwards compatibility -->
<a id="schemataxcategories"></a>
<a id="schema_TaxCategories"></a>
<a id="tocStaxcategories"></a>
<a id="tocstaxcategories"></a>

Tax Category collection

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|Tax Category collection|[[TaxCategoryEntity](#schemataxcategoryentity)]|false|none|none|

</div>
<div class="code-examples">

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
</div>
</div>

<div class="schema-data">
<div class="description">

<h2 id="tocS_ProductCatalog">ProductCatalog</h2>
<!-- backwards compatibility -->
<a id="schemaproductcatalog"></a>
<a id="schema_ProductCatalog"></a>
<a id="tocSproductcatalog"></a>
<a id="tocsproductcatalog"></a>

Product Catalog

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|name|string|false|none|Product name.|
|merchantId|integer|false|none|Sale point/merchant identifier.|
|platformId|integer|false|none|Platform identifier.|

</div>
<div class="code-examples">

```json
{
  "name": "string",
  "merchantId": 0,
  "platformId": 0
}

```
</div>
</div>

<div class="schema-data">
<div class="description">

<h2 id="tocS_ProductCatalogEntity">ProductCatalogEntity</h2>
<!-- backwards compatibility -->
<a id="schemaproductcatalogentity"></a>
<a id="schema_ProductCatalogEntity"></a>
<a id="tocSproductcatalogentity"></a>
<a id="tocsproductcatalogentity"></a>

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
<div class="code-examples">

```json
{
  "id": 0,
  "salePoint": "string",
  "name": "string",
  "merchantId": 0,
  "platformId": 0
}

```
</div>
</div>

<div class="schema-data">
<div class="description">

<h2 id="tocS_ProductCatalogs">ProductCatalogs</h2>
<!-- backwards compatibility -->
<a id="schemaproductcatalogs"></a>
<a id="schema_ProductCatalogs"></a>
<a id="tocSproductcatalogs"></a>
<a id="tocsproductcatalogs"></a>

Product Catalog сollection

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|catalogs|[[ProductCatalogEntity](#schemaproductcatalogentity)]|false|none|none|

</div>
<div class="code-examples">

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
</div>
</div>

<div class="schema-data">
<div class="description">

<h2 id="tocS_Category">Category</h2>
<!-- backwards compatibility -->
<a id="schemacategory"></a>
<a id="schema_Category"></a>
<a id="tocScategory"></a>
<a id="tocscategory"></a>

Product Catalog category

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|Product Catalog category|string|false|none|none|

</div>
<div class="code-examples">

```json
"Videoserver"

```
</div>
</div>

<div class="schema-data">
<div class="description">

<h2 id="tocS_Categories">Categories</h2>
<!-- backwards compatibility -->
<a id="schemacategories"></a>
<a id="schema_Categories"></a>
<a id="tocScategories"></a>
<a id="tocscategories"></a>

Catalog Category collection

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|Catalog Category collection|[[Category](#schemacategory)]|false|none|none|

</div>
<div class="code-examples">

```json
[
  "Videoserver"
]

```
</div>
</div>

<div class="schema-data">
<div class="description">

<h2 id="tocS_MappingType">MappingType</h2>
<!-- backwards compatibility -->
<a id="schemamappingtype"></a>
<a id="schema_MappingType"></a>
<a id="tocSmappingtype"></a>
<a id="tocsmappingtype"></a>

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
<div class="code-examples">

```json
"autoMapped"

```
</div>
</div>

<div class="schema-data">
<div class="description">

<h2 id="tocS_Image">Image</h2>
<!-- backwards compatibility -->
<a id="schemaimage"></a>
<a id="schema_Image"></a>
<a id="tocSimage"></a>
<a id="tocsimage"></a>

Image

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|url|[Link](#schemalink)|true|none|Absolute URI.|
|width|integer|true|none|Image width.|
|height|integer|false|none|Image height.|

</div>
<div class="code-examples">

```json
{
  "url": "https//stripe.com/images/img.png",
  "width": 32,
  "height": 32
}

```
</div>
</div>

<div class="schema-data">
<div class="description">

<h2 id="tocS_Product">Product</h2>
<!-- backwards compatibility -->
<a id="schemaproduct"></a>
<a id="schema_Product"></a>
<a id="tocSproduct"></a>
<a id="tocsproduct"></a>

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
<div class="code-examples">

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
</div>
</div>

<div class="schema-data">
<div class="description">

<h2 id="tocS_ProductEntity">ProductEntity</h2>
<!-- backwards compatibility -->
<a id="schemaproductentity"></a>
<a id="schema_ProductEntity"></a>
<a id="tocSproductentity"></a>
<a id="tocsproductentity"></a>

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
<div class="code-examples">

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
</div>
</div>

<div class="schema-data">
<div class="description">

<h2 id="tocS_StockUnit">StockUnit</h2>
<!-- backwards compatibility -->
<a id="schemastockunit"></a>
<a id="schema_StockUnit"></a>
<a id="tocSstockunit"></a>
<a id="tocsstockunit"></a>

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
<div class="code-examples">

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
</div>
</div>

<div class="schema-data">
<div class="description">

<h2 id="tocS_StockUnitEntity">StockUnitEntity</h2>
<!-- backwards compatibility -->
<a id="schemastockunitentity"></a>
<a id="schema_StockUnitEntity"></a>
<a id="tocSstockunitentity"></a>
<a id="tocsstockunitentity"></a>

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
<div class="code-examples">

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
</div>
</div>

<div class="schema-data">
<div class="description">

<h2 id="tocS_Products">Products</h2>
<!-- backwards compatibility -->
<a id="schemaproducts"></a>
<a id="schema_Products"></a>
<a id="tocSproducts"></a>
<a id="tocsproducts"></a>

Product collection

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|pagination|[Pagination](#schemapagination)|false|none|Hypermedia approach for pagination, contains links<br>for current, previous and next pages.|
|fetchInfo|[FetchInfo](#schemafetchinfo)|false|none|Data fetch info.<br>Used for implementing data pagination.|
|products|[[ProductEntity](#schemaproductentity)]|false|none|none|

</div>
<div class="code-examples">

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
</div>
</div>

<div class="schema-data">
<div class="description">

<h2 id="tocS_TaxLevel">TaxLevel</h2>
<!-- backwards compatibility -->
<a id="schemataxlevel"></a>
<a id="schema_TaxLevel"></a>
<a id="tocStaxlevel"></a>
<a id="tocstaxlevel"></a>

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
<div class="code-examples">

```json
"state"

```
</div>
</div>

<div class="schema-data">
<div class="description">

<h2 id="tocS_TaxRate">TaxRate</h2>
<!-- backwards compatibility -->
<a id="schemataxrate"></a>
<a id="schema_TaxRate"></a>
<a id="tocStaxrate"></a>
<a id="tocstaxrate"></a>

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
<div class="code-examples">

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
</div>
</div>

<div class="schema-data">
<div class="description">

<h2 id="tocS_Tax">Tax</h2>
<!-- backwards compatibility -->
<a id="schematax"></a>
<a id="schema_Tax"></a>
<a id="tocStax"></a>
<a id="tocstax"></a>

Tax

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|rate|[TaxRate](#schemataxrate)|false|none|none|
|amount|[Amount](#schemaamount)|false|none|Amont in format is [ISO 20022]. <br>The decimal separator is a dot. NNNN.NN|

</div>
<div class="code-examples">

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
</div>
</div>

<div class="schema-data">
<div class="description">

<h2 id="tocS_TransactionType">TransactionType</h2>
<!-- backwards compatibility -->
<a id="schematransactiontype"></a>
<a id="schema_TransactionType"></a>
<a id="tocStransactiontype"></a>
<a id="tocstransactiontype"></a>

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
<div class="code-examples">

```json
"new"

```
</div>
</div>

<div class="schema-data">
<div class="description">

<h2 id="tocS_TransactionStatus">TransactionStatus</h2>
<!-- backwards compatibility -->
<a id="schematransactionstatus"></a>
<a id="schema_TransactionStatus"></a>
<a id="tocStransactionstatus"></a>
<a id="tocstransactionstatus"></a>

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
<div class="code-examples">

```json
"preview"

```
</div>
</div>

<div class="schema-data">
<div class="description">

<h2 id="tocS_Transaction">Transaction</h2>
<!-- backwards compatibility -->
<a id="schematransaction"></a>
<a id="schema_Transaction"></a>
<a id="tocStransaction"></a>
<a id="tocstransaction"></a>

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
<div class="code-examples">

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
</div>
</div>

<div class="schema-data">
<div class="description">

<h2 id="tocS_TransactionEntity">TransactionEntity</h2>
<!-- backwards compatibility -->
<a id="schematransactionentity"></a>
<a id="schema_TransactionEntity"></a>
<a id="tocStransactionentity"></a>
<a id="tocstransactionentity"></a>

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
<div class="code-examples">

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
</div>
</div>

<div class="schema-data">
<div class="description">

<h2 id="tocS_Transactions">Transactions</h2>
<!-- backwards compatibility -->
<a id="schematransactions"></a>
<a id="schema_Transactions"></a>
<a id="tocStransactions"></a>
<a id="tocstransactions"></a>

Transaction collection

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|pagination|[Pagination](#schemapagination)|false|none|Hypermedia approach for pagination, contains links<br>for current, previous and next pages.|
|fetchInfo|[FetchInfo](#schemafetchinfo)|false|none|Data fetch info.<br>Used for implementing data pagination.|
|transactions|[[TransactionEntity](#schematransactionentity)]|false|none|none|

</div>
<div class="code-examples">

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
</div>
</div>

<div class="schema-data">
<div class="description">

<h2 id="tocS_OrderItem">OrderItem</h2>
<!-- backwards compatibility -->
<a id="schemaorderitem"></a>
<a id="schema_OrderItem"></a>
<a id="tocSorderitem"></a>
<a id="tocsorderitem"></a>

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
<div class="code-examples">

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
</div>
</div>

<div class="schema-data">
<div class="description">

<h2 id="tocS_OrderTotal">OrderTotal</h2>
<!-- backwards compatibility -->
<a id="schemaordertotal"></a>
<a id="schema_OrderTotal"></a>
<a id="tocSordertotal"></a>
<a id="tocsordertotal"></a>

Order Total

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|total|[Amount](#schemaamount)|false|none|Amont in format is [ISO 20022]. <br>The decimal separator is a dot. NNNN.NN|
|subTotal|[Amount](#schemaamount)|false|none|Amont in format is [ISO 20022]. <br>The decimal separator is a dot. NNNN.NN|
|totalTax|[Amount](#schemaamount)|false|none|Amont in format is [ISO 20022]. <br>The decimal separator is a dot. NNNN.NN|
|taxDetails|[[Tax](#schematax)]|false|none|none|

</div>
<div class="code-examples">

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
</div>
</div>

<div class="schema-data">
<div class="description">

<h2 id="tocS_Order">Order</h2>
<!-- backwards compatibility -->
<a id="schemaorder"></a>
<a id="schema_Order"></a>
<a id="tocSorder"></a>
<a id="tocsorder"></a>

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
<div class="code-examples">

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
</div>
</div>

<div class="schema-data">
<div class="description">

<h2 id="tocS_OrderEntity">OrderEntity</h2>
<!-- backwards compatibility -->
<a id="schemaorderentity"></a>
<a id="schema_OrderEntity"></a>
<a id="tocSorderentity"></a>
<a id="tocsorderentity"></a>

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
<div class="code-examples">

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
</div>
</div>

<div class="schema-data">
<div class="description">

<h2 id="tocS_TransactionSummary">TransactionSummary</h2>
<!-- backwards compatibility -->
<a id="schematransactionsummary"></a>
<a id="schema_TransactionSummary"></a>
<a id="tocStransactionsummary"></a>
<a id="tocstransactionsummary"></a>

Transaction Summary

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|countTrans|integer|false|none|Number of the transactions.|
|totalSales|[Amount](#schemaamount)|false|none|Amont in format is [ISO 20022]. <br>The decimal separator is a dot. NNNN.NN|
|totalTax|[Amount](#schemaamount)|false|none|Amont in format is [ISO 20022]. <br>The decimal separator is a dot. NNNN.NN|

</div>
<div class="code-examples">

```json
{
  "countTrans": 343,
  "totalSales": 6565.9,
  "totalTax": 34.3
}

```
</div>
</div>

<div class="schema-data">
<div class="description">

<h2 id="tocS_Log">Log</h2>
<!-- backwards compatibility -->
<a id="schemalog"></a>
<a id="schema_Log"></a>
<a id="tocSlog"></a>
<a id="tocslog"></a>

Log

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|request|[Link](#schemalink)|false|none|Absolute URI.|
|response|[Link](#schemalink)|false|none|Absolute URI.|
|date|[Date](#schemadate)|false|none|Date in format [ISO-8601], YYYY-MM-DD|
|salePoint|string|false|none|Sale point identifier, email.|

</div>
<div class="code-examples">

```json
{
  "request": "http://192.168.0.17/api/v1.2/nextPage?size=12",
  "response": "http://192.168.0.17/api/v1.2/nextPage?size=12",
  "date": "2010-10-11",
  "salePoint": "string"
}

```
</div>
</div>

<div class="schema-data">
<div class="description">

<h2 id="tocS_Logs">Logs</h2>
<!-- backwards compatibility -->
<a id="schemalogs"></a>
<a id="schema_Logs"></a>
<a id="tocSlogs"></a>
<a id="tocslogs"></a>

Log collection

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|logs|[[Log](#schemalog)]|false|none|[Tax calculation log.<br>]|

</div>
<div class="code-examples">

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
</div>
</div>

