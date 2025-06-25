# Query
(*query*)

## Overview

Actions related to Query

### Available Operations

* [get_search_query](#get_search_query) - Runs the query and returns the results

## get_search_query

Runs the query and returns the results

### Example Usage

```python
from cribl_sdk_python_fafo import CriblSDKPythonFafo, models
import os


with CriblSDKPythonFafo(
    server_url="https://api.example.com",
    security=models.Security(
        bearer_auth=os.getenv("CRIBLSDKPYTHONFAFO_BEARER_AUTH", ""),
    ),
) as cspf_client:

    res = cspf_client.query.get_search_query()

    with res as jsonl_stream:
        for event in jsonl_stream:
            # handle event
            print(event, flush=True)

```

### Parameters

| Parameter                                                                      | Type                                                                           | Required                                                                       | Description                                                                    |
| ------------------------------------------------------------------------------ | ------------------------------------------------------------------------------ | ------------------------------------------------------------------------------ | ------------------------------------------------------------------------------ |
| `query_id`                                                                     | *Optional[str]*                                                                | :heavy_minus_sign:                                                             | Saved query ID                                                                 |
| `job_id`                                                                       | *Optional[str]*                                                                | :heavy_minus_sign:                                                             | Job ID                                                                         |
| `query`                                                                        | *Optional[str]*                                                                | :heavy_minus_sign:                                                             | Search query string                                                            |
| `earliest`                                                                     | *Optional[float]*                                                              | :heavy_minus_sign:                                                             | Beginning of query time range, inclusive, in a relative time format or seconds |
| `latest`                                                                       | *Optional[float]*                                                              | :heavy_minus_sign:                                                             | End of query time range, exclusive, in a relative time format or seconds       |
| `sample_rate`                                                                  | *Optional[float]*                                                              | :heavy_minus_sign:                                                             | Number between 0-1 to sample events during search                              |
| `force`                                                                        | *Optional[bool]*                                                               | :heavy_minus_sign:                                                             | When true, forces to run the scheduled query                                   |
| `offset`                                                                       | *Optional[float]*                                                              | :heavy_minus_sign:                                                             | Pagination offset                                                              |
| `limit`                                                                        | *Optional[float]*                                                              | :heavy_minus_sign:                                                             | Pagination limit - maximum number of events to return                          |
| `retries`                                                                      | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)               | :heavy_minus_sign:                                                             | Configuration to override the default retry behavior of the client.            |

### Response

**[Union[jsonl.JsonLStream[models.SearchJobResults], jsonl.JsonLStreamAsync[models.SearchJobResults]]](../../models/.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| errors.Error     | 500              | application/json |
| errors.APIError  | 4XX, 5XX         | \*/\*            |