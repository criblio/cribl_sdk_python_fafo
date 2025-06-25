<!-- Start SDK Example Usage [usage] -->
```python
# Synchronous Example
from cribl_sdk_python_fafo import CriblSDKPythonFafo, models
import os


with CriblSDKPythonFafo(
    server_url="https://api.example.com",
    security=models.Security(
        bearer_auth=os.getenv("CRIBLSDKPYTHONFAFO_BEARER_AUTH", ""),
    ),
) as cspf_client:

    res = cspf_client.projects.get_system_projects_subscriptions_by_group_id_by_and_project_id(group_id="<id>", project_id="<id>")

    # Handle response
    print(res)
```

</br>

The same SDK client can also be used to make asychronous requests by importing asyncio.
```python
# Asynchronous Example
import asyncio
from cribl_sdk_python_fafo import CriblSDKPythonFafo, models
import os

async def main():

    async with CriblSDKPythonFafo(
        server_url="https://api.example.com",
        security=models.Security(
            bearer_auth=os.getenv("CRIBLSDKPYTHONFAFO_BEARER_AUTH", ""),
        ),
    ) as cspf_client:

        res = await cspf_client.projects.get_system_projects_subscriptions_by_group_id_by_and_project_id_async(group_id="<id>", project_id="<id>")

        # Handle response
        print(res)

asyncio.run(main())
```
<!-- End SDK Example Usage [usage] -->