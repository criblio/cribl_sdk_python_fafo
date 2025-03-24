# Notifications
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
from cribl import Cribl
import os


with Cribl(
    bearer_auth=os.getenv("CRIBL_BEARER_AUTH", ""),
) as c_client:

    res = c_client.notifications.list_notification()

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.ListNotificationResponseBody](../../models/listnotificationresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |

## create_notification

Create Notification

### Example Usage

```python
from cribl import Cribl
import os


with Cribl(
    bearer_auth=os.getenv("CRIBL_BEARER_AUTH", ""),
) as c_client:

    res = c_client.notifications.create_notification(id="<id>", condition="<value>")

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
| `target_configs`                                                                      | List[[models.TargetConfigs](../../models/targetconfigs.md)]                           | :heavy_minus_sign:                                                                    | N/A                                                                                   |
| `conf`                                                                                | [Optional[models.ConditionSpecificConfigs]](../../models/conditionspecificconfigs.md) | :heavy_minus_sign:                                                                    | N/A                                                                                   |
| `metadata`                                                                            | List[[models.NotificationMetadata](../../models/notificationmetadata.md)]             | :heavy_minus_sign:                                                                    | Fields to add to events from this input                                               |
| `retries`                                                                             | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)                      | :heavy_minus_sign:                                                                    | Configuration to override the default retry behavior of the client.                   |

### Response

**[models.CreateNotificationResponseBody](../../models/createnotificationresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |

## get_notification_by_id

Get Notification by ID

### Example Usage

```python
from cribl import Cribl
import os


with Cribl(
    bearer_auth=os.getenv("CRIBL_BEARER_AUTH", ""),
) as c_client:

    res = c_client.notifications.get_notification_by_id(id="<id>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `id`                                                                | *str*                                                               | :heavy_check_mark:                                                  | Unique ID to GET                                                    |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.GetNotificationByIDResponseBody](../../models/getnotificationbyidresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |

## update_notification_by_id

Update Notification

### Example Usage

```python
from cribl import Cribl
import os


with Cribl(
    bearer_auth=os.getenv("CRIBL_BEARER_AUTH", ""),
) as c_client:

    res = c_client.notifications.update_notification_by_id(id_param="<value>", id="<id>", condition="<value>")

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
| `target_configs`                                                                      | List[[models.TargetConfigs](../../models/targetconfigs.md)]                           | :heavy_minus_sign:                                                                    | N/A                                                                                   |
| `conf`                                                                                | [Optional[models.ConditionSpecificConfigs]](../../models/conditionspecificconfigs.md) | :heavy_minus_sign:                                                                    | N/A                                                                                   |
| `metadata`                                                                            | List[[models.NotificationMetadata](../../models/notificationmetadata.md)]             | :heavy_minus_sign:                                                                    | Fields to add to events from this input                                               |
| `retries`                                                                             | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)                      | :heavy_minus_sign:                                                                    | Configuration to override the default retry behavior of the client.                   |

### Response

**[models.UpdateNotificationByIDResponseBody](../../models/updatenotificationbyidresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |

## delete_notification_by_id

Delete Notification

### Example Usage

```python
from cribl import Cribl
import os


with Cribl(
    bearer_auth=os.getenv("CRIBL_BEARER_AUTH", ""),
) as c_client:

    res = c_client.notifications.delete_notification_by_id(id="<id>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `id`                                                                | *str*                                                               | :heavy_check_mark:                                                  | Unique ID to DELETE                                                 |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.DeleteNotificationByIDResponseBody](../../models/deletenotificationbyidresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |