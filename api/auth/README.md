# API AUTH

**_Connection_**:

  - **Protocol**: "https"
  - **Host**: "mts-api-auth.leanalytics.io"
  - **Port**: 443

**_GrantTypes_**:

  1. "**password**"

**_OauthClientHeader_**: base64("_\<oauth_client\>_:_\<oauth_secret\>_")

**_OauthBearerToken_**: "\<token\>"

**_OauthErrResponse_**:

  - **code**: **int**
  - **error**: **string**
  - **error_description**: **string**

**_UserId_**:

  - **Id**: "\<user_id\>"

**_User_**:

  - **FirstName**: "\<firstName\>"
  - **LastName**: "\<lastName\>"
  - **Email**: "\<email\>"
  - **ActiveDomains**: **boolean**

**_Domains_**:

  1. **Domain**
  2. ...

**_Domain_**:

  - **Id**: "\<domain_id\>"
  - **Name**: "\<domain_name\>"
  - **Created_At**: **date**

## Oauth

### POST /oauth/token

**_RequestHeaders_**:

  - **Authorization**: "Basic: **OauthClientHeader**"
  - **Content-Type**: "application/x-www-form-urlencoded"

**_Parameters_**:

  - **username**: "\<email\>_"
  - **password**: "\<password\>"
  - **grant_type**: OneOf(**GrantType**)

**_HttpResponseHeaders_**:

  - 400: "Content-Type: application/json"
  - 500: "Content-Type: application/json"

**_HttpResponseCode_**:

  - **200**: **OauthBearerToken**
  - **400**: **OauthErrResponse**
  - **500**: **OauthErrResponse**

## User

### GET /user

**_RequestHeaders_**:

  - **Authorization**: "Bearer **OauthBearerToken**"

**_HttpResponseHeaders_**:

  - 200: "Content-Type: application/json"

**_HttpResponseCode_**:

  - **200**: **UserId**

---

### POST /user

**_RequestHeaders_**:

  - **Content-Type**: "application/x-www-form-urlencoded"

**_Parameters_**:

  - **firstName**: "\<firstName\>"
  - **lastName**: "\<lastName\>"
  - **email**: "\<email\>"
  - **password**: "\<password\>"

**_HttpResponseCode_**:

  - 201: "\<user_id\>"
  - 406: "\<error_message\>"

---

### GET /user/\<user_id\>

**_RequestHeaders_**:

  - **Authorization**: "Bearer **OauthBearerToken**"

**_HttpResponseHeaders_**:

  - 200: "Content-Type: application/json"

**_HttpResponseCode_**:

  - 200: **User**
  - 401
  - 403

---

### PUT /user/\<user_id\>

**_RequestHeaders_**:

  - **Authorization**: "Bearer **OauthBearerToken**"
  - **Content-Type**: "application/x-www-form-urlencoded"

**_Parameters_**:

  - lastName: "\<firstName\>"
  - firstName: "\<lastName\>"
  - password: "\<password\>"

**_HttpResponseCode_**:

  - 200
  - 401
  - 403

## Domains

### GET /domain

**_RequestHeaders_**:

  - **Authorization**: "Bearer **OauthBearerToken**"

**_HttpResponseHeaders_**:

  - 200: "Content-Type: application/json"

**_HttpResponseCode_**:

  - 200: **Domains**
  - 401
  - 403
  - 404

---

### GET /domain/\<domain_id\>

**_RequestHeaders_**:

  - **Authorization**: "Bearer **OauthBearerToken**"

**_HttpResponseHeaders_**:

  - 200: "Content-Type: application/json"

**_HttpResponseCode_**:

  - 200: **Domain**
  - 401
  - 403
  - 404
