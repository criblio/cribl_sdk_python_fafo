# Certificates
(*certificates*)

## Overview

Actions related to Certificates

### Available Operations

* [list_certificate](#list_certificate) - Get a list of Certificate objects
* [create_certificate](#create_certificate) - Create Certificate
* [get_certificate_by_id](#get_certificate_by_id) - Get Certificate by ID
* [update_certificate_by_id](#update_certificate_by_id) - Update Certificate
* [delete_certificate_by_id](#delete_certificate_by_id) - Delete Certificate

## list_certificate

Get a list of Certificate objects

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

    res = cspf_client.certificates.list_certificate()

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.ListCertificateResponse](../../models/listcertificateresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| errors.Error     | 500              | application/json |
| errors.APIError  | 4XX, 5XX         | \*/\*            |

## create_certificate

Create Certificate

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

    res = cspf_client.certificates.create_certificate(id="<id>", cert="<value>", priv_key="<value>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                                                                                                                                        | Type                                                                                                                                                                             | Required                                                                                                                                                                         | Description                                                                                                                                                                      |
| -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `id`                                                                                                                                                                             | *str*                                                                                                                                                                            | :heavy_check_mark:                                                                                                                                                               | N/A                                                                                                                                                                              |
| `cert`                                                                                                                                                                           | *str*                                                                                                                                                                            | :heavy_check_mark:                                                                                                                                                               | Drag/drop or upload host certificate in PEM/Base64 format, or paste its contents here                                                                                            |
| `priv_key`                                                                                                                                                                       | *str*                                                                                                                                                                            | :heavy_check_mark:                                                                                                                                                               | N/A                                                                                                                                                                              |
| `description`                                                                                                                                                                    | *Optional[str]*                                                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                               | N/A                                                                                                                                                                              |
| `passphrase`                                                                                                                                                                     | *Optional[str]*                                                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                               | N/A                                                                                                                                                                              |
| `ca`                                                                                                                                                                             | *Optional[str]*                                                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                               | Optionally, drag/drop or upload all CA certificates in PEM/Base64 format. Or, paste certificate contents here. Certificates can be used for client and/or server authentication. |
| `in_use`                                                                                                                                                                         | List[*str*]                                                                                                                                                                      | :heavy_minus_sign:                                                                                                                                                               | List of configurations that reference this certificate                                                                                                                           |
| `retries`                                                                                                                                                                        | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)                                                                                                                 | :heavy_minus_sign:                                                                                                                                                               | Configuration to override the default retry behavior of the client.                                                                                                              |

### Response

**[models.CreateCertificateResponse](../../models/createcertificateresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| errors.Error     | 500              | application/json |
| errors.APIError  | 4XX, 5XX         | \*/\*            |

## get_certificate_by_id

Get Certificate by ID

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

    res = cspf_client.certificates.get_certificate_by_id(id="<id>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `id`                                                                | *str*                                                               | :heavy_check_mark:                                                  | Unique ID to GET                                                    |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.GetCertificateByIDResponse](../../models/getcertificatebyidresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| errors.Error     | 500              | application/json |
| errors.APIError  | 4XX, 5XX         | \*/\*            |

## update_certificate_by_id

Update Certificate

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

    res = cspf_client.certificates.update_certificate_by_id(id_param="<value>", id="<id>", cert="<value>", priv_key="<value>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                                                                                                                                        | Type                                                                                                                                                                             | Required                                                                                                                                                                         | Description                                                                                                                                                                      |
| -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `id_param`                                                                                                                                                                       | *str*                                                                                                                                                                            | :heavy_check_mark:                                                                                                                                                               | Unique ID to PATCH                                                                                                                                                               |
| `id`                                                                                                                                                                             | *str*                                                                                                                                                                            | :heavy_check_mark:                                                                                                                                                               | N/A                                                                                                                                                                              |
| `cert`                                                                                                                                                                           | *str*                                                                                                                                                                            | :heavy_check_mark:                                                                                                                                                               | Drag/drop or upload host certificate in PEM/Base64 format, or paste its contents here                                                                                            |
| `priv_key`                                                                                                                                                                       | *str*                                                                                                                                                                            | :heavy_check_mark:                                                                                                                                                               | N/A                                                                                                                                                                              |
| `description`                                                                                                                                                                    | *Optional[str]*                                                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                               | N/A                                                                                                                                                                              |
| `passphrase`                                                                                                                                                                     | *Optional[str]*                                                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                               | N/A                                                                                                                                                                              |
| `ca`                                                                                                                                                                             | *Optional[str]*                                                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                               | Optionally, drag/drop or upload all CA certificates in PEM/Base64 format. Or, paste certificate contents here. Certificates can be used for client and/or server authentication. |
| `in_use`                                                                                                                                                                         | List[*str*]                                                                                                                                                                      | :heavy_minus_sign:                                                                                                                                                               | List of configurations that reference this certificate                                                                                                                           |
| `retries`                                                                                                                                                                        | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)                                                                                                                 | :heavy_minus_sign:                                                                                                                                                               | Configuration to override the default retry behavior of the client.                                                                                                              |

### Response

**[models.UpdateCertificateByIDResponse](../../models/updatecertificatebyidresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| errors.Error     | 500              | application/json |
| errors.APIError  | 4XX, 5XX         | \*/\*            |

## delete_certificate_by_id

Delete Certificate

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

    res = cspf_client.certificates.delete_certificate_by_id(id="<id>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `id`                                                                | *str*                                                               | :heavy_check_mark:                                                  | Unique ID to DELETE                                                 |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.DeleteCertificateByIDResponse](../../models/deletecertificatebyidresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| errors.Error     | 500              | application/json |
| errors.APIError  | 4XX, 5XX         | \*/\*            |