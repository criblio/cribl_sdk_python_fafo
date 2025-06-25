# Logging
(*logging*)

## Overview

Actions related to logging

### Available Operations

* [get_system_jobs_logs_by_id_and_group_id](#get_system_jobs_logs_by_id_and_group_id) - Get contents of the log file
* [get_system_logs_by_id](#get_system_logs_by_id) - Get contents of the log file
* [get_system_logs](#get_system_logs) - Get a list of log files
* [get_system_logs_search](#get_system_logs_search) - Get contents of the log file

## get_system_jobs_logs_by_id_and_group_id

Get contents of the log file

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

    res = cspf_client.logging.get_system_jobs_logs_by_id_and_group_id(id="<id>", group_id="<id>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                                     | Type                                                                          | Required                                                                      | Description                                                                   |
| ----------------------------------------------------------------------------- | ----------------------------------------------------------------------------- | ----------------------------------------------------------------------------- | ----------------------------------------------------------------------------- |
| `id`                                                                          | *str*                                                                         | :heavy_check_mark:                                                            | Job id                                                                        |
| `group_id`                                                                    | *str*                                                                         | :heavy_check_mark:                                                            | Group ID (optional)                                                           |
| `limit`                                                                       | *Optional[int]*                                                               | :heavy_minus_sign:                                                            | Maximum number of log lines to retrieve starting from offset.                 |
| `offset`                                                                      | *Optional[int]*                                                               | :heavy_minus_sign:                                                            | Offset in the current log file to fetch the log events from.                  |
| `end_offset`                                                                  | *Optional[int]*                                                               | :heavy_minus_sign:                                                            | in the current log file to fetch the log events upto.                         |
| `et`                                                                          | *Optional[int]*                                                               | :heavy_minus_sign:                                                            | Epoch timestamp of the earliest event (includes rolled files present on disk) |
| `lt`                                                                          | *Optional[int]*                                                               | :heavy_minus_sign:                                                            | Epoch timestamp of the latest event (includes rolled files present on disk)   |
| `filter_`                                                                     | *Optional[str]*                                                               | :heavy_minus_sign:                                                            | Filter                                                                        |
| `retries`                                                                     | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)              | :heavy_minus_sign:                                                            | Configuration to override the default retry behavior of the client.           |

### Response

**[models.GetSystemJobsLogsByIDAndGroupIDResponse](../../models/getsystemjobslogsbyidandgroupidresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| errors.Error     | 500              | application/json |
| errors.APIError  | 4XX, 5XX         | \*/\*            |

## get_system_logs_by_id

Get contents of the log file

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

    res = cspf_client.logging.get_system_logs_by_id(id="<id>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                                     | Type                                                                          | Required                                                                      | Description                                                                   |
| ----------------------------------------------------------------------------- | ----------------------------------------------------------------------------- | ----------------------------------------------------------------------------- | ----------------------------------------------------------------------------- |
| `id`                                                                          | *str*                                                                         | :heavy_check_mark:                                                            | Log ID                                                                        |
| `limit`                                                                       | *Optional[int]*                                                               | :heavy_minus_sign:                                                            | Maximum number of log lines to retrieve starting from offset.                 |
| `end_offset`                                                                  | *Optional[int]*                                                               | :heavy_minus_sign:                                                            | in the current log file to fetch the log events upto.                         |
| `et`                                                                          | *Optional[int]*                                                               | :heavy_minus_sign:                                                            | Epoch timestamp of the earliest event (includes rolled files present on disk) |
| `lt`                                                                          | *Optional[int]*                                                               | :heavy_minus_sign:                                                            | Epoch timestamp of the latest event (includes rolled files present on disk)   |
| `filter_`                                                                     | *Optional[str]*                                                               | :heavy_minus_sign:                                                            | Filter                                                                        |
| `retries`                                                                     | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)              | :heavy_minus_sign:                                                            | Configuration to override the default retry behavior of the client.           |

### Response

**[models.GetSystemLogsByIDResponse](../../models/getsystemlogsbyidresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| errors.Error     | 500              | application/json |
| errors.APIError  | 4XX, 5XX         | \*/\*            |

## get_system_logs

Get a list of log files

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

    res = cspf_client.logging.get_system_logs()

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.GetSystemLogsResponse](../../models/getsystemlogsresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| errors.Error     | 500              | application/json |
| errors.APIError  | 4XX, 5XX         | \*/\*            |

## get_system_logs_search

Get contents of the log file

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

    res = cspf_client.logging.get_system_logs_search(type_="<value>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                                     | Type                                                                          | Required                                                                      | Description                                                                   |
| ----------------------------------------------------------------------------- | ----------------------------------------------------------------------------- | ----------------------------------------------------------------------------- | ----------------------------------------------------------------------------- |
| `type`                                                                        | *str*                                                                         | :heavy_check_mark:                                                            | type of logs request single multi group                                       |
| `group_id`                                                                    | *Optional[str]*                                                               | :heavy_minus_sign:                                                            | id of the group to query                                                      |
| `files`                                                                       | *Optional[str]*                                                               | :heavy_minus_sign:                                                            | query string[] optional file or files to query                                |
| `limit`                                                                       | *Optional[int]*                                                               | :heavy_minus_sign:                                                            | Maximum number of log lines to retrieve starting from offset.                 |
| `et`                                                                          | *Optional[int]*                                                               | :heavy_minus_sign:                                                            | Epoch timestamp of the earliest event (includes rolled files present on disk) |
| `lt`                                                                          | *Optional[int]*                                                               | :heavy_minus_sign:                                                            | Epoch timestamp of the latest event (includes rolled files present on disk)   |
| `filter_`                                                                     | *Optional[str]*                                                               | :heavy_minus_sign:                                                            | Filter                                                                        |
| `retries`                                                                     | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)              | :heavy_minus_sign:                                                            | Configuration to override the default retry behavior of the client.           |

### Response

**[models.GetSystemLogsSearchResponse](../../models/getsystemlogssearchresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| errors.Error     | 500              | application/json |
| errors.APIError  | 4XX, 5XX         | \*/\*            |