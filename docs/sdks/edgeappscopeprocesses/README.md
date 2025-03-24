# EdgeAppScopeProcesses
(*edge_app_scope_processes*)

## Overview

Actions related to Edge AppScope processes

### Available Operations

* [create_edge_appscope_processes](#create_edge_appscope_processes) - Attach AppScope to a process running on the edge host
* [get_edge_appscope_processes](#get_edge_appscope_processes) - Get a detailed list of scoped processes running on the edge host
* [delete_edge_appscope_processes_by_pid](#delete_edge_appscope_processes_by_pid) - Detach AppScope from a process running on the edge host
* [get_edge_appscope_processes_by_pid](#get_edge_appscope_processes_by_pid) - Get details of a scoped process running on the edge host
* [update_edge_appscope_processes_by_pid](#update_edge_appscope_processes_by_pid) - Update AppScope configuration for a process running on the edge host

## create_edge_appscope_processes

Attach AppScope to a process running on the edge host

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

    res = c_client.edge_app_scope_processes.create_edge_appscope_processes(pid="<id>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `pid`                                                               | *str*                                                               | :heavy_check_mark:                                                  | config string required                                              |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.CreateEdgeAppscopeProcessesResponseBody](../../models/createedgeappscopeprocessesresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |

## get_edge_appscope_processes

Get a detailed list of scoped processes running on the edge host

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

    res = c_client.edge_app_scope_processes.get_edge_appscope_processes()

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.GetEdgeAppscopeProcessesResponseBody](../../models/getedgeappscopeprocessesresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |

## delete_edge_appscope_processes_by_pid

Detach AppScope from a process running on the edge host

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

    res = c_client.edge_app_scope_processes.delete_edge_appscope_processes_by_pid(pid="<id>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `pid`                                                               | *str*                                                               | :heavy_check_mark:                                                  | config string required                                              |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.DeleteEdgeAppscopeProcessesByPidResponseBody](../../models/deleteedgeappscopeprocessesbypidresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |

## get_edge_appscope_processes_by_pid

Get details of a scoped process running on the edge host

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

    res = c_client.edge_app_scope_processes.get_edge_appscope_processes_by_pid(pid="<id>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `pid`                                                               | *str*                                                               | :heavy_check_mark:                                                  | pid                                                                 |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.GetEdgeAppscopeProcessesByPidResponseBody](../../models/getedgeappscopeprocessesbypidresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |

## update_edge_appscope_processes_by_pid

Update AppScope configuration for a process running on the edge host

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

    res = c_client.edge_app_scope_processes.update_edge_appscope_processes_by_pid(pid="<id>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `pid`                                                               | *str*                                                               | :heavy_check_mark:                                                  | config string required                                              |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.UpdateEdgeAppscopeProcessesByPidResponseBody](../../models/updateedgeappscopeprocessesbypidresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |