# SavedQuerySchedule


## Fields

| Field                                                        | Type                                                         | Required                                                     | Description                                                  |
| ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
| `cron_schedule`                                              | *str*                                                        | :heavy_check_mark:                                           | N/A                                                          |
| `enabled`                                                    | *bool*                                                       | :heavy_check_mark:                                           | N/A                                                          |
| `keep_last_n`                                                | *float*                                                      | :heavy_check_mark:                                           | N/A                                                          |
| `notifications`                                              | [models.NotificationsModel](../models/notificationsmodel.md) | :heavy_check_mark:                                           | N/A                                                          |
| `resume_missed`                                              | *Optional[bool]*                                             | :heavy_minus_sign:                                           | N/A                                                          |
| `resume_on_boot`                                             | *Optional[bool]*                                             | :heavy_minus_sign:                                           | N/A                                                          |
| `tz`                                                         | *str*                                                        | :heavy_check_mark:                                           | N/A                                                          |