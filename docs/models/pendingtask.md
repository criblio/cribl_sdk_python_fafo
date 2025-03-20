# PendingTask


## Fields

| Field                                                          | Type                                                           | Required                                                       | Description                                                    |
| -------------------------------------------------------------- | -------------------------------------------------------------- | -------------------------------------------------------------- | -------------------------------------------------------------- |
| `id`                                                           | *Optional[str]*                                                | :heavy_minus_sign:                                             | Task ID (generated).                                           |
| `type`                                                         | [Optional[models.LookupFileType]](../models/lookupfiletype.md) | :heavy_minus_sign:                                             | Task type                                                      |
| `error`                                                        | *Optional[str]*                                                | :heavy_minus_sign:                                             | Error message if task has failed                               |