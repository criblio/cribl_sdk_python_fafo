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
from cribl_sdk_python_fafo import CriblSDKPythonFafo, models
import os


with CriblSDKPythonFafo(
    server_url="https://api.example.com",
    security=models.Security(
        bearer_auth=os.getenv("CRIBLSDKPYTHONFAFO_BEARER_AUTH", ""),
    ),
) as cspf_client:

    res = cspf_client.dashboards.list_search_dashboard()

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.ListSearchDashboardResponse](../../models/listsearchdashboardresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| errors.Error     | 500              | application/json |
| errors.APIError  | 4XX, 5XX         | \*/\*            |

## create_search_dashboard

Create SearchDashboard

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

    res = cspf_client.dashboards.create_search_dashboard(created=9377.15, created_by="<value>", elements=[
        {
            "id": "<id>",
            "layout": {
                "h": 5003.17,
                "w": 3536.4,
                "x": 839.93,
                "y": 6172.28,
            },
            "type": models.DashboardElementType.MARKDOWN_DEFAULT,
            "variant": models.VariantMarkdown.MARKDOWN,
        },
    ], id="<id>", modified=5727.25, name="<value>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                                 | Type                                                                      | Required                                                                  | Description                                                               |
| ------------------------------------------------------------------------- | ------------------------------------------------------------------------- | ------------------------------------------------------------------------- | ------------------------------------------------------------------------- |
| `created`                                                                 | *float*                                                                   | :heavy_check_mark:                                                        | N/A                                                                       |
| `created_by`                                                              | *str*                                                                     | :heavy_check_mark:                                                        | N/A                                                                       |
| `elements`                                                                | List[[models.DashboardElement](../../models/dashboardelement.md)]         | :heavy_check_mark:                                                        | N/A                                                                       |
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

**[models.CreateSearchDashboardResponse](../../models/createsearchdashboardresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| errors.Error     | 500              | application/json |
| errors.APIError  | 4XX, 5XX         | \*/\*            |

## get_search_dashboard_by_id

Get SearchDashboard by ID

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

    res = cspf_client.dashboards.get_search_dashboard_by_id(id="<id>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `id`                                                                | *str*                                                               | :heavy_check_mark:                                                  | Unique ID to GET                                                    |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.GetSearchDashboardByIDResponse](../../models/getsearchdashboardbyidresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| errors.Error     | 500              | application/json |
| errors.APIError  | 4XX, 5XX         | \*/\*            |

## update_search_dashboard_by_id

Update SearchDashboard

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

    res = cspf_client.dashboards.update_search_dashboard_by_id(id_param="<value>", created=9322.04, created_by="<value>", elements=[
        {
            "id": "<id>",
            "layout": {
                "h": 639.57,
                "w": 6274.13,
                "x": 2916.93,
                "y": 2991.89,
            },
            "search": {
                "type": models.TypeValues.VALUES,
                "values": [],
            },
            "type": models.VisualizationElementTypeEnum1.CHART_HORIZONTAL_BAR,
        },
    ], id="<id>", modified=1763.84, name="<value>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                                 | Type                                                                      | Required                                                                  | Description                                                               |
| ------------------------------------------------------------------------- | ------------------------------------------------------------------------- | ------------------------------------------------------------------------- | ------------------------------------------------------------------------- |
| `id_param`                                                                | *str*                                                                     | :heavy_check_mark:                                                        | Unique ID to PATCH                                                        |
| `created`                                                                 | *float*                                                                   | :heavy_check_mark:                                                        | N/A                                                                       |
| `created_by`                                                              | *str*                                                                     | :heavy_check_mark:                                                        | N/A                                                                       |
| `elements`                                                                | List[[models.DashboardElement](../../models/dashboardelement.md)]         | :heavy_check_mark:                                                        | N/A                                                                       |
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

**[models.UpdateSearchDashboardByIDResponse](../../models/updatesearchdashboardbyidresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| errors.Error     | 500              | application/json |
| errors.APIError  | 4XX, 5XX         | \*/\*            |

## delete_search_dashboard_by_id

Delete SearchDashboard

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

    res = cspf_client.dashboards.delete_search_dashboard_by_id(id="<id>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `id`                                                                | *str*                                                               | :heavy_check_mark:                                                  | Unique ID to DELETE                                                 |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.DeleteSearchDashboardByIDResponse](../../models/deletesearchdashboardbyidresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| errors.Error     | 500              | application/json |
| errors.APIError  | 4XX, 5XX         | \*/\*            |

## get_search_dashboard_acl_by_id

List accesses to SearchDashboard granted to users

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

    res = cspf_client.dashboards.get_search_dashboard_acl_by_id(id="<id>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `id`                                                                | *str*                                                               | :heavy_check_mark:                                                  | Unique ID for ACL Get                                               |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.GetSearchDashboardACLByIDResponse](../../models/getsearchdashboardaclbyidresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| errors.Error     | 500              | application/json |
| errors.APIError  | 4XX, 5XX         | \*/\*            |

## create_search_dashboard_acl_apply_by_id

Add/remove accesses to SearchDashboard for users

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

    cspf_client.dashboards.create_search_dashboard_acl_apply_by_id(id="<id>")

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
| errors.Error     | 500              | application/json |
| errors.APIError  | 4XX, 5XX         | \*/\*            |

## get_search_dashboard_acl_teams_by_id

List accesses to SearchDashboard granted to Teams

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

    res = cspf_client.dashboards.get_search_dashboard_acl_teams_by_id(id="<id>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `id`                                                                | *str*                                                               | :heavy_check_mark:                                                  | Unique ID for ACL Teams Get                                         |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.GetSearchDashboardACLTeamsByIDResponse](../../models/getsearchdashboardaclteamsbyidresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| errors.Error     | 500              | application/json |
| errors.APIError  | 4XX, 5XX         | \*/\*            |

## create_search_dashboard_acl_teams_apply_by_id

Add/remove accesses to SearchDashboard for Teams

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

    cspf_client.dashboards.create_search_dashboard_acl_teams_apply_by_id(id="<id>")

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
| errors.Error     | 500              | application/json |
| errors.APIError  | 4XX, 5XX         | \*/\*            |