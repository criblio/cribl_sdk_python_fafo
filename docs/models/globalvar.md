# GlobalVar


## Fields

| Field                                                        | Type                                                         | Required                                                     | Description                                                  |
| ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
| `id`                                                         | *str*                                                        | :heavy_check_mark:                                           | Global variable name.                                        |
| `lib`                                                        | *Optional[str]*                                              | :heavy_minus_sign:                                           | N/A                                                          |
| `description`                                                | *Optional[str]*                                              | :heavy_minus_sign:                                           | Brief description of this variable. Optional.                |
| `type`                                                       | [Optional[models.GlobalVarType]](../models/globalvartype.md) | :heavy_minus_sign:                                           | Type of variable                                             |
| `value`                                                      | *Optional[str]*                                              | :heavy_minus_sign:                                           | Value of variable                                            |
| `tags`                                                       | *Optional[str]*                                              | :heavy_minus_sign:                                           | One or more tags related to this variable. Optional.         |