# Health
(*health*)

## Overview

Actions related to REST server health

### Available Operations

* [get_health_info](#get_health_info) - Provides health info for REST server

## get_health_info

Provides health info for REST server

### Example Usage

```python
from cribl import Cribl


with Cribl(
    server_url="https://api.example.com",
) as c_client:

    res = c_client.health.get_health_info()

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.HealthStatus](../../models/healthstatus.md)**

### Errors

| Error Type               | Status Code              | Content Type             |
| ------------------------ | ------------------------ | ------------------------ |
| models.HealthStatusError | 420                      | application/json         |
| models.APIError          | 4XX, 5XX                 | \*/\*                    |