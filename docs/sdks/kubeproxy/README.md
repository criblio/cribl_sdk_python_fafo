# KubeProxy
(*kube_proxy*)

## Overview

Actions related to Kube Proxy

### Available Operations

* [get_edge_kube_proxy](#get_edge_kube_proxy) - Make a GET request to the K8s API

## get_edge_kube_proxy

Make a GET request to the K8s API

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

    res = c_client.kube_proxy.get_edge_kube_proxy()

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `path`                                                              | *Optional[str]*                                                     | :heavy_minus_sign:                                                  | string optional                                                     |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.GetEdgeKubeProxyResponseBody](../../models/getedgekubeproxyresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |