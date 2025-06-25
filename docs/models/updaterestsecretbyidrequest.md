# UpdateRestSecretByIDRequest


## Fields

| Field                                        | Type                                         | Required                                     | Description                                  |
| -------------------------------------------- | -------------------------------------------- | -------------------------------------------- | -------------------------------------------- |
| `id_param`                                   | *str*                                        | :heavy_check_mark:                           | Unique ID to PATCH                           |
| `rest_secret`                                | [models.RestSecret](../models/restsecret.md) | :heavy_check_mark:                           | RestSecret object to be updated              |