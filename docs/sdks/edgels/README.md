# EdgeLs
(*edge_ls*)

## Overview

Actions related to Edge listing

### Available Operations

* [get_edge_ls_by_path](#get_edge_ls_by_path) - Get a directory listing of the given path

## get_edge_ls_by_path

Get a directory listing of the given path

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

    res = c_client.edge_ls.get_edge_ls_by_path(path="/net")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `path`                                                              | *str*                                                               | :heavy_check_mark:                                                  | Defaults to empty for the root directory                            |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.GetEdgeLsByPathResponseBody](../../models/getedgelsbypathresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |