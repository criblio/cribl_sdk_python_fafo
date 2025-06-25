# FieldT


## Fields

| Field                                          | Type                                           | Required                                       | Description                                    |
| ---------------------------------------------- | ---------------------------------------------- | ---------------------------------------------- | ---------------------------------------------- |
| `buckets`                                      | List[[models.Bucket](../models/bucket.md)]     | :heavy_check_mark:                             | N/A                                            |
| `count`                                        | *float*                                        | :heavy_check_mark:                             | N/A                                            |
| `count_distinct`                               | *float*                                        | :heavy_check_mark:                             | N/A                                            |
| `count_null`                                   | *float*                                        | :heavy_check_mark:                             | N/A                                            |
| `max`                                          | [Optional[models.Max]](../models/max.md)       | :heavy_minus_sign:                             | N/A                                            |
| `mean`                                         | *Optional[float]*                              | :heavy_minus_sign:                             | N/A                                            |
| `min`                                          | [Optional[models.Min]](../models/min.md)       | :heavy_minus_sign:                             | N/A                                            |
| `name`                                         | *str*                                          | :heavy_check_mark:                             | N/A                                            |
| `stdev`                                        | *Optional[float]*                              | :heavy_minus_sign:                             | N/A                                            |
| `top_values`                                   | List[[models.TopValue](../models/topvalue.md)] | :heavy_check_mark:                             | N/A                                            |
| `type`                                         | [models.FieldType](../models/fieldtype.md)     | :heavy_check_mark:                             | N/A                                            |