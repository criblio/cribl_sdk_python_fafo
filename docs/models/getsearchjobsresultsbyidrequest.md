# GetSearchJobsResultsByIDRequest


## Fields

| Field                                    | Type                                     | Required                                 | Description                              |
| ---------------------------------------- | ---------------------------------------- | ---------------------------------------- | ---------------------------------------- |
| `id`                                     | *str*                                    | :heavy_check_mark:                       | search job id                            |
| `limit`                                  | *Optional[float]*                        | :heavy_minus_sign:                       | maximum number of events returned        |
| `offset`                                 | *Optional[float]*                        | :heavy_minus_sign:                       | starting offset of the events            |
| `lower_bound`                            | *Optional[float]*                        | :heavy_minus_sign:                       | lower bound of the time range, inclusive |
| `upper_bound`                            | *Optional[float]*                        | :heavy_minus_sign:                       | upper bound of the time range, exclusive |