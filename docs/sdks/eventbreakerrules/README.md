# EventBreakerRules
(*event_breaker_rules*)

## Overview

Actions related to Event Breaker rules

### Available Operations

* [list_event_breaker_ruleset](#list_event_breaker_ruleset) - Get a list of Event Breaker Ruleset objects
* [create_event_breaker_ruleset](#create_event_breaker_ruleset) - Create Event Breaker Ruleset
* [get_event_breaker_ruleset_by_id](#get_event_breaker_ruleset_by_id) - Get Event Breaker Ruleset by ID
* [update_event_breaker_ruleset_by_id](#update_event_breaker_ruleset_by_id) - Update Event Breaker Ruleset
* [delete_event_breaker_ruleset_by_id](#delete_event_breaker_ruleset_by_id) - Delete Event Breaker Ruleset

## list_event_breaker_ruleset

Get a list of Event Breaker Ruleset objects

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

    res = cspf_client.event_breaker_rules.list_event_breaker_ruleset()

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.ListEventBreakerRulesetResponse](../../models/listeventbreakerrulesetresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| errors.Error     | 500              | application/json |
| errors.APIError  | 4XX, 5XX         | \*/\*            |

## create_event_breaker_ruleset

Create Event Breaker Ruleset

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

    res = cspf_client.event_breaker_rules.create_event_breaker_ruleset(id="<id>", lib=models.Library.CUSTOM, min_raw_length=256)

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                                       | Type                                                                            | Required                                                                        | Description                                                                     |
| ------------------------------------------------------------------------------- | ------------------------------------------------------------------------------- | ------------------------------------------------------------------------------- | ------------------------------------------------------------------------------- |
| `id`                                                                            | *str*                                                                           | :heavy_check_mark:                                                              | N/A                                                                             |
| `lib`                                                                           | [Optional[models.Library]](../../models/library.md)                             | :heavy_minus_sign:                                                              | N/A                                                                             |
| `description`                                                                   | *Optional[str]*                                                                 | :heavy_minus_sign:                                                              | N/A                                                                             |
| `tags`                                                                          | *Optional[str]*                                                                 | :heavy_minus_sign:                                                              | N/A                                                                             |
| `min_raw_length`                                                                | *Optional[float]*                                                               | :heavy_minus_sign:                                                              | The  minimum number of characters in _raw to determine which rule to use        |
| `rules`                                                                         | List[[models.EventBreakerRulesetRule](../../models/eventbreakerrulesetrule.md)] | :heavy_minus_sign:                                                              | A list of rules that will be applied, in order, to the input data stream        |
| `retries`                                                                       | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)                | :heavy_minus_sign:                                                              | Configuration to override the default retry behavior of the client.             |

### Response

**[models.CreateEventBreakerRulesetResponse](../../models/createeventbreakerrulesetresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| errors.Error     | 500              | application/json |
| errors.APIError  | 4XX, 5XX         | \*/\*            |

## get_event_breaker_ruleset_by_id

Get Event Breaker Ruleset by ID

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

    res = cspf_client.event_breaker_rules.get_event_breaker_ruleset_by_id(id="<id>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `id`                                                                | *str*                                                               | :heavy_check_mark:                                                  | Unique ID to GET                                                    |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.GetEventBreakerRulesetByIDResponse](../../models/geteventbreakerrulesetbyidresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| errors.Error     | 500              | application/json |
| errors.APIError  | 4XX, 5XX         | \*/\*            |

## update_event_breaker_ruleset_by_id

Update Event Breaker Ruleset

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

    res = cspf_client.event_breaker_rules.update_event_breaker_ruleset_by_id(id_param="<value>", id="<id>", lib=models.Library.CUSTOM, min_raw_length=256)

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                                       | Type                                                                            | Required                                                                        | Description                                                                     |
| ------------------------------------------------------------------------------- | ------------------------------------------------------------------------------- | ------------------------------------------------------------------------------- | ------------------------------------------------------------------------------- |
| `id_param`                                                                      | *str*                                                                           | :heavy_check_mark:                                                              | Unique ID to PATCH                                                              |
| `id`                                                                            | *str*                                                                           | :heavy_check_mark:                                                              | N/A                                                                             |
| `lib`                                                                           | [Optional[models.Library]](../../models/library.md)                             | :heavy_minus_sign:                                                              | N/A                                                                             |
| `description`                                                                   | *Optional[str]*                                                                 | :heavy_minus_sign:                                                              | N/A                                                                             |
| `tags`                                                                          | *Optional[str]*                                                                 | :heavy_minus_sign:                                                              | N/A                                                                             |
| `min_raw_length`                                                                | *Optional[float]*                                                               | :heavy_minus_sign:                                                              | The  minimum number of characters in _raw to determine which rule to use        |
| `rules`                                                                         | List[[models.EventBreakerRulesetRule](../../models/eventbreakerrulesetrule.md)] | :heavy_minus_sign:                                                              | A list of rules that will be applied, in order, to the input data stream        |
| `retries`                                                                       | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)                | :heavy_minus_sign:                                                              | Configuration to override the default retry behavior of the client.             |

### Response

**[models.UpdateEventBreakerRulesetByIDResponse](../../models/updateeventbreakerrulesetbyidresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| errors.Error     | 500              | application/json |
| errors.APIError  | 4XX, 5XX         | \*/\*            |

## delete_event_breaker_ruleset_by_id

Delete Event Breaker Ruleset

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

    res = cspf_client.event_breaker_rules.delete_event_breaker_ruleset_by_id(id="<id>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `id`                                                                | *str*                                                               | :heavy_check_mark:                                                  | Unique ID to DELETE                                                 |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.DeleteEventBreakerRulesetByIDResponse](../../models/deleteeventbreakerrulesetbyidresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| errors.Error     | 500              | application/json |
| errors.APIError  | 4XX, 5XX         | \*/\*            |