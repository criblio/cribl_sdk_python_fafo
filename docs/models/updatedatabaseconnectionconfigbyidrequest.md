# UpdateDatabaseConnectionConfigByIDRequest


## Fields

| Field                                                                    | Type                                                                     | Required                                                                 | Description                                                              |
| ------------------------------------------------------------------------ | ------------------------------------------------------------------------ | ------------------------------------------------------------------------ | ------------------------------------------------------------------------ |
| `id_param`                                                               | *str*                                                                    | :heavy_check_mark:                                                       | Unique ID to PATCH                                                       |
| `database_connection_config`                                             | [models.DatabaseConnectionConfig](../models/databaseconnectionconfig.md) | :heavy_check_mark:                                                       | DatabaseConnectionConfig object to be updated                            |