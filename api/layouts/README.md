# API LAYOUTS

**_Connection_**:

  - **Protocol**: "https"
  - **Host**: "mts-api-layouts.leanalytics.io"
  - **Port**: 443


**_OauthBearerToken_**: "\<token\>"

**_Layout_**:

  - **createdAt**: **date**
  - **updatedAt**: **date**
  - **id**: "\<layout_id\>"
  - **domainId**: "\<domain_id\>"
  - **value**: **string**
  - **raw_value**: **string**
  - **name**: "\<layout_name\>"

**_Layouts_**:

  - **layout**
  - ..

## Layouts

### GET /domain/\<domain_id\>

**_RequestHeaders_**:

  - **Authorization**: "Bearer **OauthBearerToken**"

**_HttpResponseHeaders_**:

  - 200: "Content-Type: application/json"

**_HttpResponseCode_**:

  - 200: **layouts**
  - 401
  - 403
  - 404
  - 406

### GET /domain/\<domain_id\>/\<layout_name\>

**_RequestHeaders_**:

  - **Authorization**: "Bearer **OauthBearerToken**"

**_HttpResponseHeaders_**:

  - 200: "Content-Type: application/json"

**_HttpResponseCode_**:

  - 200: **layout**
  - 401
  - 403
  - 404
  - 406

### DELETE /domain/\<domain_id\>/\<layout_name\>

**_RequestHeaders_**:

  - **Authorization**: "Bearer **OauthBearerToken**"

**_HttpResponseCode_**:

  - 401
  - 403
  - 404
  - 406
  - 410

### POST /domain/\<domain_id\>

**_RequestHeaders_**:

  - **Authorization**: "Bearer **OauthBearerToken**"
  - **Content-Type**: "application/x-www-form-urlencoded"

**_Parameters_**:

  - **name**: "\<layout_name\>"
  - **value**:  **string**

**_HttpResponseCode_**:

  - 201: "\<layout_id\>"
  - 401
  - 403
  - 404
  - 406
  - 409
