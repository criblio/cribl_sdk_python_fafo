<!-- Start SDK Example Usage [usage] -->
```python
# Synchronous Example
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

</br>

The same SDK client can also be used to make asychronous requests by importing asyncio.
```python
# Asynchronous Example
import asyncio
import cribl
from cribl import Cribl
import dateutil.parser
import os

async def main():

    async with Cribl(
        bearer_auth=os.getenv("CRIBL_BEARER_AUTH", ""),
    ) as c_client:

        res = await c_client.v5.billing.consumption.v5_billing_consumption_get_single_product_usage_breakdown_async(organization_id="<id>", product_slug=cribl.ProductSlug.SEARCH, starting_on=dateutil.parser.isoparse("2023-11-28T21:49:04.925Z"), ending_before=dateutil.parser.isoparse("2025-09-09T13:52:53.788Z"), window=cribl.ConsumptionWindowV5.MONTHLY)

        # Handle response
        print(res)

asyncio.run(main())
```
<!-- End SDK Example Usage [usage] -->