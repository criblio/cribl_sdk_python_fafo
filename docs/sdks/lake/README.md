# Lake
(*lake*)

## Overview

Actions related to Lake

### Available Operations

* [create_cribl_lake_dataset_by_lake_id](#create_cribl_lake_dataset_by_lake_id) - Create a Dataset in the specified Lake
* [get_cribl_lake_dataset_by_lake_id](#get_cribl_lake_dataset_by_lake_id) - Get the list of Dataset contained in the specified Lake
* [delete_cribl_lake_dataset_by_lake_id_and_id](#delete_cribl_lake_dataset_by_lake_id_and_id) - Delete a Dataset in the specified Lake
* [get_cribl_lake_dataset_by_lake_id_and_id](#get_cribl_lake_dataset_by_lake_id_and_id) - Get a Dataset in the specified Lake
* [update_cribl_lake_dataset_by_lake_id_and_id](#update_cribl_lake_dataset_by_lake_id_and_id) - Update a Dataset in the specified Lake

## create_cribl_lake_dataset_by_lake_id

Create a Dataset in the specified Lake

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

    res = c_client.lake.create_cribl_lake_dataset_by_lake_id(lake_id="<id>", bucket_name="<value>", id="<id>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                                           | Type                                                                                | Required                                                                            | Description                                                                         |
| ----------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------- |
| `lake_id`                                                                           | *str*                                                                               | :heavy_check_mark:                                                                  | lake id that contains the Datasets                                                  |
| `bucket_name`                                                                       | *str*                                                                               | :heavy_check_mark:                                                                  | N/A                                                                                 |
| `id`                                                                                | *str*                                                                               | :heavy_check_mark:                                                                  | N/A                                                                                 |
| `accelerated_fields`                                                                | List[*str*]                                                                         | :heavy_minus_sign:                                                                  | N/A                                                                                 |
| `cache_connection`                                                                  | [Optional[models.CacheConnection]](../../models/cacheconnection.md)                 | :heavy_minus_sign:                                                                  | N/A                                                                                 |
| `deletion_started_at`                                                               | *Optional[float]*                                                                   | :heavy_minus_sign:                                                                  | N/A                                                                                 |
| `description`                                                                       | *Optional[str]*                                                                     | :heavy_minus_sign:                                                                  | N/A                                                                                 |
| `format_`                                                                           | [Optional[models.CriblLakeDatasetFormat]](../../models/cribllakedatasetformat.md)   | :heavy_minus_sign:                                                                  | N/A                                                                                 |
| `retention_period_in_days`                                                          | *Optional[float]*                                                                   | :heavy_minus_sign:                                                                  | N/A                                                                                 |
| `search_config`                                                                     | [Optional[models.LakeDatasetSearchConfig]](../../models/lakedatasetsearchconfig.md) | :heavy_minus_sign:                                                                  | N/A                                                                                 |
| `view_name`                                                                         | *Optional[str]*                                                                     | :heavy_minus_sign:                                                                  | N/A                                                                                 |
| `retries`                                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)                    | :heavy_minus_sign:                                                                  | Configuration to override the default retry behavior of the client.                 |

### Response

**[models.CreateCriblLakeDatasetByLakeIDResponseBody](../../models/createcribllakedatasetbylakeidresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |

## get_cribl_lake_dataset_by_lake_id

Get the list of Dataset contained in the specified Lake

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

    res = c_client.lake.get_cribl_lake_dataset_by_lake_id(lake_id="<id>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `lake_id`                                                           | *str*                                                               | :heavy_check_mark:                                                  | lake id that contains the Datasets                                  |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.GetCriblLakeDatasetByLakeIDResponseBody](../../models/getcribllakedatasetbylakeidresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |

## delete_cribl_lake_dataset_by_lake_id_and_id

Delete a Dataset in the specified Lake

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

    res = c_client.lake.delete_cribl_lake_dataset_by_lake_id_and_id(lake_id="<id>", id="<id>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `lake_id`                                                           | *str*                                                               | :heavy_check_mark:                                                  | lake id that contains the Datasets                                  |
| `id`                                                                | *str*                                                               | :heavy_check_mark:                                                  | dataset id to delete                                                |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.DeleteCriblLakeDatasetByLakeIDAndIDResponseBody](../../models/deletecribllakedatasetbylakeidandidresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |

## get_cribl_lake_dataset_by_lake_id_and_id

Get a Dataset in the specified Lake

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

    res = c_client.lake.get_cribl_lake_dataset_by_lake_id_and_id(lake_id="<id>", id="<id>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `lake_id`                                                           | *str*                                                               | :heavy_check_mark:                                                  | lake id that contains the Datasets                                  |
| `id`                                                                | *str*                                                               | :heavy_check_mark:                                                  | dataset id to get                                                   |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.GetCriblLakeDatasetByLakeIDAndIDResponseBody](../../models/getcribllakedatasetbylakeidandidresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |

## update_cribl_lake_dataset_by_lake_id_and_id

Update a Dataset in the specified Lake

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

    res = c_client.lake.update_cribl_lake_dataset_by_lake_id_and_id(lake_id="<id>", id_param="<value>", bucket_name="<value>", id="<id>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                                           | Type                                                                                | Required                                                                            | Description                                                                         |
| ----------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------- |
| `lake_id`                                                                           | *str*                                                                               | :heavy_check_mark:                                                                  | lake id that contains the Datasets                                                  |
| `id_param`                                                                          | *str*                                                                               | :heavy_check_mark:                                                                  | dataset id to update                                                                |
| `bucket_name`                                                                       | *str*                                                                               | :heavy_check_mark:                                                                  | N/A                                                                                 |
| `id`                                                                                | *str*                                                                               | :heavy_check_mark:                                                                  | N/A                                                                                 |
| `accelerated_fields`                                                                | List[*str*]                                                                         | :heavy_minus_sign:                                                                  | N/A                                                                                 |
| `cache_connection`                                                                  | [Optional[models.CacheConnection]](../../models/cacheconnection.md)                 | :heavy_minus_sign:                                                                  | N/A                                                                                 |
| `deletion_started_at`                                                               | *Optional[float]*                                                                   | :heavy_minus_sign:                                                                  | N/A                                                                                 |
| `description`                                                                       | *Optional[str]*                                                                     | :heavy_minus_sign:                                                                  | N/A                                                                                 |
| `format_`                                                                           | [Optional[models.CriblLakeDatasetFormat]](../../models/cribllakedatasetformat.md)   | :heavy_minus_sign:                                                                  | N/A                                                                                 |
| `retention_period_in_days`                                                          | *Optional[float]*                                                                   | :heavy_minus_sign:                                                                  | N/A                                                                                 |
| `search_config`                                                                     | [Optional[models.LakeDatasetSearchConfig]](../../models/lakedatasetsearchconfig.md) | :heavy_minus_sign:                                                                  | N/A                                                                                 |
| `view_name`                                                                         | *Optional[str]*                                                                     | :heavy_minus_sign:                                                                  | N/A                                                                                 |
| `retries`                                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)                    | :heavy_minus_sign:                                                                  | Configuration to override the default retry behavior of the client.                 |

### Response

**[models.UpdateCriblLakeDatasetByLakeIDAndIDResponseBody](../../models/updatecribllakedatasetbylakeidandidresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |