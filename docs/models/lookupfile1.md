# LookupFile1


## Fields

| Field                                                            | Type                                                             | Required                                                         | Description                                                      |
| ---------------------------------------------------------------- | ---------------------------------------------------------------- | ---------------------------------------------------------------- | ---------------------------------------------------------------- |
| `file_info`                                                      | [Optional[models.FileInfo]](../models/fileinfo.md)               | :heavy_minus_sign:                                               | N/A                                                              |
| `id`                                                             | *str*                                                            | :heavy_check_mark:                                               | N/A                                                              |
| `description`                                                    | *Optional[str]*                                                  | :heavy_minus_sign:                                               | N/A                                                              |
| `tags`                                                           | *Optional[str]*                                                  | :heavy_minus_sign:                                               | One or more tags related to this lookup. Optional.               |
| `size`                                                           | *Optional[float]*                                                | :heavy_minus_sign:                                               | File size. Optional.                                             |
| `version`                                                        | *Optional[str]*                                                  | :heavy_minus_sign:                                               | Unique string generated for each modification of this lookup     |
| `mode`                                                           | [Optional[models.LookupFileMode1]](../models/lookupfilemode1.md) | :heavy_minus_sign:                                               | N/A                                                              |
| `pending_task`                                                   | [Optional[models.PendingTask1]](../models/pendingtask1.md)       | :heavy_minus_sign:                                               | N/A                                                              |