# LookupFile1Input


## Fields

| Field                                                          | Type                                                           | Required                                                       | Description                                                    |
| -------------------------------------------------------------- | -------------------------------------------------------------- | -------------------------------------------------------------- | -------------------------------------------------------------- |
| `file_info`                                                    | [Optional[models.FileInfo]](../models/fileinfo.md)             | :heavy_minus_sign:                                             | N/A                                                            |
| `id`                                                           | *str*                                                          | :heavy_check_mark:                                             | N/A                                                            |
| `description`                                                  | *Optional[str]*                                                | :heavy_minus_sign:                                             | N/A                                                            |
| `tags`                                                         | *Optional[str]*                                                | :heavy_minus_sign:                                             | One or more tags related to this lookup. Optional.             |
| `size`                                                         | *Optional[float]*                                              | :heavy_minus_sign:                                             | File size. Optional.                                           |
| `mode`                                                         | [Optional[models.LookupFileMode]](../models/lookupfilemode.md) | :heavy_minus_sign:                                             | Operation mode for CSV-based lookups                           |