# Policies
(*policies*)

## Overview

Actions related to Policies

### Available Operations

* [list_policy_rule](#list_policy_rule) - Get a list of PolicyRule objects
* [create_policy_rule](#create_policy_rule) - Create PolicyRule
* [get_policy_rule_by_id](#get_policy_rule_by_id) - Get PolicyRule by ID
* [update_policy_rule_by_id](#update_policy_rule_by_id) - Update PolicyRule
* [delete_policy_rule_by_id](#delete_policy_rule_by_id) - Delete PolicyRule

## list_policy_rule

Get a list of PolicyRule objects

### Example Usage

```python
from cribl import Cribl
import os


with Cribl(
    bearer_auth=os.getenv("CRIBL_BEARER_AUTH", ""),
) as c_client:

    res = c_client.policies.list_policy_rule()

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.ListPolicyRuleResponseBody](../../models/listpolicyruleresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |

## create_policy_rule

Create PolicyRule

### Example Usage

```python
from cribl import Cribl
import os


with Cribl(
    bearer_auth=os.getenv("CRIBL_BEARER_AUTH", ""),
) as c_client:

    res = c_client.policies.create_policy_rule(id="<id>", template=[
        "<value>",
        "<value>",
        "<value>",
    ])

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `id`                                                                | *str*                                                               | :heavy_check_mark:                                                  | N/A                                                                 |
| `template`                                                          | List[*str*]                                                         | :heavy_check_mark:                                                  | N/A                                                                 |
| `args`                                                              | List[*str*]                                                         | :heavy_minus_sign:                                                  | N/A                                                                 |
| `description`                                                       | *Optional[str]*                                                     | :heavy_minus_sign:                                                  | N/A                                                                 |
| `title`                                                             | *Optional[str]*                                                     | :heavy_minus_sign:                                                  | N/A                                                                 |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.CreatePolicyRuleResponseBody](../../models/createpolicyruleresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |

## get_policy_rule_by_id

Get PolicyRule by ID

### Example Usage

```python
from cribl import Cribl
import os


with Cribl(
    bearer_auth=os.getenv("CRIBL_BEARER_AUTH", ""),
) as c_client:

    res = c_client.policies.get_policy_rule_by_id(id="<id>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `id`                                                                | *str*                                                               | :heavy_check_mark:                                                  | Unique ID to GET                                                    |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.GetPolicyRuleByIDResponseBody](../../models/getpolicyrulebyidresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |

## update_policy_rule_by_id

Update PolicyRule

### Example Usage

```python
from cribl import Cribl
import os


with Cribl(
    bearer_auth=os.getenv("CRIBL_BEARER_AUTH", ""),
) as c_client:

    res = c_client.policies.update_policy_rule_by_id(id_param="<value>", id="<id>", template=[
        "<value>",
        "<value>",
        "<value>",
    ])

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `id_param`                                                          | *str*                                                               | :heavy_check_mark:                                                  | Unique ID to PATCH                                                  |
| `id`                                                                | *str*                                                               | :heavy_check_mark:                                                  | N/A                                                                 |
| `template`                                                          | List[*str*]                                                         | :heavy_check_mark:                                                  | N/A                                                                 |
| `args`                                                              | List[*str*]                                                         | :heavy_minus_sign:                                                  | N/A                                                                 |
| `description`                                                       | *Optional[str]*                                                     | :heavy_minus_sign:                                                  | N/A                                                                 |
| `title`                                                             | *Optional[str]*                                                     | :heavy_minus_sign:                                                  | N/A                                                                 |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.UpdatePolicyRuleByIDResponseBody](../../models/updatepolicyrulebyidresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |

## delete_policy_rule_by_id

Delete PolicyRule

### Example Usage

```python
from cribl import Cribl
import os


with Cribl(
    bearer_auth=os.getenv("CRIBL_BEARER_AUTH", ""),
) as c_client:

    res = c_client.policies.delete_policy_rule_by_id(id="<id>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `id`                                                                | *str*                                                               | :heavy_check_mark:                                                  | Unique ID to DELETE                                                 |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.DeletePolicyRuleByIDResponseBody](../../models/deletepolicyrulebyidresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |