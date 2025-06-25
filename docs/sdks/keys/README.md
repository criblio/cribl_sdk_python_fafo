# Keys
(*keys*)

## Overview

Actions related to encryption keys

### Available Operations

* [list_key_metadata_entity](#list_key_metadata_entity) - Get a list of KeyMetadataEntity objects
* [create_key_metadata_entity](#create_key_metadata_entity) - Create KeyMetadataEntity
* [get_key_metadata_entity_by_id](#get_key_metadata_entity_by_id) - Get KeyMetadataEntity by ID
* [update_key_metadata_entity_by_id](#update_key_metadata_entity_by_id) - Update KeyMetadataEntity
* [delete_key_metadata_entity_by_id](#delete_key_metadata_entity_by_id) - Delete KeyMetadataEntity

## list_key_metadata_entity

Get a list of KeyMetadataEntity objects

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

    res = cspf_client.keys.list_key_metadata_entity()

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.ListKeyMetadataEntityResponse](../../models/listkeymetadataentityresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| errors.Error     | 500              | application/json |
| errors.APIError  | 4XX, 5XX         | \*/\*            |

## create_key_metadata_entity

Create KeyMetadataEntity

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

    res = cspf_client.keys.create_key_metadata_entity(key_id="<id>", algorithm=models.EncryptionAlgorithm.AES_256_CBC, kms=models.KMSForThisKey.LOCAL, keyclass=0, use_iv=False, iv_size=models.InitializationVectorSize.TWELVE)

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                                                                                                                                 | Type                                                                                                                                                                      | Required                                                                                                                                                                  | Description                                                                                                                                                               |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `key_id`                                                                                                                                                                  | *str*                                                                                                                                                                     | :heavy_check_mark:                                                                                                                                                        | N/A                                                                                                                                                                       |
| `description`                                                                                                                                                             | *Optional[str]*                                                                                                                                                           | :heavy_minus_sign:                                                                                                                                                        | N/A                                                                                                                                                                       |
| `algorithm`                                                                                                                                                               | [Optional[models.EncryptionAlgorithm]](../../models/encryptionalgorithm.md)                                                                                               | :heavy_minus_sign:                                                                                                                                                        | N/A                                                                                                                                                                       |
| `kms`                                                                                                                                                                     | [Optional[models.KMSForThisKey]](../../models/kmsforthiskey.md)                                                                                                           | :heavy_minus_sign:                                                                                                                                                        | N/A                                                                                                                                                                       |
| `keyclass`                                                                                                                                                                | *Optional[float]*                                                                                                                                                         | :heavy_minus_sign:                                                                                                                                                        | N/A                                                                                                                                                                       |
| `created`                                                                                                                                                                 | *Optional[float]*                                                                                                                                                         | :heavy_minus_sign:                                                                                                                                                        | N/A                                                                                                                                                                       |
| `expires`                                                                                                                                                                 | *Optional[float]*                                                                                                                                                         | :heavy_minus_sign:                                                                                                                                                        | N/A                                                                                                                                                                       |
| `plain_key`                                                                                                                                                               | *Optional[str]*                                                                                                                                                           | :heavy_minus_sign:                                                                                                                                                        | N/A                                                                                                                                                                       |
| `cipher_key`                                                                                                                                                              | *Optional[str]*                                                                                                                                                           | :heavy_minus_sign:                                                                                                                                                        | N/A                                                                                                                                                                       |
| `use_iv`                                                                                                                                                                  | *Optional[bool]*                                                                                                                                                          | :heavy_minus_sign:                                                                                                                                                        | Seed encryption with a [nonce](https://en.wikipedia.org/wiki/Cryptographic_nonce) to make the key more random and unique. Must be enabled with the aes-256-gcm algorithm. |
| `iv_size`                                                                                                                                                                 | [Optional[models.InitializationVectorSize]](../../models/initializationvectorsize.md)                                                                                     | :heavy_minus_sign:                                                                                                                                                        | Length of the initialization vector, in bytes                                                                                                                             |
| `group`                                                                                                                                                                   | *Optional[str]*                                                                                                                                                           | :heavy_minus_sign:                                                                                                                                                        | Name of the Worker Group/Fleet that created this key                                                                                                                      |
| `retries`                                                                                                                                                                 | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)                                                                                                          | :heavy_minus_sign:                                                                                                                                                        | Configuration to override the default retry behavior of the client.                                                                                                       |

### Response

**[models.CreateKeyMetadataEntityResponse](../../models/createkeymetadataentityresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| errors.Error     | 500              | application/json |
| errors.APIError  | 4XX, 5XX         | \*/\*            |

## get_key_metadata_entity_by_id

Get KeyMetadataEntity by ID

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

    res = cspf_client.keys.get_key_metadata_entity_by_id(id="<id>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `id`                                                                | *str*                                                               | :heavy_check_mark:                                                  | Unique ID to GET                                                    |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.GetKeyMetadataEntityByIDResponse](../../models/getkeymetadataentitybyidresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| errors.Error     | 500              | application/json |
| errors.APIError  | 4XX, 5XX         | \*/\*            |

## update_key_metadata_entity_by_id

Update KeyMetadataEntity

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

    res = cspf_client.keys.update_key_metadata_entity_by_id(id="<id>", key_id="<id>", algorithm=models.EncryptionAlgorithm.AES_256_CBC, kms=models.KMSForThisKey.LOCAL, keyclass=0, use_iv=False, iv_size=models.InitializationVectorSize.TWELVE)

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                                                                                                                                 | Type                                                                                                                                                                      | Required                                                                                                                                                                  | Description                                                                                                                                                               |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `id`                                                                                                                                                                      | *str*                                                                                                                                                                     | :heavy_check_mark:                                                                                                                                                        | Unique ID to PATCH                                                                                                                                                        |
| `key_id`                                                                                                                                                                  | *str*                                                                                                                                                                     | :heavy_check_mark:                                                                                                                                                        | N/A                                                                                                                                                                       |
| `description`                                                                                                                                                             | *Optional[str]*                                                                                                                                                           | :heavy_minus_sign:                                                                                                                                                        | N/A                                                                                                                                                                       |
| `algorithm`                                                                                                                                                               | [Optional[models.EncryptionAlgorithm]](../../models/encryptionalgorithm.md)                                                                                               | :heavy_minus_sign:                                                                                                                                                        | N/A                                                                                                                                                                       |
| `kms`                                                                                                                                                                     | [Optional[models.KMSForThisKey]](../../models/kmsforthiskey.md)                                                                                                           | :heavy_minus_sign:                                                                                                                                                        | N/A                                                                                                                                                                       |
| `keyclass`                                                                                                                                                                | *Optional[float]*                                                                                                                                                         | :heavy_minus_sign:                                                                                                                                                        | N/A                                                                                                                                                                       |
| `created`                                                                                                                                                                 | *Optional[float]*                                                                                                                                                         | :heavy_minus_sign:                                                                                                                                                        | N/A                                                                                                                                                                       |
| `expires`                                                                                                                                                                 | *Optional[float]*                                                                                                                                                         | :heavy_minus_sign:                                                                                                                                                        | N/A                                                                                                                                                                       |
| `plain_key`                                                                                                                                                               | *Optional[str]*                                                                                                                                                           | :heavy_minus_sign:                                                                                                                                                        | N/A                                                                                                                                                                       |
| `cipher_key`                                                                                                                                                              | *Optional[str]*                                                                                                                                                           | :heavy_minus_sign:                                                                                                                                                        | N/A                                                                                                                                                                       |
| `use_iv`                                                                                                                                                                  | *Optional[bool]*                                                                                                                                                          | :heavy_minus_sign:                                                                                                                                                        | Seed encryption with a [nonce](https://en.wikipedia.org/wiki/Cryptographic_nonce) to make the key more random and unique. Must be enabled with the aes-256-gcm algorithm. |
| `iv_size`                                                                                                                                                                 | [Optional[models.InitializationVectorSize]](../../models/initializationvectorsize.md)                                                                                     | :heavy_minus_sign:                                                                                                                                                        | Length of the initialization vector, in bytes                                                                                                                             |
| `group`                                                                                                                                                                   | *Optional[str]*                                                                                                                                                           | :heavy_minus_sign:                                                                                                                                                        | Name of the Worker Group/Fleet that created this key                                                                                                                      |
| `retries`                                                                                                                                                                 | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)                                                                                                          | :heavy_minus_sign:                                                                                                                                                        | Configuration to override the default retry behavior of the client.                                                                                                       |

### Response

**[models.UpdateKeyMetadataEntityByIDResponse](../../models/updatekeymetadataentitybyidresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| errors.Error     | 500              | application/json |
| errors.APIError  | 4XX, 5XX         | \*/\*            |

## delete_key_metadata_entity_by_id

Delete KeyMetadataEntity

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

    res = cspf_client.keys.delete_key_metadata_entity_by_id(id="<id>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `id`                                                                | *str*                                                               | :heavy_check_mark:                                                  | Unique ID to DELETE                                                 |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.DeleteKeyMetadataEntityByIDResponse](../../models/deletekeymetadataentitybyidresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| errors.Error     | 500              | application/json |
| errors.APIError  | 4XX, 5XX         | \*/\*            |