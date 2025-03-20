# UpdateSchemaLibByPackAndIDRequest


## Fields

| Field                                                | Type                                                 | Required                                             | Description                                          |
| ---------------------------------------------------- | ---------------------------------------------------- | ---------------------------------------------------- | ---------------------------------------------------- |
| `id_param`                                           | *str*                                                | :heavy_check_mark:                                   | Unique ID to PATCH for pack                          |
| `pack`                                               | *str*                                                | :heavy_check_mark:                                   | pack ID to PATCH                                     |
| `schema_lib_entry`                                   | [models.SchemaLibEntry](../models/schemalibentry.md) | :heavy_check_mark:                                   | Schema object to be updated                          |