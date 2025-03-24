# Outputs
(*outputs*)

## Overview

Actions related to outputs

### Available Operations

* [list_output](#list_output) - Get a list of Output objects
* [create_output](#create_output) - Create Output
* [get_output_by_id](#get_output_by_id) - Get Output by ID
* [update_output_by_id](#update_output_by_id) - Update Output
* [delete_output_by_id](#delete_output_by_id) - Delete Output
* [delete_output_pq_by_id](#delete_output_pq_by_id) - Clears destination persistent queue
* [get_output_pq_by_id](#get_output_pq_by_id) - Retrieves status of latest clear PQ job for an output
* [get_output_samples_by_id](#get_output_samples_by_id) - Retrieve samples data for the specified output. Used to get sample data for the test action.
* [create_output_test_by_id](#create_output_test_by_id) - Send sample data to an output to validate configuration or test connectivity
* [list_output_status](#list_output_status) - Get a list of OutputStatus objects
* [get_output_status_by_id](#get_output_status_by_id) - Get OutputStatus by ID

## list_output

Get a list of Output objects

### Example Usage

```python
from cribl import Cribl
import os


with Cribl(
    bearer_auth=os.getenv("CRIBL_BEARER_AUTH", ""),
) as c_client:

    res = c_client.outputs.list_output()

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.ListOutputResponseBody](../../models/listoutputresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |

## create_output

Create Output

### Example Usage

```python
import cribl
from cribl import Cribl
import os


with Cribl(
    bearer_auth=os.getenv("CRIBL_BEARER_AUTH", ""),
) as c_client:

    res = c_client.outputs.create_output(request={
        "id": "<id>",
        "type": cribl.OutputSyslogType.SYSLOG,
        "protocol": cribl.OutputSyslogProtocol.TCP,
        "facility": cribl.Facility.ONE,
        "severity": cribl.OutputSyslogSeverity.FIVE,
        "app_name": "Cribl",
        "message_format": cribl.MessageFormat.RFC3164,
        "timestamp_format": cribl.TimestampFormat.SYSLOG,
        "throttle_rate_per_sec": "0",
        "log_failed_requests": False,
        "load_balanced": True,
        "connection_timeout": 10000,
        "write_timeout": 60000,
        "on_backpressure": cribl.OutputSyslogBackpressureBehavior.BLOCK,
        "max_record_size": 1500,
        "udp_dns_resolve_period_sec": 0,
        "pq_max_file_size": "1 MB",
        "pq_max_size": "5GB",
        "pq_path": "$CRIBL_HOME/state/queues",
        "pq_compress": cribl.OutputSyslogCompression.NONE,
        "pq_on_backpressure": cribl.OutputSyslogQueueFullBehavior.BLOCK,
        "pq_mode": cribl.OutputSyslogMode.ERROR,
    })

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `request`                                                           | [models.Output](../../models/output.md)                             | :heavy_check_mark:                                                  | The request object to use for the request.                          |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.CreateOutputResponseBody](../../models/createoutputresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |

## get_output_by_id

Get Output by ID

### Example Usage

```python
from cribl import Cribl
import os


with Cribl(
    bearer_auth=os.getenv("CRIBL_BEARER_AUTH", ""),
) as c_client:

    res = c_client.outputs.get_output_by_id(id="<id>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `id`                                                                | *str*                                                               | :heavy_check_mark:                                                  | Unique ID to GET                                                    |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.GetOutputByIDResponseBody](../../models/getoutputbyidresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |

## update_output_by_id

Update Output

### Example Usage

```python
import cribl
from cribl import Cribl
import os


with Cribl(
    bearer_auth=os.getenv("CRIBL_BEARER_AUTH", ""),
) as c_client:

    res = c_client.outputs.update_output_by_id(id="<id>", output={
        "bucket": "<value>",
        "aws_authentication_method": cribl.OutputS3AuthenticationMethod.AUTO,
        "signature_version": cribl.OutputS3SignatureVersion.V4,
        "reuse_connections": True,
        "reject_unauthorized": True,
        "enable_assume_role": False,
        "duration_seconds": 3600,
        "stage_path": "$CRIBL_HOME/state/outputs/staging",
        "add_id_to_stage_path": True,
        "dest_path": "",
        "object_acl": cribl.ObjectACL.PRIVATE,
        "remove_empty_dirs": True,
        "partition_expr": "C.Time.strftime(_time ? _time : Date.now()/1000, '%Y/%m/%d')",
        "format_": cribl.OutputS3DataFormat.JSON,
        "base_file_name": "`CriblOut`",
        "file_name_suffix": "`.${C.env[\"CRIBL_WORKER_ID\"]}.${__format}${__compression === \"gzip\" ? \".gz\" : \"\"}`",
        "max_file_size_mb": 32,
        "max_open_files": 100,
        "header_line": "",
        "write_high_water_mark": 64,
        "on_backpressure": cribl.OutputS3BackpressureBehavior.BLOCK,
        "deadletter_enabled": False,
        "on_disk_full_backpressure": cribl.OutputS3DiskSpaceProtection.BLOCK,
        "max_file_open_time_sec": 300,
        "max_file_idle_time_sec": 30,
        "max_concurrent_file_parts": 4,
        "verify_permissions": True,
        "max_closing_files_to_backpressure": 100,
        "compress": cribl.OutputS3Compress.GZIP,
        "compression_level": cribl.OutputS3CompressionLevel.BEST_SPEED,
        "automatic_schema": False,
        "parquet_version": cribl.OutputS3ParquetVersion.PARQUET_2_6,
        "parquet_data_page_version": cribl.OutputS3DataPageVersion.DATA_PAGE_V2,
        "parquet_row_group_length": 10000,
        "parquet_page_size": "1MB",
        "enable_statistics": True,
        "enable_write_page_index": True,
        "enable_page_checksum": False,
        "empty_dir_cleanup_sec": 300,
        "deadletter_path": "$CRIBL_HOME/state/outputs/dead-letter",
        "max_retry_num": 20,
    })

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `id`                                                                | *str*                                                               | :heavy_check_mark:                                                  | Unique ID to PATCH                                                  |
| `output`                                                            | [models.Output](../../models/output.md)                             | :heavy_check_mark:                                                  | Output object to be updated                                         |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.UpdateOutputByIDResponseBody](../../models/updateoutputbyidresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |

## delete_output_by_id

Delete Output

### Example Usage

```python
from cribl import Cribl
import os


with Cribl(
    bearer_auth=os.getenv("CRIBL_BEARER_AUTH", ""),
) as c_client:

    res = c_client.outputs.delete_output_by_id(id="<id>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `id`                                                                | *str*                                                               | :heavy_check_mark:                                                  | Unique ID to DELETE                                                 |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.DeleteOutputByIDResponseBody](../../models/deleteoutputbyidresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |

## delete_output_pq_by_id

Clears destination persistent queue

### Example Usage

```python
from cribl import Cribl
import os


with Cribl(
    bearer_auth=os.getenv("CRIBL_BEARER_AUTH", ""),
) as c_client:

    res = c_client.outputs.delete_output_pq_by_id(id="<id>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `id`                                                                | *str*                                                               | :heavy_check_mark:                                                  | Output Id                                                           |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.DeleteOutputPqByIDResponseBody](../../models/deleteoutputpqbyidresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |

## get_output_pq_by_id

Retrieves status of latest clear PQ job for an output

### Example Usage

```python
from cribl import Cribl
import os


with Cribl(
    bearer_auth=os.getenv("CRIBL_BEARER_AUTH", ""),
) as c_client:

    res = c_client.outputs.get_output_pq_by_id(id="<id>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `id`                                                                | *str*                                                               | :heavy_check_mark:                                                  | Output Id                                                           |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.GetOutputPqByIDResponseBody](../../models/getoutputpqbyidresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |

## get_output_samples_by_id

Retrieve samples data for the specified output. Used to get sample data for the test action.

### Example Usage

```python
from cribl import Cribl
import os


with Cribl(
    bearer_auth=os.getenv("CRIBL_BEARER_AUTH", ""),
) as c_client:

    res = c_client.outputs.get_output_samples_by_id(id="<id>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `id`                                                                | *str*                                                               | :heavy_check_mark:                                                  | Output Id                                                           |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.GetOutputSamplesByIDResponseBody](../../models/getoutputsamplesbyidresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |

## create_output_test_by_id

Send sample data to an output to validate configuration or test connectivity

### Example Usage

```python
from cribl import Cribl
import os


with Cribl(
    bearer_auth=os.getenv("CRIBL_BEARER_AUTH", ""),
) as c_client:

    res = c_client.outputs.create_output_test_by_id(id="<id>", events=[
        {
            "raw": "<value>",
        },
    ])

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `id`                                                                | *str*                                                               | :heavy_check_mark:                                                  | Output Id                                                           |
| `events`                                                            | List[[models.CriblEvent](../../models/criblevent.md)]               | :heavy_check_mark:                                                  | N/A                                                                 |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.CreateOutputTestByIDResponseBody](../../models/createoutputtestbyidresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |

## list_output_status

Get a list of OutputStatus objects

### Example Usage

```python
from cribl import Cribl
import os


with Cribl(
    bearer_auth=os.getenv("CRIBL_BEARER_AUTH", ""),
) as c_client:

    res = c_client.outputs.list_output_status()

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.ListOutputStatusResponseBody](../../models/listoutputstatusresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |

## get_output_status_by_id

Get OutputStatus by ID

### Example Usage

```python
from cribl import Cribl
import os


with Cribl(
    bearer_auth=os.getenv("CRIBL_BEARER_AUTH", ""),
) as c_client:

    res = c_client.outputs.get_output_status_by_id(id="<id>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `id`                                                                | *str*                                                               | :heavy_check_mark:                                                  | Unique ID to GET                                                    |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.GetOutputStatusByIDResponseBody](../../models/getoutputstatusbyidresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |