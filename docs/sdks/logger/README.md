# Logger
(*logger*)

## Overview

Actions related to Logger

### Available Operations

* [list_logger_config](#list_logger_config) - Get a list of LoggerConfig objects
* [get_logger_config_by_id](#get_logger_config_by_id) - Get LoggerConfig by ID
* [update_logger_config_by_id](#update_logger_config_by_id) - Update LoggerConfig
* [delete_logger_config_by_id](#delete_logger_config_by_id) - Delete LoggerConfig

## list_logger_config

Get a list of LoggerConfig objects

### Example Usage

```python
from cribl import Cribl
import os


with Cribl(
    server_url="https://api.example.com",
    bearer_auth=os.getenv("CRIBL_BEARER_AUTH", ""),
) as c_client:

    res = c_client.logger.list_logger_config()

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.ListLoggerConfigResponseBody](../../models/listloggerconfigresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |

## get_logger_config_by_id

Get LoggerConfig by ID

### Example Usage

```python
from cribl import Cribl
import os


with Cribl(
    server_url="https://api.example.com",
    bearer_auth=os.getenv("CRIBL_BEARER_AUTH", ""),
) as c_client:

    res = c_client.logger.get_logger_config_by_id(id="<id>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `id`                                                                | *str*                                                               | :heavy_check_mark:                                                  | Unique ID to GET                                                    |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.GetLoggerConfigByIDResponseBody](../../models/getloggerconfigbyidresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |

## update_logger_config_by_id

Update LoggerConfig

### Example Usage

```python
from cribl import Cribl
import os


with Cribl(
    server_url="https://api.example.com",
    bearer_auth=os.getenv("CRIBL_BEARER_AUTH", ""),
) as c_client:

    res = c_client.logger.update_logger_config_by_id(id_param="<value>", channels=[

    ], id="<id>", limit_rate=3458.88, max_size_bytes=6138.31, redact_fields=[
        "<value>",
        "<value>",
        "<value>",
    ], redact_label="<value>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `id_param`                                                          | *str*                                                               | :heavy_check_mark:                                                  | Unique ID to PATCH                                                  |
| `channels`                                                          | List[[models.LoggerEntry](../../models/loggerentry.md)]             | :heavy_check_mark:                                                  | N/A                                                                 |
| `id`                                                                | *str*                                                               | :heavy_check_mark:                                                  | N/A                                                                 |
| `limit_rate`                                                        | *float*                                                             | :heavy_check_mark:                                                  | N/A                                                                 |
| `max_size_bytes`                                                    | *float*                                                             | :heavy_check_mark:                                                  | N/A                                                                 |
| `redact_fields`                                                     | List[*str*]                                                         | :heavy_check_mark:                                                  | N/A                                                                 |
| `redact_label`                                                      | *str*                                                               | :heavy_check_mark:                                                  | N/A                                                                 |
| `default_redact_fields`                                             | List[*str*]                                                         | :heavy_minus_sign:                                                  | N/A                                                                 |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.UpdateLoggerConfigByIDResponseBody](../../models/updateloggerconfigbyidresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |

## delete_logger_config_by_id

Delete LoggerConfig

### Example Usage

```python
from cribl import Cribl
import os


with Cribl(
    server_url="https://api.example.com",
    bearer_auth=os.getenv("CRIBL_BEARER_AUTH", ""),
) as c_client:

    res = c_client.logger.delete_logger_config_by_id(id="<id>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `id`                                                                | *str*                                                               | :heavy_check_mark:                                                  | Unique ID to DELETE                                                 |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.DeleteLoggerConfigByIDResponseBody](../../models/deleteloggerconfigbyidresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |