# UpdateRoutesByPackAndIDRequest


## Fields

| Field                                          | Type                                           | Required                                       | Description                                    |
| ---------------------------------------------- | ---------------------------------------------- | ---------------------------------------------- | ---------------------------------------------- |
| `id_param`                                     | *str*                                          | :heavy_check_mark:                             | Unique ID to PATCH for pack                    |
| `pack`                                         | *str*                                          | :heavy_check_mark:                             | pack ID to PATCH                               |
| `routes`                                       | [models.RoutesInput](../models/routesinput.md) | :heavy_check_mark:                             | Routes object to be updated                    |