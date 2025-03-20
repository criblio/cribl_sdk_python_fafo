# LoggerConfig


## Fields

| Field                                                | Type                                                 | Required                                             | Description                                          |
| ---------------------------------------------------- | ---------------------------------------------------- | ---------------------------------------------------- | ---------------------------------------------------- |
| `channels`                                           | List[[models.LoggerEntry](../models/loggerentry.md)] | :heavy_check_mark:                                   | N/A                                                  |
| `id`                                                 | *str*                                                | :heavy_check_mark:                                   | N/A                                                  |
| `limit_rate`                                         | *float*                                              | :heavy_check_mark:                                   | N/A                                                  |
| `max_size_bytes`                                     | *float*                                              | :heavy_check_mark:                                   | N/A                                                  |
| `redact_fields`                                      | List[*str*]                                          | :heavy_check_mark:                                   | N/A                                                  |
| `redact_label`                                       | *str*                                                | :heavy_check_mark:                                   | N/A                                                  |
| `default_redact_fields`                              | List[*str*]                                          | :heavy_minus_sign:                                   | N/A                                                  |