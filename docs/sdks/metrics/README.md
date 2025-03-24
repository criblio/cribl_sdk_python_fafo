# Metrics
(*metrics*)

## Overview

Actions related to metrics

### Available Operations

* [create_system_metrics_enum](#create_system_metrics_enum) - Enumerate all internal system metrics
* [get_system_metrics](#get_system_metrics) - Query raw internal system metrics
* [create_system_metrics_query](#create_system_metrics_query) - Aggregate raw internal system metrics

## create_system_metrics_enum

Enumerate all internal system metrics

### Example Usage

```python
from cribl import Cribl
import os


with Cribl(
    bearer_auth=os.getenv("CRIBL_BEARER_AUTH", ""),
) as c_client:

    res = c_client.metrics.create_system_metrics_enum()

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `request`                                                           | [models.SystemMetricsEnum](../../models/systemmetricsenum.md)       | :heavy_check_mark:                                                  | The request object to use for the request.                          |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.CreateSystemMetricsEnumResponseBody](../../models/createsystemmetricsenumresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |

## get_system_metrics

Query raw internal system metrics

### Example Usage

```python
from cribl import Cribl
import os


with Cribl(
    bearer_auth=os.getenv("CRIBL_BEARER_AUTH", ""),
) as c_client:

    res = c_client.metrics.get_system_metrics()

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                                     | Type                                                                          | Required                                                                      | Description                                                                   |
| ----------------------------------------------------------------------------- | ----------------------------------------------------------------------------- | ----------------------------------------------------------------------------- | ----------------------------------------------------------------------------- |
| `wp`                                                                          | *Optional[str]*                                                               | :heavy_minus_sign:                                                            | worker process to query, this would work only on a worker node                |
| `num_buckets`                                                                 | *Optional[float]*                                                             | :heavy_minus_sign:                                                            | buckets in the past to include in the query results                           |
| `earliest`                                                                    | *Optional[str]*                                                               | :heavy_minus_sign:                                                            | earliest time to query against                                                |
| `latest`                                                                      | *Optional[str]*                                                               | :heavy_minus_sign:                                                            | latest time to query against                                                  |
| `metric_name_filter`                                                          | *Optional[str]*                                                               | :heavy_minus_sign:                                                            | can be a regex or an array of metric names                                    |
| `filter_expr`                                                                 | *Optional[str]*                                                               | :heavy_minus_sign:                                                            | a js expression to apply against the metrics returned (can filter dimensions) |
| `retries`                                                                     | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)              | :heavy_minus_sign:                                                            | Configuration to override the default retry behavior of the client.           |

### Response

**[models.GetSystemMetricsResponseBody](../../models/getsystemmetricsresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |

## create_system_metrics_query

Aggregate raw internal system metrics

### Example Usage

```python
from cribl import Cribl
import os


with Cribl(
    bearer_auth=os.getenv("CRIBL_BEARER_AUTH", ""),
) as c_client:

    res = c_client.metrics.create_system_metrics_query(aggs={
        "aggregations": [

        ],
        "cumulative": True,
        "flush_event_limit": 6815.29,
        "flush_mem_limit": 4113.04,
        "hostname": "cool-invite.biz",
        "metrics_mode": False,
        "sufficient_stats_only": False,
        "time_window_seconds": 5869.17,
    })

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                                         | Type                                                                              | Required                                                                          | Description                                                                       |
| --------------------------------------------------------------------------------- | --------------------------------------------------------------------------------- | --------------------------------------------------------------------------------- | --------------------------------------------------------------------------------- |
| `aggs`                                                                            | [models.AggregationMgrOptions](../../models/aggregationmgroptions.md)             | :heavy_check_mark:                                                                | N/A                                                                               |
| `always_bounds`                                                                   | *Optional[bool]*                                                                  | :heavy_minus_sign:                                                                | N/A                                                                               |
| `earliest`                                                                        | [Optional[models.MetricsAggOptsEarliest]](../../models/metricsaggoptsearliest.md) | :heavy_minus_sign:                                                                | N/A                                                                               |
| `latest`                                                                          | [Optional[models.MetricsAggOptsLatest]](../../models/metricsaggoptslatest.md)     | :heavy_minus_sign:                                                                | N/A                                                                               |
| `metrics`                                                                         | [Optional[models.MetricsStore]](../../models/metricsstore.md)                     | :heavy_minus_sign:                                                                | N/A                                                                               |
| `where`                                                                           | *Optional[str]*                                                                   | :heavy_minus_sign:                                                                | N/A                                                                               |
| `retries`                                                                         | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)                  | :heavy_minus_sign:                                                                | Configuration to override the default retry behavior of the client.               |

### Response

**[models.CreateSystemMetricsQueryResponseBody](../../models/createsystemmetricsqueryresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |