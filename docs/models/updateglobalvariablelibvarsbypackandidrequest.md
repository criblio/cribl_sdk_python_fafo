# UpdateGlobalVariableLibVarsByPackAndIDRequest


## Fields

| Field                                      | Type                                       | Required                                   | Description                                |
| ------------------------------------------ | ------------------------------------------ | ------------------------------------------ | ------------------------------------------ |
| `id_param`                                 | *str*                                      | :heavy_check_mark:                         | Unique ID to PATCH for pack                |
| `pack`                                     | *str*                                      | :heavy_check_mark:                         | pack ID to PATCH                           |
| `global_var`                               | [models.GlobalVar](../models/globalvar.md) | :heavy_check_mark:                         | Global Variable object to be updated       |