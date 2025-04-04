# GetJobsResultsByIDAndGroupRequest


## Fields

| Field                                     | Type                                      | Required                                  | Description                               |
| ----------------------------------------- | ----------------------------------------- | ----------------------------------------- | ----------------------------------------- |
| `id`                                      | *str*                                     | :heavy_check_mark:                        | Instance id of the job to get results for |
| `max_files`                               | *Optional[float]*                         | :heavy_minus_sign:                        | Maximum files to get job results          |
| `group`                                   | *str*                                     | :heavy_check_mark:                        | Group the job belongs to                  |