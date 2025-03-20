<!-- Start SDK Example Usage [usage] -->
```python
# Synchronous Example
import cribl
from cribl import Cribl
import os


with Cribl(
    server_url="https://api.example.com",
    bearer_auth=os.getenv("CRIBL_BEARER_AUTH", ""),
) as c_client:

    res = c_client.billing.get_usage(organization_id="<id>", metric_type=cribl.MetricType.HYBRID_WORKER_G_BS_RECEIVED, starting_on="<value>", ending_before="<value>")

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
import os

async def main():

    async with Cribl(
        server_url="https://api.example.com",
        bearer_auth=os.getenv("CRIBL_BEARER_AUTH", ""),
    ) as c_client:

        res = await c_client.billing.get_usage_async(organization_id="<id>", metric_type=cribl.MetricType.HYBRID_WORKER_G_BS_RECEIVED, starting_on="<value>", ending_before="<value>")

        # Handle response
        print(res)

asyncio.run(main())
```
<!-- End SDK Example Usage [usage] -->