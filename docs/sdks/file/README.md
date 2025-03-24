# File
(*file*)

## Overview

Actions related to File

### Available Operations

* [create_edge_file_ingest](#create_edge_file_ingest) - Ingest a specified file through a specified pipeline to a specified destination or send to routes.

## create_edge_file_ingest

Ingest a specified file through a specified pipeline to a specified destination or send to routes.

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

    res = c_client.file.create_edge_file_ingest()

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `file_path`                                                         | *Optional[str]*                                                     | :heavy_minus_sign:                                                  | Absolute path to file to ingest.                                    |
| `pipeline_id`                                                       | *Optional[str]*                                                     | :heavy_minus_sign:                                                  | Id of the pipeline to use.                                          |
| `output_id`                                                         | *Optional[str]*                                                     | :heavy_minus_sign:                                                  | Destination to send events to.                                      |
| `pre_processing_pipeline_id`                                        | *Optional[str]*                                                     | :heavy_minus_sign:                                                  | Id to the pre-processing pipeline to use for routes.                |
| `send_to_routes`                                                    | *Optional[str]*                                                     | :heavy_minus_sign:                                                  | boolean condition required on whether to send events to routes.     |
| `breaker_rule_set`                                                  | *Optional[str]*                                                     | :heavy_minus_sign:                                                  | Breaker rules to use on the file.                                   |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.CreateEdgeFileIngestResponseBody](../../models/createedgefileingestresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |