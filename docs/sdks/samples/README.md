# Samples
(*samples*)

## Overview

Actions related to samples

### Available Operations

* [create_system_projects_subscriptions_capture_by_group_id_and_subscription_id](#create_system_projects_subscriptions_capture_by_group_id_and_subscription_id) - Capture live incoming data from a particular Project and Subscription at the Subscription
* [create_system_projects_capture_by_group_id_and_project_id](#create_system_projects_capture_by_group_id_and_project_id) - Capture live incoming data from a particular Project and Subscription at the Destination
* [create_system_projects_preview_by_group_id_and_project_id](#create_system_projects_preview_by_group_id_and_project_id) - Sends sample events through a Pipeline  for specified Project and returns the results
* [list_data_sample](#list_data_sample) - Get a list of DataSample objects
* [create_data_sample](#create_data_sample) - Create DataSample
* [get_data_sample_by_id](#get_data_sample_by_id) - Get DataSample by ID
* [update_data_sample_by_id](#update_data_sample_by_id) - Update DataSample
* [delete_data_sample_by_id](#delete_data_sample_by_id) - Delete DataSample
* [get_data_sample_content_by_id](#get_data_sample_content_by_id) - Get sample content by ID
* [create_system_capture](#create_system_capture) - Capture live incoming data
* [create_system_projects_capture_by_project_id](#create_system_projects_capture_by_project_id) - Capture live incoming data from a particular project and subscription at the destination
* [create_system_projects_subscriptions_capture_by_project_id_and_subscription_id](#create_system_projects_subscriptions_capture_by_project_id_and_subscription_id) - Capture live incoming data from a particular project and subscription at the subscription
* [create_preview](#create_preview) - Sends sample events through a pipeline and returns the results

## create_system_projects_subscriptions_capture_by_group_id_and_subscription_id

Capture live incoming data from a particular Project and Subscription at the Subscription

### Example Usage

```python
from cribl import Cribl
import os


with Cribl(
    server_url="https://api.example.com",
    bearer_auth=os.getenv("CRIBL_BEARER_AUTH", ""),
) as c_client:

    res = c_client.samples.create_system_projects_subscriptions_capture_by_group_id_and_subscription_id(group_id="<id>", project_id="<id>", subscription_id="<id>", duration=4923.8, filter_="<value>", level=3160.52, max_events=7440.79)

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `group_id`                                                          | *str*                                                               | :heavy_check_mark:                                                  | Group Id                                                            |
| `project_id`                                                        | *str*                                                               | :heavy_check_mark:                                                  | Project Id                                                          |
| `subscription_id`                                                   | *str*                                                               | :heavy_check_mark:                                                  | Subscription Id                                                     |
| `duration`                                                          | *float*                                                             | :heavy_check_mark:                                                  | N/A                                                                 |
| `filter_`                                                           | *str*                                                               | :heavy_check_mark:                                                  | N/A                                                                 |
| `level`                                                             | *float*                                                             | :heavy_check_mark:                                                  | N/A                                                                 |
| `max_events`                                                        | *float*                                                             | :heavy_check_mark:                                                  | N/A                                                                 |
| `step_duration`                                                     | *Optional[float]*                                                   | :heavy_minus_sign:                                                  | N/A                                                                 |
| `worker_id`                                                         | *Optional[str]*                                                     | :heavy_minus_sign:                                                  | N/A                                                                 |
| `worker_threshold`                                                  | *Optional[float]*                                                   | :heavy_minus_sign:                                                  | N/A                                                                 |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.CreateSystemProjectsSubscriptionsCaptureByGroupIDAndSubscriptionIDResponseBody](../../models/createsystemprojectssubscriptionscapturebygroupidandsubscriptionidresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |

## create_system_projects_capture_by_group_id_and_project_id

Capture live incoming data from a particular Project and Subscription at the Destination

### Example Usage

```python
from cribl import Cribl
import os


with Cribl(
    server_url="https://api.example.com",
    bearer_auth=os.getenv("CRIBL_BEARER_AUTH", ""),
) as c_client:

    res = c_client.samples.create_system_projects_capture_by_group_id_and_project_id(group_id="<id>", project_id="<id>", duration=5838.43, filter_="<value>", level=9104.01, max_events=8081.96)

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `group_id`                                                          | *str*                                                               | :heavy_check_mark:                                                  | Group Id                                                            |
| `project_id`                                                        | *str*                                                               | :heavy_check_mark:                                                  | Project Id                                                          |
| `duration`                                                          | *float*                                                             | :heavy_check_mark:                                                  | N/A                                                                 |
| `filter_`                                                           | *str*                                                               | :heavy_check_mark:                                                  | N/A                                                                 |
| `level`                                                             | *float*                                                             | :heavy_check_mark:                                                  | N/A                                                                 |
| `max_events`                                                        | *float*                                                             | :heavy_check_mark:                                                  | N/A                                                                 |
| `step_duration`                                                     | *Optional[float]*                                                   | :heavy_minus_sign:                                                  | N/A                                                                 |
| `worker_id`                                                         | *Optional[str]*                                                     | :heavy_minus_sign:                                                  | N/A                                                                 |
| `worker_threshold`                                                  | *Optional[float]*                                                   | :heavy_minus_sign:                                                  | N/A                                                                 |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.CreateSystemProjectsCaptureByGroupIDAndProjectIDResponseBody](../../models/createsystemprojectscapturebygroupidandprojectidresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |

## create_system_projects_preview_by_group_id_and_project_id

Sends sample events through a Pipeline  for specified Project and returns the results

### Example Usage

```python
import cribl
from cribl import Cribl
import os


with Cribl(
    server_url="https://api.example.com",
    bearer_auth=os.getenv("CRIBL_BEARER_AUTH", ""),
) as c_client:

    res = c_client.samples.create_system_projects_preview_by_group_id_and_project_id(group_id="<id>", project_id="<id>", mode=cribl.Mode.ROUTE_AND_SEND, pipeline_id="<id>", sample_id="<id>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `group_id`                                                          | *str*                                                               | :heavy_check_mark:                                                  | Group Id                                                            |
| `project_id`                                                        | *str*                                                               | :heavy_check_mark:                                                  | Project Id                                                          |
| `mode`                                                              | [models.Mode](../../models/mode.md)                                 | :heavy_check_mark:                                                  | N/A                                                                 |
| `pipeline_id`                                                       | *str*                                                               | :heavy_check_mark:                                                  | N/A                                                                 |
| `sample_id`                                                         | *str*                                                               | :heavy_check_mark:                                                  | N/A                                                                 |
| `cpu_profile`                                                       | *Optional[bool]*                                                    | :heavy_minus_sign:                                                  | N/A                                                                 |
| `dropped`                                                           | *Optional[bool]*                                                    | :heavy_minus_sign:                                                  | N/A                                                                 |
| `enhance_metrics_output`                                            | *Optional[bool]*                                                    | :heavy_minus_sign:                                                  | N/A                                                                 |
| `events`                                                            | List[Dict[str, *Any*]]                                              | :heavy_minus_sign:                                                  | N/A                                                                 |
| `input_id`                                                          | *Optional[str]*                                                     | :heavy_minus_sign:                                                  | N/A                                                                 |
| `level`                                                             | *Optional[float]*                                                   | :heavy_minus_sign:                                                  | N/A                                                                 |
| `memory`                                                            | *Optional[float]*                                                   | :heavy_minus_sign:                                                  | N/A                                                                 |
| `sample_pipeline_id`                                                | *Optional[str]*                                                     | :heavy_minus_sign:                                                  | N/A                                                                 |
| `timeout`                                                           | *Optional[float]*                                                   | :heavy_minus_sign:                                                  | N/A                                                                 |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.CreateSystemProjectsPreviewByGroupIDAndProjectIDResponseBody](../../models/createsystemprojectspreviewbygroupidandprojectidresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |

## list_data_sample

Get a list of DataSample objects

### Example Usage

```python
from cribl import Cribl
import os


with Cribl(
    server_url="https://api.example.com",
    bearer_auth=os.getenv("CRIBL_BEARER_AUTH", ""),
) as c_client:

    res = c_client.samples.list_data_sample()

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.ListDataSampleResponseBody](../../models/listdatasampleresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |

## create_data_sample

Create DataSample

### Example Usage

```python
from cribl import Cribl
import os


with Cribl(
    server_url="https://api.example.com",
    bearer_auth=os.getenv("CRIBL_BEARER_AUTH", ""),
) as c_client:

    res = c_client.samples.create_data_sample(id="<id>", sample_name="<value>", additional_properties={

    })

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                                               | Type                                                                                    | Required                                                                                | Description                                                                             |
| --------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------- |
| `id`                                                                                    | *str*                                                                                   | :heavy_check_mark:                                                                      | N/A                                                                                     |
| `sample_name`                                                                           | *str*                                                                                   | :heavy_check_mark:                                                                      | N/A                                                                                     |
| `pipeline_id`                                                                           | *Optional[str]*                                                                         | :heavy_minus_sign:                                                                      | Select a pipeline to associate with sample with. Select GLOBAL if not sure. Deprecated. |
| `description`                                                                           | *Optional[str]*                                                                         | :heavy_minus_sign:                                                                      | Brief description of this sample file. Optional.                                        |
| `ttl`                                                                                   | *Optional[float]*                                                                       | :heavy_minus_sign:                                                                      | Time to live (TTL) for the sample; reset after each use. Leave empty to never expire.   |
| `tags`                                                                                  | *Optional[str]*                                                                         | :heavy_minus_sign:                                                                      | One or more tags related to this sample file. Optional.                                 |
| `additional_properties`                                                                 | Dict[str, *Any*]                                                                        | :heavy_minus_sign:                                                                      | N/A                                                                                     |
| `retries`                                                                               | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)                        | :heavy_minus_sign:                                                                      | Configuration to override the default retry behavior of the client.                     |

### Response

**[models.CreateDataSampleResponseBody](../../models/createdatasampleresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |

## get_data_sample_by_id

Get DataSample by ID

### Example Usage

```python
from cribl import Cribl
import os


with Cribl(
    server_url="https://api.example.com",
    bearer_auth=os.getenv("CRIBL_BEARER_AUTH", ""),
) as c_client:

    res = c_client.samples.get_data_sample_by_id(id="<id>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `id`                                                                | *str*                                                               | :heavy_check_mark:                                                  | Unique ID to GET                                                    |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.GetDataSampleByIDResponseBody](../../models/getdatasamplebyidresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |

## update_data_sample_by_id

Update DataSample

### Example Usage

```python
from cribl import Cribl
import os


with Cribl(
    server_url="https://api.example.com",
    bearer_auth=os.getenv("CRIBL_BEARER_AUTH", ""),
) as c_client:

    res = c_client.samples.update_data_sample_by_id(id_param="<value>", id="<id>", sample_name="<value>", additional_properties={

    })

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                                               | Type                                                                                    | Required                                                                                | Description                                                                             |
| --------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------- |
| `id_param`                                                                              | *str*                                                                                   | :heavy_check_mark:                                                                      | Unique ID to PATCH                                                                      |
| `id`                                                                                    | *str*                                                                                   | :heavy_check_mark:                                                                      | N/A                                                                                     |
| `sample_name`                                                                           | *str*                                                                                   | :heavy_check_mark:                                                                      | N/A                                                                                     |
| `pipeline_id`                                                                           | *Optional[str]*                                                                         | :heavy_minus_sign:                                                                      | Select a pipeline to associate with sample with. Select GLOBAL if not sure. Deprecated. |
| `description`                                                                           | *Optional[str]*                                                                         | :heavy_minus_sign:                                                                      | Brief description of this sample file. Optional.                                        |
| `ttl`                                                                                   | *Optional[float]*                                                                       | :heavy_minus_sign:                                                                      | Time to live (TTL) for the sample; reset after each use. Leave empty to never expire.   |
| `tags`                                                                                  | *Optional[str]*                                                                         | :heavy_minus_sign:                                                                      | One or more tags related to this sample file. Optional.                                 |
| `additional_properties`                                                                 | Dict[str, *Any*]                                                                        | :heavy_minus_sign:                                                                      | N/A                                                                                     |
| `retries`                                                                               | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)                        | :heavy_minus_sign:                                                                      | Configuration to override the default retry behavior of the client.                     |

### Response

**[models.UpdateDataSampleByIDResponseBody](../../models/updatedatasamplebyidresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |

## delete_data_sample_by_id

Delete DataSample

### Example Usage

```python
from cribl import Cribl
import os


with Cribl(
    server_url="https://api.example.com",
    bearer_auth=os.getenv("CRIBL_BEARER_AUTH", ""),
) as c_client:

    res = c_client.samples.delete_data_sample_by_id(id="<id>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `id`                                                                | *str*                                                               | :heavy_check_mark:                                                  | Unique ID to DELETE                                                 |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.DeleteDataSampleByIDResponseBody](../../models/deletedatasamplebyidresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |

## get_data_sample_content_by_id

Get sample content by ID

### Example Usage

```python
from cribl import Cribl
import os


with Cribl(
    server_url="https://api.example.com",
    bearer_auth=os.getenv("CRIBL_BEARER_AUTH", ""),
) as c_client:

    res = c_client.samples.get_data_sample_content_by_id(id="<id>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `id`                                                                | *str*                                                               | :heavy_check_mark:                                                  | Sample ID                                                           |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.GetDataSampleContentByIDResponseBody](../../models/getdatasamplecontentbyidresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |

## create_system_capture

Capture live incoming data

### Example Usage

```python
from cribl import Cribl
import os


with Cribl(
    server_url="https://api.example.com",
    bearer_auth=os.getenv("CRIBL_BEARER_AUTH", ""),
) as c_client:

    res = c_client.samples.create_system_capture(duration=333.16, filter_="<value>", level=584.49, max_events=4480.84)

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `duration`                                                          | *float*                                                             | :heavy_check_mark:                                                  | N/A                                                                 |
| `filter_`                                                           | *str*                                                               | :heavy_check_mark:                                                  | N/A                                                                 |
| `level`                                                             | *float*                                                             | :heavy_check_mark:                                                  | N/A                                                                 |
| `max_events`                                                        | *float*                                                             | :heavy_check_mark:                                                  | N/A                                                                 |
| `step_duration`                                                     | *Optional[float]*                                                   | :heavy_minus_sign:                                                  | N/A                                                                 |
| `worker_id`                                                         | *Optional[str]*                                                     | :heavy_minus_sign:                                                  | N/A                                                                 |
| `worker_threshold`                                                  | *Optional[float]*                                                   | :heavy_minus_sign:                                                  | N/A                                                                 |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.CreateSystemCaptureResponseBody](../../models/createsystemcaptureresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |

## create_system_projects_capture_by_project_id

Capture live incoming data from a particular project and subscription at the destination

### Example Usage

```python
from cribl import Cribl
import os


with Cribl(
    server_url="https://api.example.com",
    bearer_auth=os.getenv("CRIBL_BEARER_AUTH", ""),
) as c_client:

    res = c_client.samples.create_system_projects_capture_by_project_id(project_id="<id>", duration=5278.59, filter_="<value>", level=3497.32, max_events=2257.32)

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `project_id`                                                        | *str*                                                               | :heavy_check_mark:                                                  | Project ID                                                          |
| `duration`                                                          | *float*                                                             | :heavy_check_mark:                                                  | N/A                                                                 |
| `filter_`                                                           | *str*                                                               | :heavy_check_mark:                                                  | N/A                                                                 |
| `level`                                                             | *float*                                                             | :heavy_check_mark:                                                  | N/A                                                                 |
| `max_events`                                                        | *float*                                                             | :heavy_check_mark:                                                  | N/A                                                                 |
| `step_duration`                                                     | *Optional[float]*                                                   | :heavy_minus_sign:                                                  | N/A                                                                 |
| `worker_id`                                                         | *Optional[str]*                                                     | :heavy_minus_sign:                                                  | N/A                                                                 |
| `worker_threshold`                                                  | *Optional[float]*                                                   | :heavy_minus_sign:                                                  | N/A                                                                 |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.CreateSystemProjectsCaptureByProjectIDResponseBody](../../models/createsystemprojectscapturebyprojectidresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |

## create_system_projects_subscriptions_capture_by_project_id_and_subscription_id

Capture live incoming data from a particular project and subscription at the subscription

### Example Usage

```python
from cribl import Cribl
import os


with Cribl(
    server_url="https://api.example.com",
    bearer_auth=os.getenv("CRIBL_BEARER_AUTH", ""),
) as c_client:

    res = c_client.samples.create_system_projects_subscriptions_capture_by_project_id_and_subscription_id(project_id="<id>", subscription_id="<id>", duration=8758.36, filter_="<value>", level=6607.86, max_events=5813.86)

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `project_id`                                                        | *str*                                                               | :heavy_check_mark:                                                  | Project Id                                                          |
| `subscription_id`                                                   | *str*                                                               | :heavy_check_mark:                                                  | SubscriptionId Id                                                   |
| `duration`                                                          | *float*                                                             | :heavy_check_mark:                                                  | N/A                                                                 |
| `filter_`                                                           | *str*                                                               | :heavy_check_mark:                                                  | N/A                                                                 |
| `level`                                                             | *float*                                                             | :heavy_check_mark:                                                  | N/A                                                                 |
| `max_events`                                                        | *float*                                                             | :heavy_check_mark:                                                  | N/A                                                                 |
| `step_duration`                                                     | *Optional[float]*                                                   | :heavy_minus_sign:                                                  | N/A                                                                 |
| `worker_id`                                                         | *Optional[str]*                                                     | :heavy_minus_sign:                                                  | N/A                                                                 |
| `worker_threshold`                                                  | *Optional[float]*                                                   | :heavy_minus_sign:                                                  | N/A                                                                 |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.CreateSystemProjectsSubscriptionsCaptureByProjectIDAndSubscriptionIDResponseBody](../../models/createsystemprojectssubscriptionscapturebyprojectidandsubscriptionidresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |

## create_preview

Sends sample events through a pipeline and returns the results

### Example Usage

```python
import cribl
from cribl import Cribl
import os


with Cribl(
    server_url="https://api.example.com",
    bearer_auth=os.getenv("CRIBL_BEARER_AUTH", ""),
) as c_client:

    res = c_client.samples.create_preview(mode=cribl.Mode.PIPE, pipeline_id="<id>", sample_id="<id>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `mode`                                                              | [models.Mode](../../models/mode.md)                                 | :heavy_check_mark:                                                  | N/A                                                                 |
| `pipeline_id`                                                       | *str*                                                               | :heavy_check_mark:                                                  | N/A                                                                 |
| `sample_id`                                                         | *str*                                                               | :heavy_check_mark:                                                  | N/A                                                                 |
| `cpu_profile`                                                       | *Optional[bool]*                                                    | :heavy_minus_sign:                                                  | N/A                                                                 |
| `dropped`                                                           | *Optional[bool]*                                                    | :heavy_minus_sign:                                                  | N/A                                                                 |
| `enhance_metrics_output`                                            | *Optional[bool]*                                                    | :heavy_minus_sign:                                                  | N/A                                                                 |
| `events`                                                            | List[Dict[str, *Any*]]                                              | :heavy_minus_sign:                                                  | N/A                                                                 |
| `input_id`                                                          | *Optional[str]*                                                     | :heavy_minus_sign:                                                  | N/A                                                                 |
| `level`                                                             | *Optional[float]*                                                   | :heavy_minus_sign:                                                  | N/A                                                                 |
| `memory`                                                            | *Optional[float]*                                                   | :heavy_minus_sign:                                                  | N/A                                                                 |
| `sample_pipeline_id`                                                | *Optional[str]*                                                     | :heavy_minus_sign:                                                  | N/A                                                                 |
| `timeout`                                                           | *Optional[float]*                                                   | :heavy_minus_sign:                                                  | N/A                                                                 |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.CreatePreviewResponseBody](../../models/createpreviewresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |