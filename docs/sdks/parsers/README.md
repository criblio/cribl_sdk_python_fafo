# Parsers
(*parsers*)

## Overview

Actions related to parsers

### Available Operations

* [list_parser](#list_parser) - Get a list of Parser objects
* [create_parser](#create_parser) - Create Parser
* [get_parser_by_id](#get_parser_by_id) - Get Parser by ID
* [update_parser_by_id](#update_parser_by_id) - Update Parser
* [delete_parser_by_id](#delete_parser_by_id) - Delete Parser

## list_parser

Get a list of Parser objects

### Example Usage

```python
from cribl import Cribl
import os


with Cribl(
    bearer_auth=os.getenv("CRIBL_BEARER_AUTH", ""),
) as c_client:

    res = c_client.parsers.list_parser()

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.ListParserResponseBody](../../models/listparserresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |

## create_parser

Create Parser

### Example Usage

```python
from cribl import Cribl
import os


with Cribl(
    bearer_auth=os.getenv("CRIBL_BEARER_AUTH", ""),
) as c_client:

    res = c_client.parsers.create_parser(id="<id>", additional_properties={

    })

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                                 | Type                                                                      | Required                                                                  | Description                                                               |
| ------------------------------------------------------------------------- | ------------------------------------------------------------------------- | ------------------------------------------------------------------------- | ------------------------------------------------------------------------- |
| `id`                                                                      | *str*                                                                     | :heavy_check_mark:                                                        | N/A                                                                       |
| `lib`                                                                     | *Optional[str]*                                                           | :heavy_minus_sign:                                                        | N/A                                                                       |
| `description`                                                             | *Optional[str]*                                                           | :heavy_minus_sign:                                                        | Brief description of this parser (optional)                               |
| `tags`                                                                    | *Optional[str]*                                                           | :heavy_minus_sign:                                                        | One or more tags related to this parser (optional)                        |
| `type`                                                                    | [Optional[models.ParserLibEntryType]](../../models/parserlibentrytype.md) | :heavy_minus_sign:                                                        | Parser or formatter type to use                                           |
| `additional_properties`                                                   | Dict[str, *Any*]                                                          | :heavy_minus_sign:                                                        | N/A                                                                       |
| `retries`                                                                 | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)          | :heavy_minus_sign:                                                        | Configuration to override the default retry behavior of the client.       |

### Response

**[models.CreateParserResponseBody](../../models/createparserresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |

## get_parser_by_id

Get Parser by ID

### Example Usage

```python
from cribl import Cribl
import os


with Cribl(
    bearer_auth=os.getenv("CRIBL_BEARER_AUTH", ""),
) as c_client:

    res = c_client.parsers.get_parser_by_id(id="<id>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `id`                                                                | *str*                                                               | :heavy_check_mark:                                                  | Unique ID to GET                                                    |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.GetParserByIDResponseBody](../../models/getparserbyidresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |

## update_parser_by_id

Update Parser

### Example Usage

```python
from cribl import Cribl
import os


with Cribl(
    bearer_auth=os.getenv("CRIBL_BEARER_AUTH", ""),
) as c_client:

    res = c_client.parsers.update_parser_by_id(id_param="<value>", id="<id>", additional_properties={

    })

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                                 | Type                                                                      | Required                                                                  | Description                                                               |
| ------------------------------------------------------------------------- | ------------------------------------------------------------------------- | ------------------------------------------------------------------------- | ------------------------------------------------------------------------- |
| `id_param`                                                                | *str*                                                                     | :heavy_check_mark:                                                        | Unique ID to PATCH                                                        |
| `id`                                                                      | *str*                                                                     | :heavy_check_mark:                                                        | N/A                                                                       |
| `lib`                                                                     | *Optional[str]*                                                           | :heavy_minus_sign:                                                        | N/A                                                                       |
| `description`                                                             | *Optional[str]*                                                           | :heavy_minus_sign:                                                        | Brief description of this parser (optional)                               |
| `tags`                                                                    | *Optional[str]*                                                           | :heavy_minus_sign:                                                        | One or more tags related to this parser (optional)                        |
| `type`                                                                    | [Optional[models.ParserLibEntryType]](../../models/parserlibentrytype.md) | :heavy_minus_sign:                                                        | Parser or formatter type to use                                           |
| `additional_properties`                                                   | Dict[str, *Any*]                                                          | :heavy_minus_sign:                                                        | N/A                                                                       |
| `retries`                                                                 | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)          | :heavy_minus_sign:                                                        | Configuration to override the default retry behavior of the client.       |

### Response

**[models.UpdateParserByIDResponseBody](../../models/updateparserbyidresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |

## delete_parser_by_id

Delete Parser

### Example Usage

```python
from cribl import Cribl
import os


with Cribl(
    bearer_auth=os.getenv("CRIBL_BEARER_AUTH", ""),
) as c_client:

    res = c_client.parsers.delete_parser_by_id(id="<id>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `id`                                                                | *str*                                                               | :heavy_check_mark:                                                  | Unique ID to DELETE                                                 |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.DeleteParserByIDResponseBody](../../models/deleteparserbyidresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |