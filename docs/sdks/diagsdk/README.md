# DiagSDK
(*diag*)

## Overview

Actions related to diagnostics

### Available Operations

* [get_health_info](#get_health_info) - Provides health info for REST server
* [get_diag_bundle](#get_diag_bundle) - Returns a diag bundle as a tar.gz archive
* [get_system_info](#get_system_info) - Get basic system information
* [get_system_diag](#get_system_diag) - Get list of existing diag bundles
* [delete_system_diag](#delete_system_diag) - Remove diag bundle
* [create_system_diag_send](#create_system_diag_send) - Send a diag bundle (tar.gz archive) to Cribl

## get_health_info

Provides health info for REST server

### Example Usage

```python
from cribl_sdk_python_fafo import CriblSDKPythonFafo


with CriblSDKPythonFafo(
    server_url="https://api.example.com",
) as cspf_client:

    res = cspf_client.diag.get_health_info()

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.HealthStatus](../../models/healthstatus.md)**

### Errors

| Error Type               | Status Code              | Content Type             |
| ------------------------ | ------------------------ | ------------------------ |
| errors.HealthStatusError | 420                      | application/json         |
| errors.APIError          | 4XX, 5XX                 | \*/\*                    |

## get_diag_bundle

Returns a diag bundle as a tar.gz archive

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

    res = cspf_client.diag.get_diag_bundle()

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[httpx.Response](../../models/.md)**

### Errors

| Error Type      | Status Code     | Content Type    |
| --------------- | --------------- | --------------- |
| errors.APIError | 4XX, 5XX        | \*/\*           |

## get_system_info

Get basic system information

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

    res = cspf_client.diag.get_system_info()

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.GetSystemInfoResponse](../../models/getsysteminforesponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| errors.Error     | 500              | application/json |
| errors.APIError  | 4XX, 5XX         | \*/\*            |

## get_system_diag

Get list of existing diag bundles

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

    res = cspf_client.diag.get_system_diag()

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.GetSystemDiagResponse](../../models/getsystemdiagresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| errors.Error     | 500              | application/json |
| errors.APIError  | 4XX, 5XX         | \*/\*            |

## delete_system_diag

Remove diag bundle

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

    res = cspf_client.diag.delete_system_diag(path="/opt/lib")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `path`                                                              | *str*                                                               | :heavy_check_mark:                                                  | Diag bundle path                                                    |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.DeleteSystemDiagResponse](../../models/deletesystemdiagresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| errors.Error     | 500              | application/json |
| errors.APIError  | 4XX, 5XX         | \*/\*            |

## create_system_diag_send

Send a diag bundle (tar.gz archive) to Cribl

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

    res = cspf_client.diag.create_system_diag_send(send_to_cribl=False, rename_js=True, include_metrics=True, include_git=True, include_top_talkers=False, include_install_logs=False)

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                                                                              | Type                                                                                                                   | Required                                                                                                               | Description                                                                                                            |
| ---------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------- |
| `send_to_cribl`                                                                                                        | *Optional[bool]*                                                                                                       | :heavy_minus_sign:                                                                                                     | Send diagnostic bundle to Cribl Support                                                                                |
| `path`                                                                                                                 | *Optional[str]*                                                                                                        | :heavy_minus_sign:                                                                                                     | Existing bundle that will be sent to Cribl Support. Max 100MB.                                                         |
| `rename_js`                                                                                                            | *Optional[bool]*                                                                                                       | :heavy_minus_sign:                                                                                                     | Append .txt to JavaScript files                                                                                        |
| `include_metrics`                                                                                                      | *Optional[bool]*                                                                                                       | :heavy_minus_sign:                                                                                                     | Disable to exclude metrics from the bundle                                                                             |
| `include_git`                                                                                                          | *Optional[bool]*                                                                                                       | :heavy_minus_sign:                                                                                                     | Disable to exclude the git audit from the bundle                                                                       |
| `include_top_talkers`                                                                                                  | *Optional[bool]*                                                                                                       | :heavy_minus_sign:                                                                                                     | Include data about your 10 highest-volume Sources, Destinations, Pipelines, Routes, and Packs in the diagnostic bundle |
| `max_include_jobs`                                                                                                     | *Optional[float]*                                                                                                      | :heavy_minus_sign:                                                                                                     | Number of jobs, including all tasks that will be included in the bundle                                                |
| `include_install_logs`                                                                                                 | *Optional[bool]*                                                                                                       | :heavy_minus_sign:                                                                                                     | Enable to include installation logs in the bundle (Windows only)                                                       |
| `retries`                                                                                                              | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)                                                       | :heavy_minus_sign:                                                                                                     | Configuration to override the default retry behavior of the client.                                                    |

### Response

**[models.CreateSystemDiagSendResponse](../../models/createsystemdiagsendresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| errors.Error     | 500              | application/json |
| errors.APIError  | 4XX, 5XX         | \*/\*            |