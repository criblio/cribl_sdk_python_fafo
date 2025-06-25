# LookupFile2


## Fields

| Field                                                            | Type                                                             | Required                                                         | Description                                                      |
| ---------------------------------------------------------------- | ---------------------------------------------------------------- | ---------------------------------------------------------------- | ---------------------------------------------------------------- |
| `content`                                                        | *Optional[str]*                                                  | :heavy_minus_sign:                                               | File content.                                                    |
| `id`                                                             | *str*                                                            | :heavy_check_mark:                                               | N/A                                                              |
| `description`                                                    | *Optional[str]*                                                  | :heavy_minus_sign:                                               | N/A                                                              |
| `tags`                                                           | *Optional[str]*                                                  | :heavy_minus_sign:                                               | One or more tags related to this lookup. Optional.               |
| `size`                                                           | *Optional[float]*                                                | :heavy_minus_sign:                                               | File size. Optional.                                             |
| `version`                                                        | *Optional[str]*                                                  | :heavy_minus_sign:                                               | Unique string generated for each modification of this lookup     |
| `mode`                                                           | [Optional[models.LookupFileMode2]](../models/lookupfilemode2.md) | :heavy_minus_sign:                                               | N/A                                                              |
| `pending_task`                                                   | [Optional[models.PendingTask2]](../models/pendingtask2.md)       | :heavy_minus_sign:                                               | N/A                                                              |