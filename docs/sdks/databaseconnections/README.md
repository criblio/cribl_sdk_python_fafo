# DatabaseConnections
(*database_connections*)

## Overview

Actions related to Database Connections

### Available Operations

* [get_database_connection_config](#get_database_connection_config) - Get a list of DatabaseConnection objects
* [create_database_connection_config](#create_database_connection_config) - Create DatabaseConnectionConfig
* [get_database_connection_config_by_id](#get_database_connection_config_by_id) - Get DatabaseConnectionConfig by ID
* [update_database_connection_config_by_id](#update_database_connection_config_by_id) - Update DatabaseConnectionConfig
* [delete_database_connection_config_by_id](#delete_database_connection_config_by_id) - Delete DatabaseConnectionConfig
* [create_lib_database_connections_test](#create_lib_database_connections_test) - Test a database connection given a type and connectionString

## get_database_connection_config

Get a list of DatabaseConnection objects

### Example Usage

```python
from cribl import Cribl
import os


with Cribl(
    server_url="https://api.example.com",
    bearer_auth=os.getenv("CRIBL_BEARER_AUTH", ""),
) as c_client:

    res = c_client.database_connections.get_database_connection_config()

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `database_type`                                                     | *Optional[str]*                                                     | :heavy_minus_sign:                                                  | type of database connection                                         |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.GetDatabaseConnectionConfigResponseBody](../../models/getdatabaseconnectionconfigresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |

## create_database_connection_config

Create DatabaseConnectionConfig

### Example Usage

```python
import cribl
from cribl import Cribl
import os


with Cribl(
    server_url="https://api.example.com",
    bearer_auth=os.getenv("CRIBL_BEARER_AUTH", ""),
) as c_client:

    res = c_client.database_connections.create_database_connection_config(auth_type="<value>", database_type=cribl.DatabaseConnectionType.MYSQL, description="jump naughty pip fortunate remand apud yuck conservative nor", id="<id>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                               | Type                                                                    | Required                                                                | Description                                                             |
| ----------------------------------------------------------------------- | ----------------------------------------------------------------------- | ----------------------------------------------------------------------- | ----------------------------------------------------------------------- |
| `auth_type`                                                             | *str*                                                                   | :heavy_check_mark:                                                      | N/A                                                                     |
| `database_type`                                                         | [models.DatabaseConnectionType](../../models/databaseconnectiontype.md) | :heavy_check_mark:                                                      | N/A                                                                     |
| `description`                                                           | *str*                                                                   | :heavy_check_mark:                                                      | N/A                                                                     |
| `id`                                                                    | *str*                                                                   | :heavy_check_mark:                                                      | N/A                                                                     |
| `config_obj`                                                            | *Optional[str]*                                                         | :heavy_minus_sign:                                                      | N/A                                                                     |
| `connection_string`                                                     | *Optional[str]*                                                         | :heavy_minus_sign:                                                      | N/A                                                                     |
| `connection_timeout`                                                    | *Optional[float]*                                                       | :heavy_minus_sign:                                                      | N/A                                                                     |
| `password`                                                              | *Optional[str]*                                                         | :heavy_minus_sign:                                                      | N/A                                                                     |
| `request_timeout`                                                       | *Optional[float]*                                                       | :heavy_minus_sign:                                                      | N/A                                                                     |
| `tags`                                                                  | *Optional[str]*                                                         | :heavy_minus_sign:                                                      | N/A                                                                     |
| `user`                                                                  | *Optional[str]*                                                         | :heavy_minus_sign:                                                      | N/A                                                                     |
| `retries`                                                               | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)        | :heavy_minus_sign:                                                      | Configuration to override the default retry behavior of the client.     |

### Response

**[models.CreateDatabaseConnectionConfigResponseBody](../../models/createdatabaseconnectionconfigresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |

## get_database_connection_config_by_id

Get DatabaseConnectionConfig by ID

### Example Usage

```python
from cribl import Cribl
import os


with Cribl(
    server_url="https://api.example.com",
    bearer_auth=os.getenv("CRIBL_BEARER_AUTH", ""),
) as c_client:

    res = c_client.database_connections.get_database_connection_config_by_id(id="<id>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `id`                                                                | *str*                                                               | :heavy_check_mark:                                                  | Unique ID to GET                                                    |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.GetDatabaseConnectionConfigByIDResponseBody](../../models/getdatabaseconnectionconfigbyidresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |

## update_database_connection_config_by_id

Update DatabaseConnectionConfig

### Example Usage

```python
import cribl
from cribl import Cribl
import os


with Cribl(
    server_url="https://api.example.com",
    bearer_auth=os.getenv("CRIBL_BEARER_AUTH", ""),
) as c_client:

    res = c_client.database_connections.update_database_connection_config_by_id(id_param="<value>", auth_type="<value>", database_type=cribl.DatabaseConnectionType.ORACLE, description="orientate without internal", id="<id>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                               | Type                                                                    | Required                                                                | Description                                                             |
| ----------------------------------------------------------------------- | ----------------------------------------------------------------------- | ----------------------------------------------------------------------- | ----------------------------------------------------------------------- |
| `id_param`                                                              | *str*                                                                   | :heavy_check_mark:                                                      | Unique ID to PATCH                                                      |
| `auth_type`                                                             | *str*                                                                   | :heavy_check_mark:                                                      | N/A                                                                     |
| `database_type`                                                         | [models.DatabaseConnectionType](../../models/databaseconnectiontype.md) | :heavy_check_mark:                                                      | N/A                                                                     |
| `description`                                                           | *str*                                                                   | :heavy_check_mark:                                                      | N/A                                                                     |
| `id`                                                                    | *str*                                                                   | :heavy_check_mark:                                                      | N/A                                                                     |
| `config_obj`                                                            | *Optional[str]*                                                         | :heavy_minus_sign:                                                      | N/A                                                                     |
| `connection_string`                                                     | *Optional[str]*                                                         | :heavy_minus_sign:                                                      | N/A                                                                     |
| `connection_timeout`                                                    | *Optional[float]*                                                       | :heavy_minus_sign:                                                      | N/A                                                                     |
| `password`                                                              | *Optional[str]*                                                         | :heavy_minus_sign:                                                      | N/A                                                                     |
| `request_timeout`                                                       | *Optional[float]*                                                       | :heavy_minus_sign:                                                      | N/A                                                                     |
| `tags`                                                                  | *Optional[str]*                                                         | :heavy_minus_sign:                                                      | N/A                                                                     |
| `user`                                                                  | *Optional[str]*                                                         | :heavy_minus_sign:                                                      | N/A                                                                     |
| `retries`                                                               | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)        | :heavy_minus_sign:                                                      | Configuration to override the default retry behavior of the client.     |

### Response

**[models.UpdateDatabaseConnectionConfigByIDResponseBody](../../models/updatedatabaseconnectionconfigbyidresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |

## delete_database_connection_config_by_id

Delete DatabaseConnectionConfig

### Example Usage

```python
from cribl import Cribl
import os


with Cribl(
    server_url="https://api.example.com",
    bearer_auth=os.getenv("CRIBL_BEARER_AUTH", ""),
) as c_client:

    res = c_client.database_connections.delete_database_connection_config_by_id(id="<id>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `id`                                                                | *str*                                                               | :heavy_check_mark:                                                  | Unique ID to DELETE                                                 |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.DeleteDatabaseConnectionConfigByIDResponseBody](../../models/deletedatabaseconnectionconfigbyidresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |

## create_lib_database_connections_test

Test a database connection given a type and connectionString

### Example Usage

```python
from cribl import Cribl
import os


with Cribl(
    server_url="https://api.example.com",
    bearer_auth=os.getenv("CRIBL_BEARER_AUTH", ""),
) as c_client:

    res = c_client.database_connections.create_lib_database_connections_test(auth_type="<value>", database_type="<value>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `auth_type`                                                         | *str*                                                               | :heavy_check_mark:                                                  | N/A                                                                 |
| `database_type`                                                     | *str*                                                               | :heavy_check_mark:                                                  | N/A                                                                 |
| `config_obj`                                                        | *Optional[str]*                                                     | :heavy_minus_sign:                                                  | N/A                                                                 |
| `connection_string`                                                 | *Optional[str]*                                                     | :heavy_minus_sign:                                                  | N/A                                                                 |
| `connection_timeout`                                                | *Optional[float]*                                                   | :heavy_minus_sign:                                                  | N/A                                                                 |
| `password`                                                          | *Optional[str]*                                                     | :heavy_minus_sign:                                                  | N/A                                                                 |
| `text_secret`                                                       | *Optional[str]*                                                     | :heavy_minus_sign:                                                  | N/A                                                                 |
| `user`                                                              | *Optional[str]*                                                     | :heavy_minus_sign:                                                  | N/A                                                                 |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.CreateLibDatabaseConnectionsTestResponseBody](../../models/createlibdatabaseconnectionstestresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |