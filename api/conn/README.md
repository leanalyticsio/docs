# API CONN

**_Connection_**:

  - **Protocol**: "https"
  - **Host**: "mts-api-conn.leanalytics.io"
  - **Port**: 443

**_OauthBearerToken_**: "\<token\>"

**_ElasticsearchQueryString_**: [doc here](https://www.elastic.co/guide/en/elasticsearch/reference/current/query-dsl-query-string-query.html)

**_ElasticsearchDateRange_**: [doc here](https://www.elastic.co/guide/en/elasticsearch/reference/current/query-dsl-range-query.html#_date_format_in_range_queries)

**_FilterField_**: "\<filter_value\>"

## Search

### GET /search/\<domain_id\>

**_RequestHeaders_**:

  - **Authorization**: "Bearer **OauthBearerToken**"
  - **Content-Type**: "application/x-www-form-urlencoded"

**_Parameters_**:

  - **qs**: **ElasticsearchQueryString**
  - **gte**: **ElasticsearchDateRange**
  - **context-filter-must**:
    - **FilterField**
  - **context-filter-must-not**:
    - **FilterField**
