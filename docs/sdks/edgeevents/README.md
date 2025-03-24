# EdgeEvents
(*edge_events*)

## Overview

Actions related to EdgeEvents

### Available Operations

* [get_edge_events_collectors](#get_edge_events_collectors) - Get list of configured collectors

## get_edge_events_collectors

Get list of configured collectors

### Example Usage

```python
import cribl
from cribl import Cribl
import os


with Cribl(
    security=cribl.SecurityModel(
        bearer_auth=os.getenv("CRIBL_BEARER_AUTH", ""),
    ),
) as c_client:

    res = c_client.edge_events.get_edge_events_collectors()

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.GetEdgeEventsCollectorsResponseBody](../../models/getedgeeventscollectorsresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |