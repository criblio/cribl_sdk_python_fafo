# GlobalVariables
(*global_variables*)

## Overview

Actions related to Global Variables

### Available Operations

* [get_global_variable](#get_global_variable) - List all GlobalVars with references
* [create_global_variable](#create_global_variable) - Create Global Variable
* [get_global_variable_by_id](#get_global_variable_by_id) - Get Global Variable by ID
* [update_global_variable_by_id](#update_global_variable_by_id) - Update Global Variable
* [delete_global_variable_by_id](#delete_global_variable_by_id) - Delete Global Variable
* [get_global_variable_lib_vars_by_pack](#get_global_variable_lib_vars_by_pack) - List all GlobalVars with references within a Pack
* [create_global_variable_lib_vars_by_pack](#create_global_variable_lib_vars_by_pack) - Create Global Variable within a Pack
* [get_global_variable_lib_vars_by_pack_and_id](#get_global_variable_lib_vars_by_pack_and_id) - Get Global Variable by ID within a Pack
* [update_global_variable_lib_vars_by_pack_and_id](#update_global_variable_lib_vars_by_pack_and_id) - Update Global Variable within a Pack
* [delete_global_variable_lib_vars_by_pack_and_id](#delete_global_variable_lib_vars_by_pack_and_id) - Delete Global Variable within a Pack

## get_global_variable

List all GlobalVars with references

### Example Usage

```python
from cribl import Cribl
import os


with Cribl(
    server_url="https://api.example.com",
    bearer_auth=os.getenv("CRIBL_BEARER_AUTH", ""),
) as c_client:

    res = c_client.global_variables.get_global_variable()

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `with_`                                                             | *Optional[str]*                                                     | :heavy_minus_sign:                                                  | Pass "refs" to include references to fields the variable is used in |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.GetGlobalVariableResponseBody](../../models/getglobalvariableresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |

## create_global_variable

Create Global Variable

### Example Usage

```python
from cribl import Cribl
import os


with Cribl(
    server_url="https://api.example.com",
    bearer_auth=os.getenv("CRIBL_BEARER_AUTH", ""),
) as c_client:

    res = c_client.global_variables.create_global_variable(id="<id>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `id`                                                                | *str*                                                               | :heavy_check_mark:                                                  | Global variable name.                                               |
| `lib`                                                               | *Optional[str]*                                                     | :heavy_minus_sign:                                                  | N/A                                                                 |
| `description`                                                       | *Optional[str]*                                                     | :heavy_minus_sign:                                                  | Brief description of this variable. Optional.                       |
| `type`                                                              | [Optional[models.GlobalVarType]](../../models/globalvartype.md)     | :heavy_minus_sign:                                                  | Type of variable                                                    |
| `value`                                                             | *Optional[str]*                                                     | :heavy_minus_sign:                                                  | Value of variable                                                   |
| `tags`                                                              | *Optional[str]*                                                     | :heavy_minus_sign:                                                  | One or more tags related to this variable. Optional.                |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.CreateGlobalVariableResponseBody](../../models/createglobalvariableresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |

## get_global_variable_by_id

Get Global Variable by ID

### Example Usage

```python
from cribl import Cribl
import os


with Cribl(
    server_url="https://api.example.com",
    bearer_auth=os.getenv("CRIBL_BEARER_AUTH", ""),
) as c_client:

    res = c_client.global_variables.get_global_variable_by_id(id="<id>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `id`                                                                | *str*                                                               | :heavy_check_mark:                                                  | Unique ID to GET                                                    |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.GetGlobalVariableByIDResponseBody](../../models/getglobalvariablebyidresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |

## update_global_variable_by_id

Update Global Variable

### Example Usage

```python
from cribl import Cribl
import os


with Cribl(
    server_url="https://api.example.com",
    bearer_auth=os.getenv("CRIBL_BEARER_AUTH", ""),
) as c_client:

    res = c_client.global_variables.update_global_variable_by_id(id_param="<value>", id="<id>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `id_param`                                                          | *str*                                                               | :heavy_check_mark:                                                  | Unique ID to PATCH                                                  |
| `id`                                                                | *str*                                                               | :heavy_check_mark:                                                  | Global variable name.                                               |
| `lib`                                                               | *Optional[str]*                                                     | :heavy_minus_sign:                                                  | N/A                                                                 |
| `description`                                                       | *Optional[str]*                                                     | :heavy_minus_sign:                                                  | Brief description of this variable. Optional.                       |
| `type`                                                              | [Optional[models.GlobalVarType]](../../models/globalvartype.md)     | :heavy_minus_sign:                                                  | Type of variable                                                    |
| `value`                                                             | *Optional[str]*                                                     | :heavy_minus_sign:                                                  | Value of variable                                                   |
| `tags`                                                              | *Optional[str]*                                                     | :heavy_minus_sign:                                                  | One or more tags related to this variable. Optional.                |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.UpdateGlobalVariableByIDResponseBody](../../models/updateglobalvariablebyidresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |

## delete_global_variable_by_id

Delete Global Variable

### Example Usage

```python
from cribl import Cribl
import os


with Cribl(
    server_url="https://api.example.com",
    bearer_auth=os.getenv("CRIBL_BEARER_AUTH", ""),
) as c_client:

    res = c_client.global_variables.delete_global_variable_by_id(id="<id>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `id`                                                                | *str*                                                               | :heavy_check_mark:                                                  | Unique ID to DELETE                                                 |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.DeleteGlobalVariableByIDResponseBody](../../models/deleteglobalvariablebyidresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |

## get_global_variable_lib_vars_by_pack

List all GlobalVars with references within a Pack

### Example Usage

```python
from cribl import Cribl
import os


with Cribl(
    server_url="https://api.example.com",
    bearer_auth=os.getenv("CRIBL_BEARER_AUTH", ""),
) as c_client:

    res = c_client.global_variables.get_global_variable_lib_vars_by_pack(pack="<value>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                                    | Type                                                                         | Required                                                                     | Description                                                                  |
| ---------------------------------------------------------------------------- | ---------------------------------------------------------------------------- | ---------------------------------------------------------------------------- | ---------------------------------------------------------------------------- |
| `pack`                                                                       | *str*                                                                        | :heavy_check_mark:                                                           | pack ID to GET                                                               |
| `with_`                                                                      | *Optional[str]*                                                              | :heavy_minus_sign:                                                           | Pass "refs" to include references to fields the variable is used in for pack |
| `retries`                                                                    | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)             | :heavy_minus_sign:                                                           | Configuration to override the default retry behavior of the client.          |

### Response

**[models.GetGlobalVariableLibVarsByPackResponseBody](../../models/getglobalvariablelibvarsbypackresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |

## create_global_variable_lib_vars_by_pack

Create Global Variable within a Pack

### Example Usage

```python
from cribl import Cribl
import os


with Cribl(
    server_url="https://api.example.com",
    bearer_auth=os.getenv("CRIBL_BEARER_AUTH", ""),
) as c_client:

    res = c_client.global_variables.create_global_variable_lib_vars_by_pack(pack="<value>", id="<id>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `pack`                                                              | *str*                                                               | :heavy_check_mark:                                                  | pack ID to POST                                                     |
| `id`                                                                | *str*                                                               | :heavy_check_mark:                                                  | Global variable name.                                               |
| `lib`                                                               | *Optional[str]*                                                     | :heavy_minus_sign:                                                  | N/A                                                                 |
| `description`                                                       | *Optional[str]*                                                     | :heavy_minus_sign:                                                  | Brief description of this variable. Optional.                       |
| `type`                                                              | [Optional[models.GlobalVarType]](../../models/globalvartype.md)     | :heavy_minus_sign:                                                  | Type of variable                                                    |
| `value`                                                             | *Optional[str]*                                                     | :heavy_minus_sign:                                                  | Value of variable                                                   |
| `tags`                                                              | *Optional[str]*                                                     | :heavy_minus_sign:                                                  | One or more tags related to this variable. Optional.                |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.CreateGlobalVariableLibVarsByPackResponseBody](../../models/createglobalvariablelibvarsbypackresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |

## get_global_variable_lib_vars_by_pack_and_id

Get Global Variable by ID within a Pack

### Example Usage

```python
from cribl import Cribl
import os


with Cribl(
    server_url="https://api.example.com",
    bearer_auth=os.getenv("CRIBL_BEARER_AUTH", ""),
) as c_client:

    res = c_client.global_variables.get_global_variable_lib_vars_by_pack_and_id(id="<id>", pack="<value>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `id`                                                                | *str*                                                               | :heavy_check_mark:                                                  | Unique ID to GET for pack                                           |
| `pack`                                                              | *str*                                                               | :heavy_check_mark:                                                  | pack ID to GET                                                      |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.GetGlobalVariableLibVarsByPackAndIDResponseBody](../../models/getglobalvariablelibvarsbypackandidresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |

## update_global_variable_lib_vars_by_pack_and_id

Update Global Variable within a Pack

### Example Usage

```python
from cribl import Cribl
import os


with Cribl(
    server_url="https://api.example.com",
    bearer_auth=os.getenv("CRIBL_BEARER_AUTH", ""),
) as c_client:

    res = c_client.global_variables.update_global_variable_lib_vars_by_pack_and_id(id_param="<value>", pack="<value>", id="<id>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `id_param`                                                          | *str*                                                               | :heavy_check_mark:                                                  | Unique ID to PATCH for pack                                         |
| `pack`                                                              | *str*                                                               | :heavy_check_mark:                                                  | pack ID to PATCH                                                    |
| `id`                                                                | *str*                                                               | :heavy_check_mark:                                                  | Global variable name.                                               |
| `lib`                                                               | *Optional[str]*                                                     | :heavy_minus_sign:                                                  | N/A                                                                 |
| `description`                                                       | *Optional[str]*                                                     | :heavy_minus_sign:                                                  | Brief description of this variable. Optional.                       |
| `type`                                                              | [Optional[models.GlobalVarType]](../../models/globalvartype.md)     | :heavy_minus_sign:                                                  | Type of variable                                                    |
| `value`                                                             | *Optional[str]*                                                     | :heavy_minus_sign:                                                  | Value of variable                                                   |
| `tags`                                                              | *Optional[str]*                                                     | :heavy_minus_sign:                                                  | One or more tags related to this variable. Optional.                |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.UpdateGlobalVariableLibVarsByPackAndIDResponseBody](../../models/updateglobalvariablelibvarsbypackandidresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |

## delete_global_variable_lib_vars_by_pack_and_id

Delete Global Variable within a Pack

### Example Usage

```python
from cribl import Cribl
import os


with Cribl(
    server_url="https://api.example.com",
    bearer_auth=os.getenv("CRIBL_BEARER_AUTH", ""),
) as c_client:

    res = c_client.global_variables.delete_global_variable_lib_vars_by_pack_and_id(id="<id>", pack="<value>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `id`                                                                | *str*                                                               | :heavy_check_mark:                                                  | Unique ID to DELETE for pack                                        |
| `pack`                                                              | *str*                                                               | :heavy_check_mark:                                                  | pack ID to DELETE                                                   |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.DeleteGlobalVariableLibVarsByPackAndIDResponseBody](../../models/deleteglobalvariablelibvarsbypackandidresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |