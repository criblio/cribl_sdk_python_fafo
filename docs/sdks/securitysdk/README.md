# SecuritySDK
(*security*)

## Overview

Actions related to Security

### Available Operations

* [get_security_kms_config](#get_security_kms_config) - Get Cribl KMS config
* [update_security_kms_config](#update_security_kms_config) - Update Cribl KMS config
* [get_security_kms_health](#get_security_kms_health) - Get Cribl KMS health

## get_security_kms_config

Get Cribl KMS config

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

    res = cspf_client.security.get_security_kms_config()

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.GetSecurityKmsConfigResponse](../../models/getsecuritykmsconfigresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| errors.Error     | 500              | application/json |
| errors.APIError  | 4XX, 5XX         | \*/\*            |

## update_security_kms_config

Update Cribl KMS config

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

    res = cspf_client.security.update_security_kms_config(enable_health_check=True, provider=models.SecretProvider.LOCAL)

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                                           | Type                                                                                | Required                                                                            | Description                                                                         |
| ----------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------- |
| `enable_health_check`                                                               | *bool*                                                                              | :heavy_check_mark:                                                                  | N/A                                                                                 |
| `provider`                                                                          | [models.SecretProvider](../../models/secretprovider.md)                             | :heavy_check_mark:                                                                  | N/A                                                                                 |
| `auth`                                                                              | [Optional[models.Auth]](../../models/auth.md)                                       | :heavy_minus_sign:                                                                  | N/A                                                                                 |
| `health_check_endpoint`                                                             | *Optional[str]*                                                                     | :heavy_minus_sign:                                                                  | N/A                                                                                 |
| `namespace`                                                                         | *Optional[str]*                                                                     | :heavy_minus_sign:                                                                  | N/A                                                                                 |
| `secret_dir`                                                                        | *Optional[str]*                                                                     | :heavy_minus_sign:                                                                  | N/A                                                                                 |
| `service`                                                                           | [Optional[models.AWSKMSServiceConfig]](../../models/awskmsserviceconfig.md)         | :heavy_minus_sign:                                                                  | N/A                                                                                 |
| `tls`                                                                               | [Optional[models.VaultKMSTLSClientConfig]](../../models/vaultkmstlsclientconfig.md) | :heavy_minus_sign:                                                                  | N/A                                                                                 |
| `url`                                                                               | *Optional[str]*                                                                     | :heavy_minus_sign:                                                                  | N/A                                                                                 |
| `retries`                                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)                    | :heavy_minus_sign:                                                                  | Configuration to override the default retry behavior of the client.                 |

### Response

**[models.UpdateSecurityKmsConfigResponse](../../models/updatesecuritykmsconfigresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| errors.Error     | 500              | application/json |
| errors.APIError  | 4XX, 5XX         | \*/\*            |

## get_security_kms_health

Get Cribl KMS health

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

    res = cspf_client.security.get_security_kms_health()

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.GetSecurityKmsHealthResponse](../../models/getsecuritykmshealthresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| errors.Error     | 500              | application/json |
| errors.APIError  | 4XX, 5XX         | \*/\*            |