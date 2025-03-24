# Consumption
(*v5.billing.consumption*)

## Overview

### Available Operations

* [v5_billing_consumption_get_single_product_usage_breakdown](#v5_billing_consumption_get_single_product_usage_breakdown)
* [v5_billing_consumption_get_products_consumption_stats](#v5_billing_consumption_get_products_consumption_stats)
* [v5_billing_consumption_get_credits_summary](#v5_billing_consumption_get_credits_summary)
* [v5_billing_consumption_get_cumulative_consumption](#v5_billing_consumption_get_cumulative_consumption)
* [v5_billing_consumption_get_products_breakdown](#v5_billing_consumption_get_products_breakdown)

## v5_billing_consumption_get_single_product_usage_breakdown

### Example Usage

```python
import cribl
from cribl import Cribl
import dateutil.parser
import os


with Cribl(
    bearer_auth=os.getenv("CRIBL_BEARER_AUTH", ""),
) as c_client:

    res = c_client.v5.billing.consumption.v5_billing_consumption_get_single_product_usage_breakdown(organization_id="<id>", product_slug=cribl.ProductSlug.SEARCH, starting_on=dateutil.parser.isoparse("2023-11-28T21:49:04.925Z"), ending_before=dateutil.parser.isoparse("2025-09-09T13:52:53.788Z"), window=cribl.ConsumptionWindowV5.MONTHLY)

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                            | Type                                                                 | Required                                                             | Description                                                          |
| -------------------------------------------------------------------- | -------------------------------------------------------------------- | -------------------------------------------------------------------- | -------------------------------------------------------------------- |
| `organization_id`                                                    | *str*                                                                | :heavy_check_mark:                                                   | N/A                                                                  |
| `product_slug`                                                       | [models.ProductSlug](../../models/productslug.md)                    | :heavy_check_mark:                                                   | N/A                                                                  |
| `starting_on`                                                        | [date](https://docs.python.org/3/library/datetime.html#date-objects) | :heavy_check_mark:                                                   | N/A                                                                  |
| `ending_before`                                                      | [date](https://docs.python.org/3/library/datetime.html#date-objects) | :heavy_check_mark:                                                   | N/A                                                                  |
| `window`                                                             | [models.ConsumptionWindowV5](../../models/consumptionwindowv5.md)    | :heavy_check_mark:                                                   | N/A                                                                  |
| `retries`                                                            | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)     | :heavy_minus_sign:                                                   | Configuration to override the default retry behavior of the client.  |
| `server_url`                                                         | *Optional[str]*                                                      | :heavy_minus_sign:                                                   | An optional server URL to use.                                       |

### Response

**[models.GetSingleProductUsageBreakdownResponseV5](../../models/getsingleproductusagebreakdownresponsev5.md)**

### Errors

| Error Type      | Status Code     | Content Type    |
| --------------- | --------------- | --------------- |
| models.APIError | 4XX, 5XX        | \*/\*           |

## v5_billing_consumption_get_products_consumption_stats

### Example Usage

```python
import cribl
from cribl import Cribl
import dateutil.parser
import os


with Cribl(
    bearer_auth=os.getenv("CRIBL_BEARER_AUTH", ""),
) as c_client:

    res = c_client.v5.billing.consumption.v5_billing_consumption_get_products_consumption_stats(organization_id="<id>", starting_on=dateutil.parser.isoparse("2023-01-04T00:19:37.899Z"), ending_before=dateutil.parser.isoparse("2024-03-07T13:27:22.774Z"), window=cribl.ConsumptionWindowV5.MONTHLY)

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                            | Type                                                                 | Required                                                             | Description                                                          |
| -------------------------------------------------------------------- | -------------------------------------------------------------------- | -------------------------------------------------------------------- | -------------------------------------------------------------------- |
| `organization_id`                                                    | *str*                                                                | :heavy_check_mark:                                                   | N/A                                                                  |
| `starting_on`                                                        | [date](https://docs.python.org/3/library/datetime.html#date-objects) | :heavy_check_mark:                                                   | N/A                                                                  |
| `ending_before`                                                      | [date](https://docs.python.org/3/library/datetime.html#date-objects) | :heavy_check_mark:                                                   | N/A                                                                  |
| `window`                                                             | [models.ConsumptionWindowV5](../../models/consumptionwindowv5.md)    | :heavy_check_mark:                                                   | N/A                                                                  |
| `retries`                                                            | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)     | :heavy_minus_sign:                                                   | Configuration to override the default retry behavior of the client.  |
| `server_url`                                                         | *Optional[str]*                                                      | :heavy_minus_sign:                                                   | An optional server URL to use.                                       |

### Response

**[models.GetProductsConsumptionStatsV5](../../models/getproductsconsumptionstatsv5.md)**

### Errors

| Error Type      | Status Code     | Content Type    |
| --------------- | --------------- | --------------- |
| models.APIError | 4XX, 5XX        | \*/\*           |

## v5_billing_consumption_get_credits_summary

### Example Usage

```python
import cribl
from cribl import Cribl
import dateutil.parser
import os


with Cribl(
    bearer_auth=os.getenv("CRIBL_BEARER_AUTH", ""),
) as c_client:

    res = c_client.v5.billing.consumption.v5_billing_consumption_get_credits_summary(organization_id="<id>", starting_on=dateutil.parser.isoparse("2023-08-03T02:42:25.343Z"), ending_before=dateutil.parser.isoparse("2025-11-07T19:07:23.531Z"), window=cribl.ConsumptionWindowV5.MONTHLY)

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                            | Type                                                                 | Required                                                             | Description                                                          |
| -------------------------------------------------------------------- | -------------------------------------------------------------------- | -------------------------------------------------------------------- | -------------------------------------------------------------------- |
| `organization_id`                                                    | *str*                                                                | :heavy_check_mark:                                                   | N/A                                                                  |
| `starting_on`                                                        | [date](https://docs.python.org/3/library/datetime.html#date-objects) | :heavy_check_mark:                                                   | N/A                                                                  |
| `ending_before`                                                      | [date](https://docs.python.org/3/library/datetime.html#date-objects) | :heavy_check_mark:                                                   | N/A                                                                  |
| `window`                                                             | [models.ConsumptionWindowV5](../../models/consumptionwindowv5.md)    | :heavy_check_mark:                                                   | N/A                                                                  |
| `retries`                                                            | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)     | :heavy_minus_sign:                                                   | Configuration to override the default retry behavior of the client.  |
| `server_url`                                                         | *Optional[str]*                                                      | :heavy_minus_sign:                                                   | An optional server URL to use.                                       |

### Response

**[models.GetCreditsSummaryResponseV5](../../models/getcreditssummaryresponsev5.md)**

### Errors

| Error Type      | Status Code     | Content Type    |
| --------------- | --------------- | --------------- |
| models.APIError | 4XX, 5XX        | \*/\*           |

## v5_billing_consumption_get_cumulative_consumption

### Example Usage

```python
import cribl
from cribl import Cribl
import dateutil.parser
import os


with Cribl(
    bearer_auth=os.getenv("CRIBL_BEARER_AUTH", ""),
) as c_client:

    res = c_client.v5.billing.consumption.v5_billing_consumption_get_cumulative_consumption(organization_id="<id>", starting_on=dateutil.parser.isoparse("2025-07-17T06:51:16.318Z"), ending_before=dateutil.parser.isoparse("2025-09-28T06:02:59.574Z"), window=cribl.ConsumptionWindowV5.MONTHLY)

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                            | Type                                                                 | Required                                                             | Description                                                          |
| -------------------------------------------------------------------- | -------------------------------------------------------------------- | -------------------------------------------------------------------- | -------------------------------------------------------------------- |
| `organization_id`                                                    | *str*                                                                | :heavy_check_mark:                                                   | N/A                                                                  |
| `starting_on`                                                        | [date](https://docs.python.org/3/library/datetime.html#date-objects) | :heavy_check_mark:                                                   | N/A                                                                  |
| `ending_before`                                                      | [date](https://docs.python.org/3/library/datetime.html#date-objects) | :heavy_check_mark:                                                   | N/A                                                                  |
| `window`                                                             | [models.ConsumptionWindowV5](../../models/consumptionwindowv5.md)    | :heavy_check_mark:                                                   | N/A                                                                  |
| `retries`                                                            | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)     | :heavy_minus_sign:                                                   | Configuration to override the default retry behavior of the client.  |
| `server_url`                                                         | *Optional[str]*                                                      | :heavy_minus_sign:                                                   | An optional server URL to use.                                       |

### Response

**[models.GetCumulativeConsumptionResponseV5](../../models/getcumulativeconsumptionresponsev5.md)**

### Errors

| Error Type      | Status Code     | Content Type    |
| --------------- | --------------- | --------------- |
| models.APIError | 4XX, 5XX        | \*/\*           |

## v5_billing_consumption_get_products_breakdown

### Example Usage

```python
import cribl
from cribl import Cribl
import dateutil.parser
import os


with Cribl(
    bearer_auth=os.getenv("CRIBL_BEARER_AUTH", ""),
) as c_client:

    res = c_client.v5.billing.consumption.v5_billing_consumption_get_products_breakdown(organization_id="<id>", starting_on=dateutil.parser.isoparse("2023-01-26T07:15:37.792Z"), ending_before=dateutil.parser.isoparse("2023-10-03T12:05:18.738Z"), window=cribl.ConsumptionWindowV5.MONTHLY)

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                            | Type                                                                 | Required                                                             | Description                                                          |
| -------------------------------------------------------------------- | -------------------------------------------------------------------- | -------------------------------------------------------------------- | -------------------------------------------------------------------- |
| `organization_id`                                                    | *str*                                                                | :heavy_check_mark:                                                   | N/A                                                                  |
| `starting_on`                                                        | [date](https://docs.python.org/3/library/datetime.html#date-objects) | :heavy_check_mark:                                                   | N/A                                                                  |
| `ending_before`                                                      | [date](https://docs.python.org/3/library/datetime.html#date-objects) | :heavy_check_mark:                                                   | N/A                                                                  |
| `window`                                                             | [models.ConsumptionWindowV5](../../models/consumptionwindowv5.md)    | :heavy_check_mark:                                                   | N/A                                                                  |
| `retries`                                                            | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)     | :heavy_minus_sign:                                                   | Configuration to override the default retry behavior of the client.  |
| `server_url`                                                         | *Optional[str]*                                                      | :heavy_minus_sign:                                                   | An optional server URL to use.                                       |

### Response

**[models.GetProductsBreakdownResponseV5](../../models/getproductsbreakdownresponsev5.md)**

### Errors

| Error Type      | Status Code     | Content Type    |
| --------------- | --------------- | --------------- |
| models.APIError | 4XX, 5XX        | \*/\*           |