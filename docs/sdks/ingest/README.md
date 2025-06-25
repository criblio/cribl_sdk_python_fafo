# Ingest
(*ingest*)

## Overview

Actions related to Ingest

### Available Operations

* [create_edge_file_ingest](#create_edge_file_ingest) - Ingest a specified file through a specified pipeline to a specified destination or send to routes.

## create_edge_file_ingest

Ingest a specified file through a specified pipeline to a specified destination or send to routes.

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

    res = cspf_client.ingest.create_edge_file_ingest()

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

**[models.CreateEdgeFileIngestResponse](../../models/createedgefileingestresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| errors.Error     | 500              | application/json |
| errors.APIError  | 4XX, 5XX         | \*/\*            |