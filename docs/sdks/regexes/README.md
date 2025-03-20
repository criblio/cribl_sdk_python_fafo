# Regexes
(*regexes*)

## Overview

Actions related to regular expressions

### Available Operations

* [list_regex_lib_entry](#list_regex_lib_entry) - Get a list of RegexLibEntry objects
* [create_regex_lib_entry](#create_regex_lib_entry) - Create RegexLibEntry
* [get_regex_lib_entry_by_id](#get_regex_lib_entry_by_id) - Get RegexLibEntry by ID
* [update_regex_lib_entry_by_id](#update_regex_lib_entry_by_id) - Update RegexLibEntry
* [delete_regex_lib_entry_by_id](#delete_regex_lib_entry_by_id) - Delete RegexLibEntry

## list_regex_lib_entry

Get a list of RegexLibEntry objects

### Example Usage

```python
from cribl import Cribl
import os


with Cribl(
    server_url="https://api.example.com",
    bearer_auth=os.getenv("CRIBL_BEARER_AUTH", ""),
) as c_client:

    res = c_client.regexes.list_regex_lib_entry()

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.ListRegexLibEntryResponseBody](../../models/listregexlibentryresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |

## create_regex_lib_entry

Create RegexLibEntry

### Example Usage

```python
from cribl import Cribl
import os


with Cribl(
    server_url="https://api.example.com",
    bearer_auth=os.getenv("CRIBL_BEARER_AUTH", ""),
) as c_client:

    res = c_client.regexes.create_regex_lib_entry(id="<id>", regex="<value>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `id`                                                                | *str*                                                               | :heavy_check_mark:                                                  | N/A                                                                 |
| `regex`                                                             | *str*                                                               | :heavy_check_mark:                                                  | N/A                                                                 |
| `lib`                                                               | *Optional[str]*                                                     | :heavy_minus_sign:                                                  | N/A                                                                 |
| `description`                                                       | *Optional[str]*                                                     | :heavy_minus_sign:                                                  | Brief description of this regex (optional)                          |
| `sample_data`                                                       | *Optional[str]*                                                     | :heavy_minus_sign:                                                  | Sample data for this regex (optional)                               |
| `tags`                                                              | *Optional[str]*                                                     | :heavy_minus_sign:                                                  | One or more tags related to this regex (optional)                   |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.CreateRegexLibEntryResponseBody](../../models/createregexlibentryresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |

## get_regex_lib_entry_by_id

Get RegexLibEntry by ID

### Example Usage

```python
from cribl import Cribl
import os


with Cribl(
    server_url="https://api.example.com",
    bearer_auth=os.getenv("CRIBL_BEARER_AUTH", ""),
) as c_client:

    res = c_client.regexes.get_regex_lib_entry_by_id(id="<id>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `id`                                                                | *str*                                                               | :heavy_check_mark:                                                  | Unique ID to GET                                                    |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.GetRegexLibEntryByIDResponseBody](../../models/getregexlibentrybyidresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |

## update_regex_lib_entry_by_id

Update RegexLibEntry

### Example Usage

```python
from cribl import Cribl
import os


with Cribl(
    server_url="https://api.example.com",
    bearer_auth=os.getenv("CRIBL_BEARER_AUTH", ""),
) as c_client:

    res = c_client.regexes.update_regex_lib_entry_by_id(id_param="<value>", id="<id>", regex="<value>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `id_param`                                                          | *str*                                                               | :heavy_check_mark:                                                  | Unique ID to PATCH                                                  |
| `id`                                                                | *str*                                                               | :heavy_check_mark:                                                  | N/A                                                                 |
| `regex`                                                             | *str*                                                               | :heavy_check_mark:                                                  | N/A                                                                 |
| `lib`                                                               | *Optional[str]*                                                     | :heavy_minus_sign:                                                  | N/A                                                                 |
| `description`                                                       | *Optional[str]*                                                     | :heavy_minus_sign:                                                  | Brief description of this regex (optional)                          |
| `sample_data`                                                       | *Optional[str]*                                                     | :heavy_minus_sign:                                                  | Sample data for this regex (optional)                               |
| `tags`                                                              | *Optional[str]*                                                     | :heavy_minus_sign:                                                  | One or more tags related to this regex (optional)                   |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.UpdateRegexLibEntryByIDResponseBody](../../models/updateregexlibentrybyidresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |

## delete_regex_lib_entry_by_id

Delete RegexLibEntry

### Example Usage

```python
from cribl import Cribl
import os


with Cribl(
    server_url="https://api.example.com",
    bearer_auth=os.getenv("CRIBL_BEARER_AUTH", ""),
) as c_client:

    res = c_client.regexes.delete_regex_lib_entry_by_id(id="<id>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `id`                                                                | *str*                                                               | :heavy_check_mark:                                                  | Unique ID to DELETE                                                 |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.DeleteRegexLibEntryByIDResponseBody](../../models/deleteregexlibentrybyidresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |