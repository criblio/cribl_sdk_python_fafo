# Parquetschemas
(*parquetschemas*)

## Overview

Actions related to Parquet schemas

### Available Operations

* [list_schema](#list_schema) - Get a list of Schema objects
* [create_schema](#create_schema) - Create Schema
* [get_schema_by_id](#get_schema_by_id) - Get Schema by ID
* [update_schema_by_id](#update_schema_by_id) - Update Schema
* [delete_schema_by_id](#delete_schema_by_id) - Delete Schema

## list_schema

Get a list of Schema objects

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

    res = cspf_client.parquetschemas.list_schema()

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.ListSchemaResponse](../../models/listschemaresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| errors.Error     | 500              | application/json |
| errors.APIError  | 4XX, 5XX         | \*/\*            |

## create_schema

Create Schema

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

    res = cspf_client.parquetschemas.create_schema(id="<id>", schema="<value>", additional_properties={

    })

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `id`                                                                | *str*                                                               | :heavy_check_mark:                                                  | N/A                                                                 |
| `schema_`                                                           | *str*                                                               | :heavy_check_mark:                                                  | JSON schema matching standards of draft version 2019-09             |
| `description`                                                       | *Optional[str]*                                                     | :heavy_minus_sign:                                                  | N/A                                                                 |
| `additional_properties`                                             | Dict[str, *Any*]                                                    | :heavy_minus_sign:                                                  | N/A                                                                 |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.CreateSchemaResponse](../../models/createschemaresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| errors.Error     | 500              | application/json |
| errors.APIError  | 4XX, 5XX         | \*/\*            |

## get_schema_by_id

Get Schema by ID

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

    res = cspf_client.parquetschemas.get_schema_by_id(id="<id>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `id`                                                                | *str*                                                               | :heavy_check_mark:                                                  | Unique ID to GET                                                    |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.GetSchemaByIDResponse](../../models/getschemabyidresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| errors.Error     | 500              | application/json |
| errors.APIError  | 4XX, 5XX         | \*/\*            |

## update_schema_by_id

Update Schema

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

    res = cspf_client.parquetschemas.update_schema_by_id(id_param="<value>", id="<id>", schema="<value>", additional_properties={

    })

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `id_param`                                                          | *str*                                                               | :heavy_check_mark:                                                  | Unique ID to PATCH                                                  |
| `id`                                                                | *str*                                                               | :heavy_check_mark:                                                  | N/A                                                                 |
| `schema_`                                                           | *str*                                                               | :heavy_check_mark:                                                  | JSON schema matching standards of draft version 2019-09             |
| `description`                                                       | *Optional[str]*                                                     | :heavy_minus_sign:                                                  | N/A                                                                 |
| `additional_properties`                                             | Dict[str, *Any*]                                                    | :heavy_minus_sign:                                                  | N/A                                                                 |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.UpdateSchemaByIDResponse](../../models/updateschemabyidresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| errors.Error     | 500              | application/json |
| errors.APIError  | 4XX, 5XX         | \*/\*            |

## delete_schema_by_id

Delete Schema

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

    res = cspf_client.parquetschemas.delete_schema_by_id(id="<id>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `id`                                                                | *str*                                                               | :heavy_check_mark:                                                  | Unique ID to DELETE                                                 |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.DeleteSchemaByIDResponse](../../models/deleteschemabyidresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| errors.Error     | 500              | application/json |
| errors.APIError  | 4XX, 5XX         | \*/\*            |