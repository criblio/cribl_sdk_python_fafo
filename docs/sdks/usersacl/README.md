# UsersACL
(*users_acl*)

## Overview

Actions related to Users ACL

### Available Operations

* [get_dataset_acl_by_id](#get_dataset_acl_by_id) - Get Dataset ACL
* [create_dataset_acl_apply_by_id](#create_dataset_acl_apply_by_id) - Modify Dataset ACL
* [get_search_dashboard_acl_by_id](#get_search_dashboard_acl_by_id) - Get SearchDashboard ACL
* [create_search_dashboard_acl_apply_by_id](#create_search_dashboard_acl_apply_by_id) - Modify SearchDashboard ACL
* [get_project_acl_by_id](#get_project_acl_by_id) - Get Project ACL
* [create_project_acl_apply_by_id](#create_project_acl_apply_by_id) - Modify Project ACL
* [get_groups_acl_by_id](#get_groups_acl_by_id) - ACL of members with permissions for resources in this Group

## get_dataset_acl_by_id

List accesses to Dataset granted to users

### Example Usage

```python
from cribl import Cribl
import os


with Cribl(
    server_url="https://api.example.com",
    bearer_auth=os.getenv("CRIBL_BEARER_AUTH", ""),
) as c_client:

    res = c_client.users_acl.get_dataset_acl_by_id(id="<id>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `id`                                                                | *str*                                                               | :heavy_check_mark:                                                  | Unique ID for ACL Get                                               |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.GetDatasetACLByIDResponseBody](../../models/getdatasetaclbyidresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |

## create_dataset_acl_apply_by_id

Add/remove accesses to Dataset for users

### Example Usage

```python
from cribl import Cribl
import os


with Cribl(
    server_url="https://api.example.com",
    bearer_auth=os.getenv("CRIBL_BEARER_AUTH", ""),
) as c_client:

    c_client.users_acl.create_dataset_acl_apply_by_id(id="<id>")

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

## get_search_dashboard_acl_by_id

List accesses to SearchDashboard granted to users

### Example Usage

```python
from cribl import Cribl
import os


with Cribl(
    server_url="https://api.example.com",
    bearer_auth=os.getenv("CRIBL_BEARER_AUTH", ""),
) as c_client:

    res = c_client.users_acl.get_search_dashboard_acl_by_id(id="<id>")

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
from cribl import Cribl
import os


with Cribl(
    server_url="https://api.example.com",
    bearer_auth=os.getenv("CRIBL_BEARER_AUTH", ""),
) as c_client:

    c_client.users_acl.create_search_dashboard_acl_apply_by_id(id="<id>")

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

## get_project_acl_by_id

List accesses to Project granted to users

### Example Usage

```python
from cribl import Cribl
import os


with Cribl(
    server_url="https://api.example.com",
    bearer_auth=os.getenv("CRIBL_BEARER_AUTH", ""),
) as c_client:

    res = c_client.users_acl.get_project_acl_by_id(id="<id>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `id`                                                                | *str*                                                               | :heavy_check_mark:                                                  | Unique ID for ACL Get                                               |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.GetProjectACLByIDResponseBody](../../models/getprojectaclbyidresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |

## create_project_acl_apply_by_id

Add/remove accesses to Project for users

### Example Usage

```python
from cribl import Cribl
import os


with Cribl(
    server_url="https://api.example.com",
    bearer_auth=os.getenv("CRIBL_BEARER_AUTH", ""),
) as c_client:

    c_client.users_acl.create_project_acl_apply_by_id(id="<id>")

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

## get_groups_acl_by_id

ACL of members with permissions for resources in this Group

### Example Usage

```python
from cribl import Cribl
import os


with Cribl(
    server_url="https://api.example.com",
    bearer_auth=os.getenv("CRIBL_BEARER_AUTH", ""),
) as c_client:

    res = c_client.users_acl.get_groups_acl_by_id(id="<id>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                                                         | Type                                                                                              | Required                                                                                          | Description                                                                                       |
| ------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------- |
| `id`                                                                                              | *str*                                                                                             | :heavy_check_mark:                                                                                | Group id                                                                                          |
| `type`                                                                                            | [Optional[models.GetGroupsACLByIDQueryParamType]](../../models/getgroupsaclbyidqueryparamtype.md) | :heavy_minus_sign:                                                                                | resource type by which to filter access levels                                                    |
| `retries`                                                                                         | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)                                  | :heavy_minus_sign:                                                                                | Configuration to override the default retry behavior of the client.                               |

### Response

**[models.GetGroupsACLByIDResponseBody](../../models/getgroupsaclbyidresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |