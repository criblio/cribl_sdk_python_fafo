# Workers
(*workers*)

## Overview

Actions related to Workers

### Available Operations

* [get_summary_workers](#get_summary_workers) - get worker and edge nodes count
* [get_workers](#get_workers) - get worker and edge nodes
* [update_workers_restart](#update_workers_restart) - restarts worker nodes

## get_summary_workers

get worker and edge nodes count

### Example Usage

```python
from cribl import Cribl
import os


with Cribl(
    bearer_auth=os.getenv("CRIBL_BEARER_AUTH", ""),
) as c_client:

    res = c_client.workers.get_summary_workers()

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `filter_exp`                                                        | *Optional[str]*                                                     | :heavy_minus_sign:                                                  | Filter expression evaluated against nodes                           |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.GetSummaryWorkersResponseBody](../../models/getsummaryworkersresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |

## get_workers

get worker and edge nodes

### Example Usage

```python
from cribl import Cribl
import os


with Cribl(
    bearer_auth=os.getenv("CRIBL_BEARER_AUTH", ""),
) as c_client:

    res = c_client.workers.get_workers()

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `filter_exp`                                                        | *Optional[str]*                                                     | :heavy_minus_sign:                                                  | Filter expression evaluated against nodes                           |
| `sort_exp`                                                          | *Optional[str]*                                                     | :heavy_minus_sign:                                                  | Sorting expression evaluated against nodes                          |
| `limit`                                                             | *Optional[int]*                                                     | :heavy_minus_sign:                                                  | Maximum number of nodes to return                                   |
| `offset`                                                            | *Optional[int]*                                                     | :heavy_minus_sign:                                                  | Pagination offset                                                   |
| `filter_`                                                           | *Optional[str]*                                                     | :heavy_minus_sign:                                                  | Filter object (JSON stringified) to select nodes                    |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.GetWorkersResponseBody](../../models/getworkersresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |

## update_workers_restart

restarts worker nodes

### Example Usage

```python
from cribl import Cribl
import os


with Cribl(
    bearer_auth=os.getenv("CRIBL_BEARER_AUTH", ""),
) as c_client:

    res = c_client.workers.update_workers_restart()

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.UpdateWorkersRestartResponseBody](../../models/updateworkersrestartresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |