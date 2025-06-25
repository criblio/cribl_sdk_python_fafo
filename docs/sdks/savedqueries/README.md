# SavedQueries
(*saved_queries*)

## Overview

Actions related to saved queries

### Available Operations

* [list_saved_query](#list_saved_query) - Get a list of SavedQuery objects
* [create_saved_query](#create_saved_query) - Create SavedQuery
* [get_saved_query_by_id](#get_saved_query_by_id) - Get SavedQuery by ID
* [update_saved_query_by_id](#update_saved_query_by_id) - Update SavedQuery
* [delete_saved_query_by_id](#delete_saved_query_by_id) - Delete SavedQuery

## list_saved_query

Get a list of SavedQuery objects

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

    res = cspf_client.saved_queries.list_saved_query()

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.ListSavedQueryResponse](../../models/listsavedqueryresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| errors.Error     | 500              | application/json |
| errors.APIError  | 4XX, 5XX         | \*/\*            |

## create_saved_query

Create SavedQuery

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

    res = cspf_client.saved_queries.create_saved_query(id="<id>", name="<value>", query="<value>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                                 | Type                                                                      | Required                                                                  | Description                                                               |
| ------------------------------------------------------------------------- | ------------------------------------------------------------------------- | ------------------------------------------------------------------------- | ------------------------------------------------------------------------- |
| `id`                                                                      | *str*                                                                     | :heavy_check_mark:                                                        | N/A                                                                       |
| `name`                                                                    | *str*                                                                     | :heavy_check_mark:                                                        | N/A                                                                       |
| `query`                                                                   | *str*                                                                     | :heavy_check_mark:                                                        | N/A                                                                       |
| `chart_config`                                                            | [Optional[models.ChartConfig]](../../models/chartconfig.md)               | :heavy_minus_sign:                                                        | N/A                                                                       |
| `description`                                                             | *Optional[str]*                                                           | :heavy_minus_sign:                                                        | N/A                                                                       |
| `display_username`                                                        | *Optional[str]*                                                           | :heavy_minus_sign:                                                        | N/A                                                                       |
| `earliest`                                                                | *Optional[str]*                                                           | :heavy_minus_sign:                                                        | N/A                                                                       |
| `is_private`                                                              | *Optional[bool]*                                                          | :heavy_minus_sign:                                                        | N/A                                                                       |
| `is_system`                                                               | *Optional[bool]*                                                          | :heavy_minus_sign:                                                        | N/A                                                                       |
| `latest`                                                                  | *Optional[str]*                                                           | :heavy_minus_sign:                                                        | N/A                                                                       |
| `lib`                                                                     | [Optional[models.CriblLib]](../../models/cribllib.md)                     | :heavy_minus_sign:                                                        | N/A                                                                       |
| `resolved_dataset_ids`                                                    | List[*str*]                                                               | :heavy_minus_sign:                                                        | N/A                                                                       |
| `sample_rate`                                                             | *Optional[float]*                                                         | :heavy_minus_sign:                                                        | N/A                                                                       |
| `schedule`                                                                | [Optional[models.SavedQuerySchedule]](../../models/savedqueryschedule.md) | :heavy_minus_sign:                                                        | N/A                                                                       |
| `table_config`                                                            | *Optional[str]*                                                           | :heavy_minus_sign:                                                        | N/A                                                                       |
| `user`                                                                    | *Optional[str]*                                                           | :heavy_minus_sign:                                                        | N/A                                                                       |
| `retries`                                                                 | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)          | :heavy_minus_sign:                                                        | Configuration to override the default retry behavior of the client.       |

### Response

**[models.CreateSavedQueryResponse](../../models/createsavedqueryresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| errors.Error     | 500              | application/json |
| errors.APIError  | 4XX, 5XX         | \*/\*            |

## get_saved_query_by_id

Get SavedQuery by ID

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

    res = cspf_client.saved_queries.get_saved_query_by_id(id="<id>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `id`                                                                | *str*                                                               | :heavy_check_mark:                                                  | Unique ID to GET                                                    |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.GetSavedQueryByIDResponse](../../models/getsavedquerybyidresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| errors.Error     | 500              | application/json |
| errors.APIError  | 4XX, 5XX         | \*/\*            |

## update_saved_query_by_id

Update SavedQuery

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

    res = cspf_client.saved_queries.update_saved_query_by_id(id_param="<value>", id="<id>", name="<value>", query="<value>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                                 | Type                                                                      | Required                                                                  | Description                                                               |
| ------------------------------------------------------------------------- | ------------------------------------------------------------------------- | ------------------------------------------------------------------------- | ------------------------------------------------------------------------- |
| `id_param`                                                                | *str*                                                                     | :heavy_check_mark:                                                        | Unique ID to PATCH                                                        |
| `id`                                                                      | *str*                                                                     | :heavy_check_mark:                                                        | N/A                                                                       |
| `name`                                                                    | *str*                                                                     | :heavy_check_mark:                                                        | N/A                                                                       |
| `query`                                                                   | *str*                                                                     | :heavy_check_mark:                                                        | N/A                                                                       |
| `chart_config`                                                            | [Optional[models.ChartConfig]](../../models/chartconfig.md)               | :heavy_minus_sign:                                                        | N/A                                                                       |
| `description`                                                             | *Optional[str]*                                                           | :heavy_minus_sign:                                                        | N/A                                                                       |
| `display_username`                                                        | *Optional[str]*                                                           | :heavy_minus_sign:                                                        | N/A                                                                       |
| `earliest`                                                                | *Optional[str]*                                                           | :heavy_minus_sign:                                                        | N/A                                                                       |
| `is_private`                                                              | *Optional[bool]*                                                          | :heavy_minus_sign:                                                        | N/A                                                                       |
| `is_system`                                                               | *Optional[bool]*                                                          | :heavy_minus_sign:                                                        | N/A                                                                       |
| `latest`                                                                  | *Optional[str]*                                                           | :heavy_minus_sign:                                                        | N/A                                                                       |
| `lib`                                                                     | [Optional[models.CriblLib]](../../models/cribllib.md)                     | :heavy_minus_sign:                                                        | N/A                                                                       |
| `resolved_dataset_ids`                                                    | List[*str*]                                                               | :heavy_minus_sign:                                                        | N/A                                                                       |
| `sample_rate`                                                             | *Optional[float]*                                                         | :heavy_minus_sign:                                                        | N/A                                                                       |
| `schedule`                                                                | [Optional[models.SavedQuerySchedule]](../../models/savedqueryschedule.md) | :heavy_minus_sign:                                                        | N/A                                                                       |
| `table_config`                                                            | *Optional[str]*                                                           | :heavy_minus_sign:                                                        | N/A                                                                       |
| `user`                                                                    | *Optional[str]*                                                           | :heavy_minus_sign:                                                        | N/A                                                                       |
| `retries`                                                                 | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)          | :heavy_minus_sign:                                                        | Configuration to override the default retry behavior of the client.       |

### Response

**[models.UpdateSavedQueryByIDResponse](../../models/updatesavedquerybyidresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| errors.Error     | 500              | application/json |
| errors.APIError  | 4XX, 5XX         | \*/\*            |

## delete_saved_query_by_id

Delete SavedQuery

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

    res = cspf_client.saved_queries.delete_saved_query_by_id(id="<id>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `id`                                                                | *str*                                                               | :heavy_check_mark:                                                  | Unique ID to DELETE                                                 |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.DeleteSavedQueryByIDResponse](../../models/deletesavedquerybyidresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| errors.Error     | 500              | application/json |
| errors.APIError  | 4XX, 5XX         | \*/\*            |