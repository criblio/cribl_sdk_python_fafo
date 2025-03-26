# Dashboards
(*dashboards*)

## Overview

Actions related to Dashboards

### Available Operations

* [list_search_dashboard](#list_search_dashboard) - Get a list of SearchDashboard objects
* [create_search_dashboard](#create_search_dashboard) - Create SearchDashboard
* [get_search_dashboard_by_id](#get_search_dashboard_by_id) - Get SearchDashboard by ID
* [update_search_dashboard_by_id](#update_search_dashboard_by_id) - Update SearchDashboard
* [delete_search_dashboard_by_id](#delete_search_dashboard_by_id) - Delete SearchDashboard
* [get_search_dashboard_acl_by_id](#get_search_dashboard_acl_by_id) - Get SearchDashboard ACL
* [create_search_dashboard_acl_apply_by_id](#create_search_dashboard_acl_apply_by_id) - Modify SearchDashboard ACL
* [get_search_dashboard_acl_teams_by_id](#get_search_dashboard_acl_teams_by_id) - Get SearchDashboard Teams
* [create_search_dashboard_acl_teams_apply_by_id](#create_search_dashboard_acl_teams_apply_by_id) - Modify SearchDashboard Teams ACL

## list_search_dashboard

Get a list of SearchDashboard objects

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

    res = c_client.dashboards.list_search_dashboard()

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.ListSearchDashboardResponseBody](../../models/listsearchdashboardresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |

## create_search_dashboard

Create SearchDashboard

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

    res = c_client.dashboards.create_search_dashboard(created=4792.84, created_by="<value>", elements=[
        {
            "id": "<id>",
            "layout": {
                "h": 106.05,
                "w": 472.66,
                "x": 4619.27,
                "y": 2943.59,
            },
            "search": {
                "type": cribl.SearchQuery3Type.VALUES,
                "values": [

                ],
            },
            "type": cribl.DashboardElementType.CHART_HORIZONTAL_BAR,
        },
        {
            "id": "<id>",
            "layout": {
                "h": 1930.21,
                "w": 1107.88,
                "x": 6308.92,
                "y": 2426.59,
            },
            "search": {
                "earliest": 8306.4,
                "latest": 6427.51,
                "query": "<value>",
                "type": cribl.SearchQuery2Type.INLINE,
            },
            "type": cribl.DashboardElementType.COUNTER_SINGLE,
        },
        {
            "id": "<id>",
            "layout": {
                "h": 47.23,
                "w": 1577.11,
                "x": 529.47,
                "y": 9170.69,
            },
            "type": cribl.ElementsType.MARKDOWN_DEFAULT,
            "variant": cribl.Variant.MARKDOWN,
        },
    ], id="<id>", modified=5752.27, name="<value>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                                 | Type                                                                      | Required                                                                  | Description                                                               |
| ------------------------------------------------------------------------- | ------------------------------------------------------------------------- | ------------------------------------------------------------------------- | ------------------------------------------------------------------------- |
| `created`                                                                 | *float*                                                                   | :heavy_check_mark:                                                        | N/A                                                                       |
| `created_by`                                                              | *str*                                                                     | :heavy_check_mark:                                                        | N/A                                                                       |
| `elements`                                                                | List[[models.Elements](../../models/elements.md)]                         | :heavy_check_mark:                                                        | N/A                                                                       |
| `id`                                                                      | *str*                                                                     | :heavy_check_mark:                                                        | N/A                                                                       |
| `modified`                                                                | *float*                                                                   | :heavy_check_mark:                                                        | N/A                                                                       |
| `name`                                                                    | *str*                                                                     | :heavy_check_mark:                                                        | N/A                                                                       |
| `cache_ttl_seconds`                                                       | *Optional[float]*                                                         | :heavy_minus_sign:                                                        | N/A                                                                       |
| `category`                                                                | *Optional[str]*                                                           | :heavy_minus_sign:                                                        | N/A                                                                       |
| `description`                                                             | *Optional[str]*                                                           | :heavy_minus_sign:                                                        | N/A                                                                       |
| `display_created_by`                                                      | *Optional[str]*                                                           | :heavy_minus_sign:                                                        | N/A                                                                       |
| `display_modified_by`                                                     | *Optional[str]*                                                           | :heavy_minus_sign:                                                        | N/A                                                                       |
| `modified_by`                                                             | *Optional[str]*                                                           | :heavy_minus_sign:                                                        | N/A                                                                       |
| `pack_id`                                                                 | *Optional[str]*                                                           | :heavy_minus_sign:                                                        | N/A                                                                       |
| `refresh_rate`                                                            | *Optional[float]*                                                         | :heavy_minus_sign:                                                        | N/A                                                                       |
| `resolved_dataset_ids`                                                    | List[*str*]                                                               | :heavy_minus_sign:                                                        | N/A                                                                       |
| `schedule`                                                                | [Optional[models.SavedQuerySchedule]](../../models/savedqueryschedule.md) | :heavy_minus_sign:                                                        | N/A                                                                       |
| `retries`                                                                 | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)          | :heavy_minus_sign:                                                        | Configuration to override the default retry behavior of the client.       |

### Response

**[models.CreateSearchDashboardResponseBody](../../models/createsearchdashboardresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |

## get_search_dashboard_by_id

Get SearchDashboard by ID

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

    res = c_client.dashboards.get_search_dashboard_by_id(id="<id>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `id`                                                                | *str*                                                               | :heavy_check_mark:                                                  | Unique ID to GET                                                    |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.GetSearchDashboardByIDResponseBody](../../models/getsearchdashboardbyidresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |

## update_search_dashboard_by_id

Update SearchDashboard

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

    res = c_client.dashboards.update_search_dashboard_by_id(id_param="<value>", created=7131.04, created_by="<value>", elements=[

    ], id="<id>", modified=370.77, name="<value>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                                 | Type                                                                      | Required                                                                  | Description                                                               |
| ------------------------------------------------------------------------- | ------------------------------------------------------------------------- | ------------------------------------------------------------------------- | ------------------------------------------------------------------------- |
| `id_param`                                                                | *str*                                                                     | :heavy_check_mark:                                                        | Unique ID to PATCH                                                        |
| `created`                                                                 | *float*                                                                   | :heavy_check_mark:                                                        | N/A                                                                       |
| `created_by`                                                              | *str*                                                                     | :heavy_check_mark:                                                        | N/A                                                                       |
| `elements`                                                                | List[[models.Elements](../../models/elements.md)]                         | :heavy_check_mark:                                                        | N/A                                                                       |
| `id`                                                                      | *str*                                                                     | :heavy_check_mark:                                                        | N/A                                                                       |
| `modified`                                                                | *float*                                                                   | :heavy_check_mark:                                                        | N/A                                                                       |
| `name`                                                                    | *str*                                                                     | :heavy_check_mark:                                                        | N/A                                                                       |
| `cache_ttl_seconds`                                                       | *Optional[float]*                                                         | :heavy_minus_sign:                                                        | N/A                                                                       |
| `category`                                                                | *Optional[str]*                                                           | :heavy_minus_sign:                                                        | N/A                                                                       |
| `description`                                                             | *Optional[str]*                                                           | :heavy_minus_sign:                                                        | N/A                                                                       |
| `display_created_by`                                                      | *Optional[str]*                                                           | :heavy_minus_sign:                                                        | N/A                                                                       |
| `display_modified_by`                                                     | *Optional[str]*                                                           | :heavy_minus_sign:                                                        | N/A                                                                       |
| `modified_by`                                                             | *Optional[str]*                                                           | :heavy_minus_sign:                                                        | N/A                                                                       |
| `pack_id`                                                                 | *Optional[str]*                                                           | :heavy_minus_sign:                                                        | N/A                                                                       |
| `refresh_rate`                                                            | *Optional[float]*                                                         | :heavy_minus_sign:                                                        | N/A                                                                       |
| `resolved_dataset_ids`                                                    | List[*str*]                                                               | :heavy_minus_sign:                                                        | N/A                                                                       |
| `schedule`                                                                | [Optional[models.SavedQuerySchedule]](../../models/savedqueryschedule.md) | :heavy_minus_sign:                                                        | N/A                                                                       |
| `retries`                                                                 | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)          | :heavy_minus_sign:                                                        | Configuration to override the default retry behavior of the client.       |

### Response

**[models.UpdateSearchDashboardByIDResponseBody](../../models/updatesearchdashboardbyidresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |

## delete_search_dashboard_by_id

Delete SearchDashboard

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

    res = c_client.dashboards.delete_search_dashboard_by_id(id="<id>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `id`                                                                | *str*                                                               | :heavy_check_mark:                                                  | Unique ID to DELETE                                                 |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.DeleteSearchDashboardByIDResponseBody](../../models/deletesearchdashboardbyidresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |

## get_search_dashboard_acl_by_id

List accesses to SearchDashboard granted to users

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

    res = c_client.dashboards.get_search_dashboard_acl_by_id(id="<id>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `id`                                                                | *str*                                                               | :heavy_check_mark:                                                  | Unique ID for ACL Get                                               |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.GetSearchDashboardACLByIDResponseBody](../../models/getsearchdashboardaclbyidresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |

## create_search_dashboard_acl_apply_by_id

Add/remove accesses to SearchDashboard for users

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

    c_client.dashboards.create_search_dashboard_acl_apply_by_id(id="<id>")

    # Use the SDK ...

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `id`                                                                | *str*                                                               | :heavy_check_mark:                                                  | Unique ID for ACL Create                                            |
| `add`                                                               | [Optional[models.AccessControl]](../../models/accesscontrol.md)     | :heavy_minus_sign:                                                  | N/A                                                                 |
| `rm`                                                                | [Optional[models.AccessControl]](../../models/accesscontrol.md)     | :heavy_minus_sign:                                                  | N/A                                                                 |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |

## get_search_dashboard_acl_teams_by_id

List accesses to SearchDashboard granted to Teams

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

    res = c_client.dashboards.get_search_dashboard_acl_teams_by_id(id="<id>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `id`                                                                | *str*                                                               | :heavy_check_mark:                                                  | Unique ID for ACL Teams Get                                         |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.GetSearchDashboardACLTeamsByIDResponseBody](../../models/getsearchdashboardaclteamsbyidresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |

## create_search_dashboard_acl_teams_apply_by_id

Add/remove accesses to SearchDashboard for Teams

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

    c_client.dashboards.create_search_dashboard_acl_teams_apply_by_id(id="<id>")

    # Use the SDK ...

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `id`                                                                | *str*                                                               | :heavy_check_mark:                                                  | Unique ID for ACL Teams Create                                      |
| `add`                                                               | [Optional[models.AccessControl]](../../models/accesscontrol.md)     | :heavy_minus_sign:                                                  | N/A                                                                 |
| `rm`                                                                | [Optional[models.AccessControl]](../../models/accesscontrol.md)     | :heavy_minus_sign:                                                  | N/A                                                                 |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |