# Preview
(*preview*)

## Overview

Actions related to data preview

### Available Operations

* [create_system_projects_subscriptions_capture_by_group_id_and_subscription_id](#create_system_projects_subscriptions_capture_by_group_id_and_subscription_id) - Capture live incoming data from a particular Project and Subscription at the Subscription
* [create_system_projects_capture_by_group_id_and_project_id](#create_system_projects_capture_by_group_id_and_project_id) - Capture live incoming data from a particular Project and Subscription at the Destination
* [create_system_projects_preview_by_group_id_and_project_id](#create_system_projects_preview_by_group_id_and_project_id) - Sends sample events through a Pipeline  for specified Project and returns the results
* [create_system_capture](#create_system_capture) - Capture live incoming data
* [create_system_projects_capture_by_project_id](#create_system_projects_capture_by_project_id) - Capture live incoming data from a particular project and subscription at the destination
* [create_system_projects_subscriptions_capture_by_project_id_and_subscription_id](#create_system_projects_subscriptions_capture_by_project_id_and_subscription_id) - Capture live incoming data from a particular project and subscription at the subscription
* [create_preview](#create_preview) - Sends sample events through a pipeline and returns the results

## create_system_projects_subscriptions_capture_by_group_id_and_subscription_id

Capture live incoming data from a particular Project and Subscription at the Subscription

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

    res = cspf_client.preview.create_system_projects_subscriptions_capture_by_group_id_and_subscription_id(group_id="<id>", project_id="<id>", subscription_id="<id>", duration=9977.94, filter_="<value>", level=7371.6, max_events=5232.64)

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

**[models.CreateSystemProjectsSubscriptionsCaptureByGroupIDAndSubscriptionIDResponse](../../models/createsystemprojectssubscriptionscapturebygroupidandsubscriptionidresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| errors.Error     | 500              | application/json |
| errors.APIError  | 4XX, 5XX         | \*/\*            |

## create_system_projects_capture_by_group_id_and_project_id

Capture live incoming data from a particular Project and Subscription at the Destination

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

    res = cspf_client.preview.create_system_projects_capture_by_group_id_and_project_id(group_id="<id>", project_id="<id>", duration=7020.88, filter_="<value>", level=4494.37, max_events=7103.16)

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

**[models.CreateSystemProjectsCaptureByGroupIDAndProjectIDResponse](../../models/createsystemprojectscapturebygroupidandprojectidresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| errors.Error     | 500              | application/json |
| errors.APIError  | 4XX, 5XX         | \*/\*            |

## create_system_projects_preview_by_group_id_and_project_id

Sends sample events through a Pipeline  for specified Project and returns the results

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

    res = cspf_client.preview.create_system_projects_preview_by_group_id_and_project_id(group_id="<id>", project_id="<id>", mode=models.PreviewDataParamsMode.ROUTE, pipeline_id="<id>", sample_id="<id>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                             | Type                                                                  | Required                                                              | Description                                                           |
| --------------------------------------------------------------------- | --------------------------------------------------------------------- | --------------------------------------------------------------------- | --------------------------------------------------------------------- |
| `group_id`                                                            | *str*                                                                 | :heavy_check_mark:                                                    | Group Id                                                              |
| `project_id`                                                          | *str*                                                                 | :heavy_check_mark:                                                    | Project Id                                                            |
| `mode`                                                                | [models.PreviewDataParamsMode](../../models/previewdataparamsmode.md) | :heavy_check_mark:                                                    | N/A                                                                   |
| `pipeline_id`                                                         | *str*                                                                 | :heavy_check_mark:                                                    | N/A                                                                   |
| `sample_id`                                                           | *str*                                                                 | :heavy_check_mark:                                                    | N/A                                                                   |
| `cpu_profile`                                                         | *Optional[bool]*                                                      | :heavy_minus_sign:                                                    | N/A                                                                   |
| `dropped`                                                             | *Optional[bool]*                                                      | :heavy_minus_sign:                                                    | N/A                                                                   |
| `enhance_metrics_output`                                              | *Optional[bool]*                                                      | :heavy_minus_sign:                                                    | N/A                                                                   |
| `events`                                                              | List[Dict[str, *Any*]]                                                | :heavy_minus_sign:                                                    | N/A                                                                   |
| `input_id`                                                            | *Optional[str]*                                                       | :heavy_minus_sign:                                                    | N/A                                                                   |
| `level`                                                               | *Optional[float]*                                                     | :heavy_minus_sign:                                                    | N/A                                                                   |
| `memory`                                                              | *Optional[float]*                                                     | :heavy_minus_sign:                                                    | N/A                                                                   |
| `sample_pipeline_id`                                                  | *Optional[str]*                                                       | :heavy_minus_sign:                                                    | N/A                                                                   |
| `timeout`                                                             | *Optional[float]*                                                     | :heavy_minus_sign:                                                    | N/A                                                                   |
| `retries`                                                             | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)      | :heavy_minus_sign:                                                    | Configuration to override the default retry behavior of the client.   |

### Response

**[models.CreateSystemProjectsPreviewByGroupIDAndProjectIDResponse](../../models/createsystemprojectspreviewbygroupidandprojectidresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| errors.Error     | 500              | application/json |
| errors.APIError  | 4XX, 5XX         | \*/\*            |

## create_system_capture

Capture live incoming data

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

    res = cspf_client.preview.create_system_capture(duration=5717.32, filter_="<value>", level=6094.12, max_events=9941.84)

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

**[models.CreateSystemCaptureResponse](../../models/createsystemcaptureresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| errors.Error     | 500              | application/json |
| errors.APIError  | 4XX, 5XX         | \*/\*            |

## create_system_projects_capture_by_project_id

Capture live incoming data from a particular project and subscription at the destination

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

    res = cspf_client.preview.create_system_projects_capture_by_project_id(project_id="<id>", duration=4855.02, filter_="<value>", level=8634.29, max_events=5475.12)

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

**[models.CreateSystemProjectsCaptureByProjectIDResponse](../../models/createsystemprojectscapturebyprojectidresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| errors.Error     | 500              | application/json |
| errors.APIError  | 4XX, 5XX         | \*/\*            |

## create_system_projects_subscriptions_capture_by_project_id_and_subscription_id

Capture live incoming data from a particular project and subscription at the subscription

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

    res = cspf_client.preview.create_system_projects_subscriptions_capture_by_project_id_and_subscription_id(project_id="<id>", subscription_id="<id>", duration=9984.14, filter_="<value>", level=8613.29, max_events=502.1)

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

**[models.CreateSystemProjectsSubscriptionsCaptureByProjectIDAndSubscriptionIDResponse](../../models/createsystemprojectssubscriptionscapturebyprojectidandsubscriptionidresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| errors.Error     | 500              | application/json |
| errors.APIError  | 4XX, 5XX         | \*/\*            |

## create_preview

Sends sample events through a pipeline and returns the results

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

    res = cspf_client.preview.create_preview(mode=models.PreviewDataParamsMode.PIPE, pipeline_id="<id>", sample_id="<id>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                             | Type                                                                  | Required                                                              | Description                                                           |
| --------------------------------------------------------------------- | --------------------------------------------------------------------- | --------------------------------------------------------------------- | --------------------------------------------------------------------- |
| `mode`                                                                | [models.PreviewDataParamsMode](../../models/previewdataparamsmode.md) | :heavy_check_mark:                                                    | N/A                                                                   |
| `pipeline_id`                                                         | *str*                                                                 | :heavy_check_mark:                                                    | N/A                                                                   |
| `sample_id`                                                           | *str*                                                                 | :heavy_check_mark:                                                    | N/A                                                                   |
| `cpu_profile`                                                         | *Optional[bool]*                                                      | :heavy_minus_sign:                                                    | N/A                                                                   |
| `dropped`                                                             | *Optional[bool]*                                                      | :heavy_minus_sign:                                                    | N/A                                                                   |
| `enhance_metrics_output`                                              | *Optional[bool]*                                                      | :heavy_minus_sign:                                                    | N/A                                                                   |
| `events`                                                              | List[Dict[str, *Any*]]                                                | :heavy_minus_sign:                                                    | N/A                                                                   |
| `input_id`                                                            | *Optional[str]*                                                       | :heavy_minus_sign:                                                    | N/A                                                                   |
| `level`                                                               | *Optional[float]*                                                     | :heavy_minus_sign:                                                    | N/A                                                                   |
| `memory`                                                              | *Optional[float]*                                                     | :heavy_minus_sign:                                                    | N/A                                                                   |
| `sample_pipeline_id`                                                  | *Optional[str]*                                                       | :heavy_minus_sign:                                                    | N/A                                                                   |
| `timeout`                                                             | *Optional[float]*                                                     | :heavy_minus_sign:                                                    | N/A                                                                   |
| `retries`                                                             | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)      | :heavy_minus_sign:                                                    | Configuration to override the default retry behavior of the client.   |

### Response

**[models.CreatePreviewResponse](../../models/createpreviewresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| errors.Error     | 500              | application/json |
| errors.APIError  | 4XX, 5XX         | \*/\*            |