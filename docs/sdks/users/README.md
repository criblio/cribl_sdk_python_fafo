# Users
(*users*)

## Overview

Actions related to users

### Available Operations

* [list_user](#list_user) - Get a list of User objects
* [create_user](#create_user) - Create User
* [get_user_by_id](#get_user_by_id) - Get User by ID
* [update_user_by_id](#update_user_by_id) - Update User properties – admin use only
* [delete_user_by_id](#delete_user_by_id) - Delete User
* [update_user_info_by_id](#update_user_info_by_id) - Update User except for their roles
* [get_products_users_acl_by_product_and_id](#get_products_users_acl_by_product_and_id) - Get user's Access Control List
* [get_products_users_by_product](#get_products_users_by_product) - Get Users belonging to a product
* [delete_products_users_cache_by_product](#delete_products_users_cache_by_product) - Invalidate the members cache for a given product in SaaS deployment.

## list_user

Get a list of User objects

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

    res = c_client.users.list_user()

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.ListUserResponseBody](../../models/listuserresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |

## create_user

Create User

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

    res = c_client.users.create_user(disabled=False, email="Angela26@gmail.com", first="<value>", id="<id>", last="<value>", username="Caleigh.Maggio-Littel24")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `disabled`                                                          | *bool*                                                              | :heavy_check_mark:                                                  | N/A                                                                 |
| `email`                                                             | *str*                                                               | :heavy_check_mark:                                                  | N/A                                                                 |
| `first`                                                             | *str*                                                               | :heavy_check_mark:                                                  | N/A                                                                 |
| `id`                                                                | *str*                                                               | :heavy_check_mark:                                                  | N/A                                                                 |
| `last`                                                              | *str*                                                               | :heavy_check_mark:                                                  | N/A                                                                 |
| `username`                                                          | *str*                                                               | :heavy_check_mark:                                                  | N/A                                                                 |
| `current_password`                                                  | *Optional[str]*                                                     | :heavy_minus_sign:                                                  | N/A                                                                 |
| `password`                                                          | *Optional[str]*                                                     | :heavy_minus_sign:                                                  | N/A                                                                 |
| `roles`                                                             | List[*str*]                                                         | :heavy_minus_sign:                                                  | N/A                                                                 |
| `teams`                                                             | List[*str*]                                                         | :heavy_minus_sign:                                                  | N/A                                                                 |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.CreateUserResponseBody](../../models/createuserresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |

## get_user_by_id

Get User by ID

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

    res = c_client.users.get_user_by_id(id="<id>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `id`                                                                | *str*                                                               | :heavy_check_mark:                                                  | Unique ID to GET                                                    |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.GetUserByIDResponseBody](../../models/getuserbyidresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |

## update_user_by_id

Update User properties – admin use only

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

    res = c_client.users.update_user_by_id(id_param="<value>", disabled=False, email="Johanna.Kerluke33@yahoo.com", first="<value>", id="<id>", last="<value>", username="Janessa73")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `id_param`                                                          | *str*                                                               | :heavy_check_mark:                                                  | User Id                                                             |
| `disabled`                                                          | *bool*                                                              | :heavy_check_mark:                                                  | N/A                                                                 |
| `email`                                                             | *str*                                                               | :heavy_check_mark:                                                  | N/A                                                                 |
| `first`                                                             | *str*                                                               | :heavy_check_mark:                                                  | N/A                                                                 |
| `id`                                                                | *str*                                                               | :heavy_check_mark:                                                  | N/A                                                                 |
| `last`                                                              | *str*                                                               | :heavy_check_mark:                                                  | N/A                                                                 |
| `username`                                                          | *str*                                                               | :heavy_check_mark:                                                  | N/A                                                                 |
| `password`                                                          | *Optional[str]*                                                     | :heavy_minus_sign:                                                  | N/A                                                                 |
| `roles`                                                             | List[*str*]                                                         | :heavy_minus_sign:                                                  | N/A                                                                 |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.UpdateUserByIDResponseBody](../../models/updateuserbyidresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |

## delete_user_by_id

Delete User

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

    res = c_client.users.delete_user_by_id(id="<id>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `id`                                                                | *str*                                                               | :heavy_check_mark:                                                  | Unique ID to DELETE                                                 |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.DeleteUserByIDResponseBody](../../models/deleteuserbyidresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |

## update_user_info_by_id

Update User except for their roles

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

    res = c_client.users.update_user_info_by_id(id_param="<value>", disabled=False, email="Jermey_Paucek18@gmail.com", first="<value>", id="<id>", last="<value>", username="Stacy_Nitzsche8")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `id_param`                                                          | *str*                                                               | :heavy_check_mark:                                                  | User Id                                                             |
| `disabled`                                                          | *bool*                                                              | :heavy_check_mark:                                                  | N/A                                                                 |
| `email`                                                             | *str*                                                               | :heavy_check_mark:                                                  | N/A                                                                 |
| `first`                                                             | *str*                                                               | :heavy_check_mark:                                                  | N/A                                                                 |
| `id`                                                                | *str*                                                               | :heavy_check_mark:                                                  | N/A                                                                 |
| `last`                                                              | *str*                                                               | :heavy_check_mark:                                                  | N/A                                                                 |
| `username`                                                          | *str*                                                               | :heavy_check_mark:                                                  | N/A                                                                 |
| `current_password`                                                  | *Optional[str]*                                                     | :heavy_minus_sign:                                                  | N/A                                                                 |
| `password`                                                          | *Optional[str]*                                                     | :heavy_minus_sign:                                                  | N/A                                                                 |
| `roles`                                                             | List[*str*]                                                         | :heavy_minus_sign:                                                  | N/A                                                                 |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.UpdateUserInfoByIDResponseBody](../../models/updateuserinfobyidresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |

## get_products_users_acl_by_product_and_id

Get user's Access Control List

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

    res = c_client.users.get_products_users_acl_by_product_and_id(product=cribl.PathParamProduct.STREAM, id="<id>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                                                                                           | Type                                                                                                                                | Required                                                                                                                            | Description                                                                                                                         |
| ----------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------- |
| `product`                                                                                                                           | [models.PathParamProduct](../../models/pathparamproduct.md)                                                                         | :heavy_check_mark:                                                                                                                  | product by which to filter members                                                                                                  |
| `id`                                                                                                                                | *str*                                                                                                                               | :heavy_check_mark:                                                                                                                  | user id                                                                                                                             |
| `type`                                                                                                                              | [Optional[models.GetProductsUsersACLByProductAndIDQueryParamType]](../../models/getproductsusersaclbyproductandidqueryparamtype.md) | :heavy_minus_sign:                                                                                                                  | resource type by which to filter access levels                                                                                      |
| `retries`                                                                                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)                                                                    | :heavy_minus_sign:                                                                                                                  | Configuration to override the default retry behavior of the client.                                                                 |

### Response

**[models.GetProductsUsersACLByProductAndIDResponseBody](../../models/getproductsusersaclbyproductandidresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |

## get_products_users_by_product

Get Users belonging to a product

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

    res = c_client.users.get_products_users_by_product(product=cribl.GetProductsUsersByProductPathParamProduct.LAKE)

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                                                                     | Type                                                                                                          | Required                                                                                                      | Description                                                                                                   |
| ------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------- |
| `product`                                                                                                     | [models.GetProductsUsersByProductPathParamProduct](../../models/getproductsusersbyproductpathparamproduct.md) | :heavy_check_mark:                                                                                            | product by which to filter members                                                                            |
| `group_id`                                                                                                    | *Optional[str]*                                                                                               | :heavy_minus_sign:                                                                                            | filter to specific group by groupId                                                                           |
| `retries`                                                                                                     | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)                                              | :heavy_minus_sign:                                                                                            | Configuration to override the default retry behavior of the client.                                           |

### Response

**[models.GetProductsUsersByProductResponseBody](../../models/getproductsusersbyproductresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |

## delete_products_users_cache_by_product

Invalidate the members cache for a given product in SaaS deployment.

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

    res = c_client.users.delete_products_users_cache_by_product(product=cribl.DeleteProductsUsersCacheByProductPathParamProduct.STREAM)

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                                                                                     | Type                                                                                                                          | Required                                                                                                                      | Description                                                                                                                   |
| ----------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------- |
| `product`                                                                                                                     | [models.DeleteProductsUsersCacheByProductPathParamProduct](../../models/deleteproductsuserscachebyproductpathparamproduct.md) | :heavy_check_mark:                                                                                                            | product by which to filter members                                                                                            |
| `retries`                                                                                                                     | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)                                                              | :heavy_minus_sign:                                                                                                            | Configuration to override the default retry behavior of the client.                                                           |

### Response

**[models.DeleteProductsUsersCacheByProductResponseBody](../../models/deleteproductsuserscachebyproductresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |