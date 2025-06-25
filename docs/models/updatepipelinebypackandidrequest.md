# UpdatePipelineByPackAndIDRequest


## Fields

| Field                                    | Type                                     | Required                                 | Description                              |
| ---------------------------------------- | ---------------------------------------- | ---------------------------------------- | ---------------------------------------- |
| `id_param`                               | *str*                                    | :heavy_check_mark:                       | Unique ID to PATCH for pack              |
| `pack`                                   | *str*                                    | :heavy_check_mark:                       | pack ID to PATCH                         |
| `pipeline`                               | [models.Pipeline](../models/pipeline.md) | :heavy_check_mark:                       | Pipeline object to be updated            |