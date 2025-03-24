# AppscopeConfigs
(*appscope_configs*)

## Overview

Actions related to Appscope Configs

### Available Operations

* [list_appscope_lib_entry](#list_appscope_lib_entry) - Get a list of AppscopeLibEntry objects
* [create_appscope_lib_entry](#create_appscope_lib_entry) - Create AppscopeLibEntry
* [get_appscope_lib_entry_by_id](#get_appscope_lib_entry_by_id) - Get AppscopeLibEntry by ID
* [update_appscope_lib_entry_by_id](#update_appscope_lib_entry_by_id) - Update AppscopeLibEntry
* [delete_appscope_lib_entry_by_id](#delete_appscope_lib_entry_by_id) - Delete AppscopeLibEntry

## list_appscope_lib_entry

Get a list of AppscopeLibEntry objects

### Example Usage

```python
from cribl import Cribl
import os


with Cribl(
    bearer_auth=os.getenv("CRIBL_BEARER_AUTH", ""),
) as c_client:

    res = c_client.appscope_configs.list_appscope_lib_entry()

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.ListAppscopeLibEntryResponseBody](../../models/listappscopelibentryresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |

## create_appscope_lib_entry

Create AppscopeLibEntry

### Example Usage

```python
import cribl
from cribl import Cribl
import os


with Cribl(
    bearer_auth=os.getenv("CRIBL_BEARER_AUTH", ""),
) as c_client:

    res = c_client.appscope_configs.create_appscope_lib_entry(config=cribl.AppscopeConfigWithCustom(), description="for sarong profitable hm", id="<id>", lib=cribl.CriblLib.CRIBL_CUSTOM)

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                                   | Type                                                                        | Required                                                                    | Description                                                                 |
| --------------------------------------------------------------------------- | --------------------------------------------------------------------------- | --------------------------------------------------------------------------- | --------------------------------------------------------------------------- |
| `config`                                                                    | [models.AppscopeConfigWithCustom](../../models/appscopeconfigwithcustom.md) | :heavy_check_mark:                                                          | N/A                                                                         |
| `description`                                                               | *str*                                                                       | :heavy_check_mark:                                                          | N/A                                                                         |
| `id`                                                                        | *str*                                                                       | :heavy_check_mark:                                                          | N/A                                                                         |
| `lib`                                                                       | [models.CriblLib](../../models/cribllib.md)                                 | :heavy_check_mark:                                                          | N/A                                                                         |
| `tags`                                                                      | *Optional[str]*                                                             | :heavy_minus_sign:                                                          | N/A                                                                         |
| `retries`                                                                   | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)            | :heavy_minus_sign:                                                          | Configuration to override the default retry behavior of the client.         |

### Response

**[models.CreateAppscopeLibEntryResponseBody](../../models/createappscopelibentryresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |

## get_appscope_lib_entry_by_id

Get AppscopeLibEntry by ID

### Example Usage

```python
from cribl import Cribl
import os


with Cribl(
    bearer_auth=os.getenv("CRIBL_BEARER_AUTH", ""),
) as c_client:

    res = c_client.appscope_configs.get_appscope_lib_entry_by_id(id="<id>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `id`                                                                | *str*                                                               | :heavy_check_mark:                                                  | Unique ID to GET                                                    |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.GetAppscopeLibEntryByIDResponseBody](../../models/getappscopelibentrybyidresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |

## update_appscope_lib_entry_by_id

Update AppscopeLibEntry

### Example Usage

```python
import cribl
from cribl import Cribl
import os


with Cribl(
    bearer_auth=os.getenv("CRIBL_BEARER_AUTH", ""),
) as c_client:

    res = c_client.appscope_configs.update_appscope_lib_entry_by_id(id_param="<value>", config=cribl.AppscopeConfigWithCustom(), description="avow tighten zowie ouch", id="<id>", lib=cribl.CriblLib.CRIBL_CUSTOM)

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                                   | Type                                                                        | Required                                                                    | Description                                                                 |
| --------------------------------------------------------------------------- | --------------------------------------------------------------------------- | --------------------------------------------------------------------------- | --------------------------------------------------------------------------- |
| `id_param`                                                                  | *str*                                                                       | :heavy_check_mark:                                                          | Unique ID to PATCH                                                          |
| `config`                                                                    | [models.AppscopeConfigWithCustom](../../models/appscopeconfigwithcustom.md) | :heavy_check_mark:                                                          | N/A                                                                         |
| `description`                                                               | *str*                                                                       | :heavy_check_mark:                                                          | N/A                                                                         |
| `id`                                                                        | *str*                                                                       | :heavy_check_mark:                                                          | N/A                                                                         |
| `lib`                                                                       | [models.CriblLib](../../models/cribllib.md)                                 | :heavy_check_mark:                                                          | N/A                                                                         |
| `tags`                                                                      | *Optional[str]*                                                             | :heavy_minus_sign:                                                          | N/A                                                                         |
| `retries`                                                                   | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)            | :heavy_minus_sign:                                                          | Configuration to override the default retry behavior of the client.         |

### Response

**[models.UpdateAppscopeLibEntryByIDResponseBody](../../models/updateappscopelibentrybyidresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |

## delete_appscope_lib_entry_by_id

Delete AppscopeLibEntry

### Example Usage

```python
from cribl import Cribl
import os


with Cribl(
    bearer_auth=os.getenv("CRIBL_BEARER_AUTH", ""),
) as c_client:

    res = c_client.appscope_configs.delete_appscope_lib_entry_by_id(id="<id>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `id`                                                                | *str*                                                               | :heavy_check_mark:                                                  | Unique ID to DELETE                                                 |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.DeleteAppscopeLibEntryByIDResponseBody](../../models/deleteappscopelibentrybyidresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |