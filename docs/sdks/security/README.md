# Security
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
import cribl
from cribl import Cribl
import os


with Cribl(
    security=cribl.SecurityModel(
        bearer_auth=os.getenv("CRIBL_BEARER_AUTH", ""),
    ),
) as c_client:

    res = c_client.security.get_security_kms_config()

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.GetSecurityKmsConfigResponseBody](../../models/getsecuritykmsconfigresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |

## update_security_kms_config

Update Cribl KMS config

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

    res = c_client.security.update_security_kms_config(enable_health_check=True, provider=cribl.SecretProvider.VAULT)

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                                           | Type                                                                                | Required                                                                            | Description                                                                         |
| ----------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------- |
| `enable_health_check`                                                               | *bool*                                                                              | :heavy_check_mark:                                                                  | N/A                                                                                 |
| `provider`                                                                          | [models.SecretProvider](../../models/secretprovider.md)                             | :heavy_check_mark:                                                                  | N/A                                                                                 |
| `auth`                                                                              | [Optional[models.KMSProviderConfigAuth]](../../models/kmsproviderconfigauth.md)     | :heavy_minus_sign:                                                                  | N/A                                                                                 |
| `health_check_endpoint`                                                             | *Optional[str]*                                                                     | :heavy_minus_sign:                                                                  | N/A                                                                                 |
| `namespace`                                                                         | *Optional[str]*                                                                     | :heavy_minus_sign:                                                                  | N/A                                                                                 |
| `secret_dir`                                                                        | *Optional[str]*                                                                     | :heavy_minus_sign:                                                                  | N/A                                                                                 |
| `service`                                                                           | [Optional[models.AWSKMSServiceConfig]](../../models/awskmsserviceconfig.md)         | :heavy_minus_sign:                                                                  | N/A                                                                                 |
| `tls`                                                                               | [Optional[models.VaultKMSTLSClientConfig]](../../models/vaultkmstlsclientconfig.md) | :heavy_minus_sign:                                                                  | N/A                                                                                 |
| `url`                                                                               | *Optional[str]*                                                                     | :heavy_minus_sign:                                                                  | N/A                                                                                 |
| `retries`                                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)                    | :heavy_minus_sign:                                                                  | Configuration to override the default retry behavior of the client.                 |

### Response

**[models.UpdateSecurityKmsConfigResponseBody](../../models/updatesecuritykmsconfigresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |

## get_security_kms_health

Get Cribl KMS health

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

    res = c_client.security.get_security_kms_health()

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.GetSecurityKmsHealthResponseBody](../../models/getsecuritykmshealthresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |