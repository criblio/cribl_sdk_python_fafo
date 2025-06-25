# NotificationsSDK
(*notifications*)

## Overview

Actions related to Notifications

### Available Operations

* [list_notification](#list_notification) - Get a list of Notification objects
* [create_notification](#create_notification) - Create Notification
* [get_notification_by_id](#get_notification_by_id) - Get Notification by ID
* [update_notification_by_id](#update_notification_by_id) - Update Notification
* [delete_notification_by_id](#delete_notification_by_id) - Delete Notification

## list_notification

Get a list of Notification objects

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

    res = cspf_client.notifications.list_notification()

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.ListNotificationResponse](../../models/listnotificationresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| errors.Error     | 500              | application/json |
| errors.APIError  | 4XX, 5XX         | \*/\*            |

## create_notification

Create Notification

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

    res = cspf_client.notifications.create_notification(id="<id>", condition="<value>", disabled=False)

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                                             | Type                                                                                  | Required                                                                              | Description                                                                           |
| ------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------- |
| `id`                                                                                  | *str*                                                                                 | :heavy_check_mark:                                                                    | N/A                                                                                   |
| `condition`                                                                           | *str*                                                                                 | :heavy_check_mark:                                                                    | N/A                                                                                   |
| `disabled`                                                                            | *Optional[bool]*                                                                      | :heavy_minus_sign:                                                                    | N/A                                                                                   |
| `targets`                                                                             | List[*str*]                                                                           | :heavy_minus_sign:                                                                    | Targets to send any Notifications to                                                  |
| `target_configs`                                                                      | List[[models.TargetConfigUnion](../../models/targetconfigunion.md)]                   | :heavy_minus_sign:                                                                    | N/A                                                                                   |
| `conf`                                                                                | [Optional[models.ConditionSpecificConfigs]](../../models/conditionspecificconfigs.md) | :heavy_minus_sign:                                                                    | N/A                                                                                   |
| `metadata`                                                                            | List[[models.NotificationMetadatum](../../models/notificationmetadatum.md)]           | :heavy_minus_sign:                                                                    | Fields to add to events from this input                                               |
| `retries`                                                                             | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)                      | :heavy_minus_sign:                                                                    | Configuration to override the default retry behavior of the client.                   |

### Response

**[models.CreateNotificationResponse](../../models/createnotificationresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| errors.Error     | 500              | application/json |
| errors.APIError  | 4XX, 5XX         | \*/\*            |

## get_notification_by_id

Get Notification by ID

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

    res = cspf_client.notifications.get_notification_by_id(id="<id>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `id`                                                                | *str*                                                               | :heavy_check_mark:                                                  | Unique ID to GET                                                    |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.GetNotificationByIDResponse](../../models/getnotificationbyidresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| errors.Error     | 500              | application/json |
| errors.APIError  | 4XX, 5XX         | \*/\*            |

## update_notification_by_id

Update Notification

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

    res = cspf_client.notifications.update_notification_by_id(id_param="<value>", id="<id>", condition="<value>", disabled=False)

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                                             | Type                                                                                  | Required                                                                              | Description                                                                           |
| ------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------- |
| `id_param`                                                                            | *str*                                                                                 | :heavy_check_mark:                                                                    | Unique ID to PATCH                                                                    |
| `id`                                                                                  | *str*                                                                                 | :heavy_check_mark:                                                                    | N/A                                                                                   |
| `condition`                                                                           | *str*                                                                                 | :heavy_check_mark:                                                                    | N/A                                                                                   |
| `disabled`                                                                            | *Optional[bool]*                                                                      | :heavy_minus_sign:                                                                    | N/A                                                                                   |
| `targets`                                                                             | List[*str*]                                                                           | :heavy_minus_sign:                                                                    | Targets to send any Notifications to                                                  |
| `target_configs`                                                                      | List[[models.TargetConfigUnion](../../models/targetconfigunion.md)]                   | :heavy_minus_sign:                                                                    | N/A                                                                                   |
| `conf`                                                                                | [Optional[models.ConditionSpecificConfigs]](../../models/conditionspecificconfigs.md) | :heavy_minus_sign:                                                                    | N/A                                                                                   |
| `metadata`                                                                            | List[[models.NotificationMetadatum](../../models/notificationmetadatum.md)]           | :heavy_minus_sign:                                                                    | Fields to add to events from this input                                               |
| `retries`                                                                             | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)                      | :heavy_minus_sign:                                                                    | Configuration to override the default retry behavior of the client.                   |

### Response

**[models.UpdateNotificationByIDResponse](../../models/updatenotificationbyidresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| errors.Error     | 500              | application/json |
| errors.APIError  | 4XX, 5XX         | \*/\*            |

## delete_notification_by_id

Delete Notification

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

    res = cspf_client.notifications.delete_notification_by_id(id="<id>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `id`                                                                | *str*                                                               | :heavy_check_mark:                                                  | Unique ID to DELETE                                                 |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.DeleteNotificationByIDResponse](../../models/deletenotificationbyidresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| errors.Error     | 500              | application/json |
| errors.APIError  | 4XX, 5XX         | \*/\*            |