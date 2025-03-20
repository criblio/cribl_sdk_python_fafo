# ClickHouse
(*click_house*)

## Overview

Actions related to ClickHouse

### Available Operations

* [create_output_click_house_describe_table](#create_output_click_house_describe_table) - Retrieve the description of the configured ClickHouse table

## create_output_click_house_describe_table

Retrieve the description of the configured ClickHouse table

### Example Usage

```python
import cribl
from cribl import Cribl
import os


with Cribl(
    server_url="https://api.example.com",
    bearer_auth=os.getenv("CRIBL_BEARER_AUTH", ""),
) as c_client:

    res = c_client.click_house.create_output_click_house_describe_table(async_inserts=True, database="<value>", flush_period_sec=2136.91, format_=cribl.Format.JSON_EACH_ROW, load_balanced=True, mapping_type=cribl.MappingType.AUTOMATIC, table_name="<value>", url="https://ill-tune-up.info/")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                                             | Type                                                                                  | Required                                                                              | Description                                                                           |
| ------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------- |
| `async_inserts`                                                                       | *bool*                                                                                | :heavy_check_mark:                                                                    | N/A                                                                                   |
| `database`                                                                            | *str*                                                                                 | :heavy_check_mark:                                                                    | N/A                                                                                   |
| `flush_period_sec`                                                                    | *float*                                                                               | :heavy_check_mark:                                                                    | N/A                                                                                   |
| `format_`                                                                             | [models.Format](../../models/format_.md)                                              | :heavy_check_mark:                                                                    | N/A                                                                                   |
| `load_balanced`                                                                       | *bool*                                                                                | :heavy_check_mark:                                                                    | N/A                                                                                   |
| `mapping_type`                                                                        | [models.MappingType](../../models/mappingtype.md)                                     | :heavy_check_mark:                                                                    | N/A                                                                                   |
| `table_name`                                                                          | *str*                                                                                 | :heavy_check_mark:                                                                    | N/A                                                                                   |
| `url`                                                                                 | *str*                                                                                 | :heavy_check_mark:                                                                    | N/A                                                                                   |
| `auth`                                                                                | [Optional[models.HTTPOutAuthConfig]](../../models/httpoutauthconfig.md)               | :heavy_minus_sign:                                                                    | N/A                                                                                   |
| `auth_type`                                                                           | [Optional[models.CHOutConfigAuthType]](../../models/choutconfigauthtype.md)           | :heavy_minus_sign:                                                                    | N/A                                                                                   |
| `column_mappings`                                                                     | List[[models.CHOutConfigColumnMappings](../../models/choutconfigcolumnmappings.md)]   | :heavy_minus_sign:                                                                    | N/A                                                                                   |
| `compress`                                                                            | *Optional[bool]*                                                                      | :heavy_minus_sign:                                                                    | N/A                                                                                   |
| `concurrency`                                                                         | *Optional[float]*                                                                     | :heavy_minus_sign:                                                                    | N/A                                                                                   |
| `dump_format_errors_to_disk`                                                          | *Optional[bool]*                                                                      | :heavy_minus_sign:                                                                    | N/A                                                                                   |
| `exclude_mapping_fields`                                                              | List[*str*]                                                                           | :heavy_minus_sign:                                                                    | N/A                                                                                   |
| `extra_http_headers`                                                                  | List[[models.NameValue](../../models/namevalue.md)]                                   | :heavy_minus_sign:                                                                    | N/A                                                                                   |
| `extra_params`                                                                        | List[[models.HTTPOutExtraParamConfig](../../models/httpoutextraparamconfig.md)]       | :heavy_minus_sign:                                                                    | N/A                                                                                   |
| `failed_request_logging_mode`                                                         | *Optional[str]*                                                                       | :heavy_minus_sign:                                                                    | N/A                                                                                   |
| `keep_alive`                                                                          | *Optional[bool]*                                                                      | :heavy_minus_sign:                                                                    | N/A                                                                                   |
| `max_connection_reuse_sec`                                                            | *Optional[float]*                                                                     | :heavy_minus_sign:                                                                    | N/A                                                                                   |
| `max_payload_events`                                                                  | *Optional[float]*                                                                     | :heavy_minus_sign:                                                                    | N/A                                                                                   |
| `max_payload_size_kb`                                                                 | *Optional[float]*                                                                     | :heavy_minus_sign:                                                                    | N/A                                                                                   |
| `max_sockets`                                                                         | *Optional[float]*                                                                     | :heavy_minus_sign:                                                                    | N/A                                                                                   |
| `method`                                                                              | *Optional[str]*                                                                       | :heavy_minus_sign:                                                                    | N/A                                                                                   |
| `password`                                                                            | *Optional[str]*                                                                       | :heavy_minus_sign:                                                                    | N/A                                                                                   |
| `reject_unauthorized`                                                                 | *Optional[bool]*                                                                      | :heavy_minus_sign:                                                                    | N/A                                                                                   |
| `response_honor_retry_after_header`                                                   | *Optional[bool]*                                                                      | :heavy_minus_sign:                                                                    | N/A                                                                                   |
| `response_retry_settings`                                                             | List[[models.HTTPOutResponseRetryConfig](../../models/httpoutresponseretryconfig.md)] | :heavy_minus_sign:                                                                    | N/A                                                                                   |
| `safe_headers`                                                                        | List[*str*]                                                                           | :heavy_minus_sign:                                                                    | N/A                                                                                   |
| `sql_username`                                                                        | *Optional[str]*                                                                       | :heavy_minus_sign:                                                                    | N/A                                                                                   |
| `table_name_expression`                                                               | *Optional[str]*                                                                       | :heavy_minus_sign:                                                                    | N/A                                                                                   |
| `timeout_retry_settings`                                                              | [Optional[models.RetryBackoffOptions]](../../models/retrybackoffoptions.md)           | :heavy_minus_sign:                                                                    | N/A                                                                                   |
| `timeout_sec`                                                                         | *Optional[float]*                                                                     | :heavy_minus_sign:                                                                    | N/A                                                                                   |
| `tls`                                                                                 | [Optional[models.TLSClientParams]](../../models/tlsclientparams.md)                   | :heavy_minus_sign:                                                                    | N/A                                                                                   |
| `token`                                                                               | *Optional[str]*                                                                       | :heavy_minus_sign:                                                                    | N/A                                                                                   |
| `total_memory_limit_kb`                                                               | *Optional[float]*                                                                     | :heavy_minus_sign:                                                                    | N/A                                                                                   |
| `urls`                                                                                | List[[models.CHOutConfigUrls](../../models/choutconfigurls.md)]                       | :heavy_minus_sign:                                                                    | N/A                                                                                   |
| `use_round_robin_dns`                                                                 | *Optional[bool]*                                                                      | :heavy_minus_sign:                                                                    | N/A                                                                                   |
| `username`                                                                            | *Optional[str]*                                                                       | :heavy_minus_sign:                                                                    | N/A                                                                                   |
| `wait_for_async_inserts`                                                              | *Optional[bool]*                                                                      | :heavy_minus_sign:                                                                    | N/A                                                                                   |
| `retries`                                                                             | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)                      | :heavy_minus_sign:                                                                    | Configuration to override the default retry behavior of the client.                   |

### Response

**[models.CreateOutputClickHouseDescribeTableResponseBody](../../models/createoutputclickhousedescribetableresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |