# Banners
(*banners*)

## Overview

Actions related to Banners

### Available Operations

* [list_banner_message](#list_banner_message) - Get a list of BannerMessage objects
* [create_banner_message](#create_banner_message) - Create BannerMessage
* [get_banner_message_by_id](#get_banner_message_by_id) - Get BannerMessage by ID
* [update_banner_message_by_id](#update_banner_message_by_id) - Update BannerMessage
* [delete_banner_message_by_id](#delete_banner_message_by_id) - Delete BannerMessage

## list_banner_message

Get a list of BannerMessage objects

### Example Usage

```python
from cribl import Cribl
import os


with Cribl(
    server_url="https://api.example.com",
    bearer_auth=os.getenv("CRIBL_BEARER_AUTH", ""),
) as c_client:

    res = c_client.banners.list_banner_message()

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.ListBannerMessageResponseBody](../../models/listbannermessageresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |

## create_banner_message

Create BannerMessage

### Example Usage

```python
import cribl
from cribl import Cribl
import os


with Cribl(
    server_url="https://api.example.com",
    bearer_auth=os.getenv("CRIBL_BEARER_AUTH", ""),
) as c_client:

    res = c_client.banners.create_banner_message(enabled=False, type_=cribl.BannerType.CUSTOM, theme="<value>", message="<value>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                                                                                                                    | Type                                                                                                                                                         | Required                                                                                                                                                     | Description                                                                                                                                                  |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `enabled`                                                                                                                                                    | *bool*                                                                                                                                                       | :heavy_check_mark:                                                                                                                                           | Show a banner on top of all pages                                                                                                                            |
| `type`                                                                                                                                                       | [models.BannerType](../../models/bannertype.md)                                                                                                              | :heavy_check_mark:                                                                                                                                           | N/A                                                                                                                                                          |
| `theme`                                                                                                                                                      | *str*                                                                                                                                                        | :heavy_check_mark:                                                                                                                                           | N/A                                                                                                                                                          |
| `message`                                                                                                                                                    | *str*                                                                                                                                                        | :heavy_check_mark:                                                                                                                                           | Enter a message to display to all your Organization's users, across all Cribl products. Limited to one line and 100 characters; will be truncated as needed. |
| `id`                                                                                                                                                         | *Optional[str]*                                                                                                                                              | :heavy_minus_sign:                                                                                                                                           | N/A                                                                                                                                                          |
| `created`                                                                                                                                                    | *Optional[float]*                                                                                                                                            | :heavy_minus_sign:                                                                                                                                           | Time created                                                                                                                                                 |
| `invert_font_color`                                                                                                                                          | *Optional[bool]*                                                                                                                                             | :heavy_minus_sign:                                                                                                                                           | N/A                                                                                                                                                          |
| `link`                                                                                                                                                       | *Optional[str]*                                                                                                                                              | :heavy_minus_sign:                                                                                                                                           | Optionally, provide a URL to append to the message                                                                                                           |
| `link_display`                                                                                                                                               | *Optional[str]*                                                                                                                                              | :heavy_minus_sign:                                                                                                                                           | Optionally, display your link with a short text label instead of the raw URL (100-character limit)                                                           |
| `custom_themes`                                                                                                                                              | List[*str*]                                                                                                                                                  | :heavy_minus_sign:                                                                                                                                           | N/A                                                                                                                                                          |
| `retries`                                                                                                                                                    | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)                                                                                             | :heavy_minus_sign:                                                                                                                                           | Configuration to override the default retry behavior of the client.                                                                                          |

### Response

**[models.CreateBannerMessageResponseBody](../../models/createbannermessageresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |

## get_banner_message_by_id

Get BannerMessage by ID

### Example Usage

```python
from cribl import Cribl
import os


with Cribl(
    server_url="https://api.example.com",
    bearer_auth=os.getenv("CRIBL_BEARER_AUTH", ""),
) as c_client:

    res = c_client.banners.get_banner_message_by_id(id="<id>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `id`                                                                | *str*                                                               | :heavy_check_mark:                                                  | Unique ID to GET                                                    |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.GetBannerMessageByIDResponseBody](../../models/getbannermessagebyidresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |

## update_banner_message_by_id

Update BannerMessage

### Example Usage

```python
import cribl
from cribl import Cribl
import os


with Cribl(
    server_url="https://api.example.com",
    bearer_auth=os.getenv("CRIBL_BEARER_AUTH", ""),
) as c_client:

    res = c_client.banners.update_banner_message_by_id(id_param="<value>", enabled=True, type_=cribl.BannerType.SYSTEM, theme="<value>", message="<value>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                                                                                                                    | Type                                                                                                                                                         | Required                                                                                                                                                     | Description                                                                                                                                                  |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `id_param`                                                                                                                                                   | *str*                                                                                                                                                        | :heavy_check_mark:                                                                                                                                           | Unique ID to PATCH                                                                                                                                           |
| `enabled`                                                                                                                                                    | *bool*                                                                                                                                                       | :heavy_check_mark:                                                                                                                                           | Show a banner on top of all pages                                                                                                                            |
| `type`                                                                                                                                                       | [models.BannerType](../../models/bannertype.md)                                                                                                              | :heavy_check_mark:                                                                                                                                           | N/A                                                                                                                                                          |
| `theme`                                                                                                                                                      | *str*                                                                                                                                                        | :heavy_check_mark:                                                                                                                                           | N/A                                                                                                                                                          |
| `message`                                                                                                                                                    | *str*                                                                                                                                                        | :heavy_check_mark:                                                                                                                                           | Enter a message to display to all your Organization's users, across all Cribl products. Limited to one line and 100 characters; will be truncated as needed. |
| `id`                                                                                                                                                         | *Optional[str]*                                                                                                                                              | :heavy_minus_sign:                                                                                                                                           | N/A                                                                                                                                                          |
| `created`                                                                                                                                                    | *Optional[float]*                                                                                                                                            | :heavy_minus_sign:                                                                                                                                           | Time created                                                                                                                                                 |
| `invert_font_color`                                                                                                                                          | *Optional[bool]*                                                                                                                                             | :heavy_minus_sign:                                                                                                                                           | N/A                                                                                                                                                          |
| `link`                                                                                                                                                       | *Optional[str]*                                                                                                                                              | :heavy_minus_sign:                                                                                                                                           | Optionally, provide a URL to append to the message                                                                                                           |
| `link_display`                                                                                                                                               | *Optional[str]*                                                                                                                                              | :heavy_minus_sign:                                                                                                                                           | Optionally, display your link with a short text label instead of the raw URL (100-character limit)                                                           |
| `custom_themes`                                                                                                                                              | List[*str*]                                                                                                                                                  | :heavy_minus_sign:                                                                                                                                           | N/A                                                                                                                                                          |
| `retries`                                                                                                                                                    | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)                                                                                             | :heavy_minus_sign:                                                                                                                                           | Configuration to override the default retry behavior of the client.                                                                                          |

### Response

**[models.UpdateBannerMessageByIDResponseBody](../../models/updatebannermessagebyidresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |

## delete_banner_message_by_id

Delete BannerMessage

### Example Usage

```python
from cribl import Cribl
import os


with Cribl(
    server_url="https://api.example.com",
    bearer_auth=os.getenv("CRIBL_BEARER_AUTH", ""),
) as c_client:

    res = c_client.banners.delete_banner_message_by_id(id="<id>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `id`                                                                | *str*                                                               | :heavy_check_mark:                                                  | Unique ID to DELETE                                                 |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.DeleteBannerMessageByIDResponseBody](../../models/deletebannermessagebyidresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |