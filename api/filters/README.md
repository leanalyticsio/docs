# API FILTERS

**_Connection_**:

  - **Protocol**: "https"
  - **Host**: "mts-api-filters.leanalytics.io"
  - **Port**: 443

**_OauthBearerToken_**: "\<token\>"

**_FilterType_**:

  - **b64_sha256**: **string**
  - **string**: **string**
  - **integer**: **string**

**_Filter_**:

  - **key**: **string**
  - **value**: **string**
  - **type**: OneOf(**FilterType**)

**_Filters_**:

  - **Filter**
  - ..

## Filters

### GET /filters

**_RequestHeaders_**:

  - **Authorization**: "Bearer **OauthBearerToken**"

**_HttpResponseHeaders_**:

  - **200**: "Content-Type: application/json"

**_HttpResponseCode_**:

  - **200**: **Filters**

## Context Filters

### GET /context-filters

**_RequestHeaders_**:

  - **Authorization**: "Bearer **OauthBearerToken**"

**_HttpResponseHeaders_**:

  - **200**: "Content-Type: application/json"

**_HttpResponseCode_**:

  - **200**: **Filters**
