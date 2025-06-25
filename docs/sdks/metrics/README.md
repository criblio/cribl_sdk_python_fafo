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
from cribl_sdk_python_fafo import CriblSDKPythonFafo, models
import os


with CriblSDKPythonFafo(
    server_url="https://api.example.com",
    security=models.Security(
        bearer_auth=os.getenv("CRIBLSDKPYTHONFAFO_BEARER_AUTH", ""),
    ),
) as cspf_client:

    res = cspf_client.metrics.create_system_metrics_enum()

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                             | Type                                                                  | Required                                                              | Description                                                           |
| --------------------------------------------------------------------- | --------------------------------------------------------------------- | --------------------------------------------------------------------- | --------------------------------------------------------------------- |
| `dim_key_filter`                                                      | [Optional[models.DimKeyFilter]](../../models/dimkeyfilter.md)         | :heavy_minus_sign:                                                    | N/A                                                                   |
| `dim_value_filter`                                                    | [Optional[models.DimValueFilter]](../../models/dimvaluefilter.md)     | :heavy_minus_sign:                                                    | N/A                                                                   |
| `earliest`                                                            | *Optional[float]*                                                     | :heavy_minus_sign:                                                    | N/A                                                                   |
| `filter_expr`                                                         | *Optional[str]*                                                       | :heavy_minus_sign:                                                    | N/A                                                                   |
| `max_values`                                                          | *Optional[float]*                                                     | :heavy_minus_sign:                                                    | N/A                                                                   |
| `metric_name_filter`                                                  | [Optional[models.MetricNameFilter]](../../models/metricnamefilter.md) | :heavy_minus_sign:                                                    | N/A                                                                   |
| `retries`                                                             | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)      | :heavy_minus_sign:                                                    | Configuration to override the default retry behavior of the client.   |

### Response

**[models.CreateSystemMetricsEnumResponse](../../models/createsystemmetricsenumresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| errors.Error     | 500              | application/json |
| errors.APIError  | 4XX, 5XX         | \*/\*            |

## get_system_metrics

Query raw internal system metrics

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

    res = cspf_client.metrics.get_system_metrics()

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

**[models.GetSystemMetricsResponse](../../models/getsystemmetricsresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| errors.Error     | 500              | application/json |
| errors.APIError  | 4XX, 5XX         | \*/\*            |

## create_system_metrics_query

Aggregate raw internal system metrics

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

    res = cspf_client.metrics.create_system_metrics_query(aggs={
        "aggregations": [],
        "cumulative": False,
        "flush_event_limit": 9835.34,
        "flush_mem_limit": 7220.64,
        "hostname": "handy-kielbasa.info",
        "metrics_mode": False,
        "sufficient_stats_only": True,
        "time_window_seconds": 7794.15,
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

**[models.CreateSystemMetricsQueryResponse](../../models/createsystemmetricsqueryresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| errors.Error     | 500              | application/json |
| errors.APIError  | 4XX, 5XX         | \*/\*            |