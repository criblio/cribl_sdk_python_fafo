# FileSampler
(*file_sampler*)

## Overview

Actions related to FileSampler

### Available Operations

* [get_edge_file_sample](#get_edge_file_sample) - Get some number of bytes from the file at the given path

## get_edge_file_sample

Get some number of bytes from the file at the given path

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

    res = cspf_client.file_sampler.get_edge_file_sample(path="/usr/ports")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                                          | Type                                                                               | Required                                                                           | Description                                                                        |
| ---------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------- |
| `path`                                                                             | *str*                                                                              | :heavy_check_mark:                                                                 | The path to the file to sample                                                     |
| `bytes_requested`                                                                  | *Optional[float]*                                                                  | :heavy_minus_sign:                                                                 | The number of bytes to return;   this value could be constrained by system limits. |
| `retries`                                                                          | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)                   | :heavy_minus_sign:                                                                 | Configuration to override the default retry behavior of the client.                |

### Response

**[models.GetEdgeFileSampleResponse](../../models/getedgefilesampleresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| errors.Error     | 500              | application/json |
| errors.APIError  | 4XX, 5XX         | \*/\*            |