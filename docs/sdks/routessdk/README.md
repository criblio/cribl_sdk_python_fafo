# RoutesSDK
(*routes*)

## Overview

Actions related to Routes

### Available Operations

* [list_routes](#list_routes) - Get a list of Routes objects
* [get_routes_by_id](#get_routes_by_id) - Get Routes by ID
* [update_routes_by_id](#update_routes_by_id) - Update Routes
* [create_routes_append_by_id](#create_routes_append_by_id) - Appends routes to the end of the routing table
* [get_routes_by_pack](#get_routes_by_pack) - Get a list of Routes objects within a Pack
* [get_routes_by_pack_and_id](#get_routes_by_pack_and_id) - Get Routes by ID within a Pack
* [update_routes_by_pack_and_id](#update_routes_by_pack_and_id) - Update Routes within a Pack
* [create_routes_append_by_pack_and_id](#create_routes_append_by_pack_and_id) - Appends routes to the end of the routing table within a Pack

## list_routes

Get a list of Routes objects

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

    res = c_client.routes.list_routes()

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.ListRoutesResponseBody](../../models/listroutesresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |

## get_routes_by_id

Get Routes by ID

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

    res = c_client.routes.get_routes_by_id(id="<id>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `id`                                                                | *str*                                                               | :heavy_check_mark:                                                  | Unique ID to GET                                                    |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.GetRoutesByIDResponseBody](../../models/getroutesbyidresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |

## update_routes_by_id

Update Routes

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

    res = c_client.routes.update_routes_by_id(id_param="<value>", routes=[
        cribl.RoutesRouteInput(
            name="<value>",
            pipeline="<value>",
        ),
        cribl.RoutesRouteInput(
            name="<value>",
            pipeline="<value>",
        ),
    ])

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `id_param`                                                          | *str*                                                               | :heavy_check_mark:                                                  | Unique ID to PATCH                                                  |
| `routes`                                                            | List[[models.RoutesRouteInput](../../models/routesrouteinput.md)]   | :heavy_check_mark:                                                  | Pipeline routing rules                                              |
| `id`                                                                | *Optional[str]*                                                     | :heavy_minus_sign:                                                  | Routes ID                                                           |
| `groups`                                                            | Dict[str, [models.GroupsModel](../../models/groupsmodel.md)]        | :heavy_minus_sign:                                                  | N/A                                                                 |
| `comments`                                                          | List[[models.Comments](../../models/comments.md)]                   | :heavy_minus_sign:                                                  | Comments                                                            |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.UpdateRoutesByIDResponseBody](../../models/updateroutesbyidresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |

## create_routes_append_by_id

Appends routes to the end of the routing table

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

    res = c_client.routes.create_routes_append_by_id(id="<id>", request_body=[
        {
            "final": True,
            "id": "<id>",
            "name": "<value>",
            "pipeline": "<value>",
        },
        {
            "final": True,
            "id": "<id>",
            "name": "<value>",
            "pipeline": "<value>",
        },
        {
            "final": True,
            "id": "<id>",
            "name": "<value>",
            "pipeline": "<value>",
        },
    ])

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                                         | Type                                                                              | Required                                                                          | Description                                                                       |
| --------------------------------------------------------------------------------- | --------------------------------------------------------------------------------- | --------------------------------------------------------------------------------- | --------------------------------------------------------------------------------- |
| `id`                                                                              | *str*                                                                             | :heavy_check_mark:                                                                | the route table to be appended to - currently default is the only supported value |
| `request_body`                                                                    | List[[models.RouteConf](../../models/routeconf.md)]                               | :heavy_check_mark:                                                                | RouteDefinitions object                                                           |
| `retries`                                                                         | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)                  | :heavy_minus_sign:                                                                | Configuration to override the default retry behavior of the client.               |

### Response

**[models.CreateRoutesAppendByIDResponseBody](../../models/createroutesappendbyidresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |

## get_routes_by_pack

Get a list of Routes objects within a Pack

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

    res = c_client.routes.get_routes_by_pack(pack="<value>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `pack`                                                              | *str*                                                               | :heavy_check_mark:                                                  | pack ID to GET                                                      |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.GetRoutesByPackResponseBody](../../models/getroutesbypackresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |

## get_routes_by_pack_and_id

Get Routes by ID within a Pack

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

    res = c_client.routes.get_routes_by_pack_and_id(id="<id>", pack="<value>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `id`                                                                | *str*                                                               | :heavy_check_mark:                                                  | Unique ID to GET for pack                                           |
| `pack`                                                              | *str*                                                               | :heavy_check_mark:                                                  | pack ID to GET                                                      |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.GetRoutesByPackAndIDResponseBody](../../models/getroutesbypackandidresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |

## update_routes_by_pack_and_id

Update Routes within a Pack

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

    res = c_client.routes.update_routes_by_pack_and_id(id_param="<value>", pack="<value>", routes=[
        cribl.RoutesRouteInput(
            name="<value>",
            pipeline="<value>",
        ),
        cribl.RoutesRouteInput(
            name="<value>",
            pipeline="<value>",
        ),
        cribl.RoutesRouteInput(
            name="<value>",
            pipeline="<value>",
        ),
    ])

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `id_param`                                                          | *str*                                                               | :heavy_check_mark:                                                  | Unique ID to PATCH for pack                                         |
| `pack`                                                              | *str*                                                               | :heavy_check_mark:                                                  | pack ID to PATCH                                                    |
| `routes`                                                            | List[[models.RoutesRouteInput](../../models/routesrouteinput.md)]   | :heavy_check_mark:                                                  | Pipeline routing rules                                              |
| `id`                                                                | *Optional[str]*                                                     | :heavy_minus_sign:                                                  | Routes ID                                                           |
| `groups`                                                            | Dict[str, [models.GroupsModel](../../models/groupsmodel.md)]        | :heavy_minus_sign:                                                  | N/A                                                                 |
| `comments`                                                          | List[[models.Comments](../../models/comments.md)]                   | :heavy_minus_sign:                                                  | Comments                                                            |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.UpdateRoutesByPackAndIDResponseBody](../../models/updateroutesbypackandidresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |

## create_routes_append_by_pack_and_id

Appends routes to the end of the routing table within a Pack

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

    res = c_client.routes.create_routes_append_by_pack_and_id(id="<id>", pack="<value>", request_body=[
        {
            "final": False,
            "id": "<id>",
            "name": "<value>",
            "pipeline": "<value>",
        },
        {
            "final": True,
            "id": "<id>",
            "name": "<value>",
            "pipeline": "<value>",
        },
        {
            "final": True,
            "id": "<id>",
            "name": "<value>",
            "pipeline": "<value>",
        },
    ])

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                                                  | Type                                                                                       | Required                                                                                   | Description                                                                                |
| ------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------ |
| `id`                                                                                       | *str*                                                                                      | :heavy_check_mark:                                                                         | the route table to be appended to - currently default is the only supported value for pack |
| `pack`                                                                                     | *str*                                                                                      | :heavy_check_mark:                                                                         | pack ID to POST                                                                            |
| `request_body`                                                                             | List[[models.RouteConf](../../models/routeconf.md)]                                        | :heavy_check_mark:                                                                         | RouteDefinitions object                                                                    |
| `retries`                                                                                  | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)                           | :heavy_minus_sign:                                                                         | Configuration to override the default retry behavior of the client.                        |

### Response

**[models.CreateRoutesAppendByPackAndIDResponseBody](../../models/createroutesappendbypackandidresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |