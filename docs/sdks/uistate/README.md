# UIState
(*ui_state*)

## Overview

Actions related to UiState

### Available Operations

* [get_ui_by_key](#get_ui_by_key) - Get UI state by key
* [update_ui_by_key](#update_ui_by_key) - Update UI state by key

## get_ui_by_key

Get UI state by key

### Example Usage

```python
from cribl import Cribl
import os


with Cribl(
    bearer_auth=os.getenv("CRIBL_BEARER_AUTH", ""),
) as c_client:

    res = c_client.ui_state.get_ui_by_key(key="<key>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `key`                                                               | *str*                                                               | :heavy_check_mark:                                                  | UI state key                                                        |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.GetUIByKeyResponseBody](../../models/getuibykeyresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |

## update_ui_by_key

Update UI state by key

### Example Usage

```python
import cribl
from cribl import Cribl
import os


with Cribl(
    bearer_auth=os.getenv("CRIBL_BEARER_AUTH", ""),
) as c_client:

    res = c_client.ui_state.update_ui_by_key(key="<key>", op=cribl.Op.SET, value="<value>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `key`                                                               | *str*                                                               | :heavy_check_mark:                                                  | UI state key                                                        |
| `op`                                                                | [models.Op](../../models/op.md)                                     | :heavy_check_mark:                                                  | N/A                                                                 |
| `value`                                                             | *Any*                                                               | :heavy_check_mark:                                                  | N/A                                                                 |
| `args`                                                              | Dict[str, *Any*]                                                    | :heavy_minus_sign:                                                  | N/A                                                                 |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.UpdateUIByKeyResponseBody](../../models/updateuibykeyresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |