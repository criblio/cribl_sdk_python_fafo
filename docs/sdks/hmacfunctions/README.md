# HmacFunctions
(*hmac_functions*)

## Overview

Actions related to HMAC functions

### Available Operations

* [list_hmac_function](#list_hmac_function) - Get a list of HmacFunction objects
* [create_hmac_function](#create_hmac_function) - Create HmacFunction
* [get_hmac_function_by_id](#get_hmac_function_by_id) - Get HmacFunction by ID
* [update_hmac_function_by_id](#update_hmac_function_by_id) - Update HmacFunction
* [delete_hmac_function_by_id](#delete_hmac_function_by_id) - Delete HmacFunction

## list_hmac_function

Get a list of HmacFunction objects

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

    res = c_client.hmac_functions.list_hmac_function()

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.ListHmacFunctionResponseBody](../../models/listhmacfunctionresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |

## create_hmac_function

Create HmacFunction

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

    res = c_client.hmac_functions.create_hmac_function(header_expression="<value>", header_name="<value>", id="<id>", lib=cribl.CriblLib.CUSTOM, string_builders=[
        "<value>",
        "<value>",
    ])

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `header_expression`                                                 | *str*                                                               | :heavy_check_mark:                                                  | N/A                                                                 |
| `header_name`                                                       | *str*                                                               | :heavy_check_mark:                                                  | N/A                                                                 |
| `id`                                                                | *str*                                                               | :heavy_check_mark:                                                  | N/A                                                                 |
| `lib`                                                               | [models.CriblLib](../../models/cribllib.md)                         | :heavy_check_mark:                                                  | N/A                                                                 |
| `string_builders`                                                   | List[*str*]                                                         | :heavy_check_mark:                                                  | N/A                                                                 |
| `description`                                                       | *Optional[str]*                                                     | :heavy_minus_sign:                                                  | N/A                                                                 |
| `string_delim`                                                      | *Optional[str]*                                                     | :heavy_minus_sign:                                                  | N/A                                                                 |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.CreateHmacFunctionResponseBody](../../models/createhmacfunctionresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |

## get_hmac_function_by_id

Get HmacFunction by ID

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

    res = c_client.hmac_functions.get_hmac_function_by_id(id="<id>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `id`                                                                | *str*                                                               | :heavy_check_mark:                                                  | Unique ID to GET                                                    |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.GetHmacFunctionByIDResponseBody](../../models/gethmacfunctionbyidresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |

## update_hmac_function_by_id

Update HmacFunction

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

    res = c_client.hmac_functions.update_hmac_function_by_id(id_param="<value>", header_expression="<value>", header_name="<value>", id="<id>", lib=cribl.CriblLib.CRIBL, string_builders=[
        "<value>",
        "<value>",
        "<value>",
    ])

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `id_param`                                                          | *str*                                                               | :heavy_check_mark:                                                  | Unique ID to PATCH                                                  |
| `header_expression`                                                 | *str*                                                               | :heavy_check_mark:                                                  | N/A                                                                 |
| `header_name`                                                       | *str*                                                               | :heavy_check_mark:                                                  | N/A                                                                 |
| `id`                                                                | *str*                                                               | :heavy_check_mark:                                                  | N/A                                                                 |
| `lib`                                                               | [models.CriblLib](../../models/cribllib.md)                         | :heavy_check_mark:                                                  | N/A                                                                 |
| `string_builders`                                                   | List[*str*]                                                         | :heavy_check_mark:                                                  | N/A                                                                 |
| `description`                                                       | *Optional[str]*                                                     | :heavy_minus_sign:                                                  | N/A                                                                 |
| `string_delim`                                                      | *Optional[str]*                                                     | :heavy_minus_sign:                                                  | N/A                                                                 |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.UpdateHmacFunctionByIDResponseBody](../../models/updatehmacfunctionbyidresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |

## delete_hmac_function_by_id

Delete HmacFunction

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

    res = c_client.hmac_functions.delete_hmac_function_by_id(id="<id>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `id`                                                                | *str*                                                               | :heavy_check_mark:                                                  | Unique ID to DELETE                                                 |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.DeleteHmacFunctionByIDResponseBody](../../models/deletehmacfunctionbyidresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |