# GetJobsRequest


## Fields

| Field                                                    | Type                                                     | Required                                                 | Description                                              |
| -------------------------------------------------------- | -------------------------------------------------------- | -------------------------------------------------------- | -------------------------------------------------------- |
| `offset`                                                 | *Optional[int]*                                          | :heavy_minus_sign:                                       | Pagination offset                                        |
| `limit`                                                  | *Optional[int]*                                          | :heavy_minus_sign:                                       | Maximum number of items to return                        |
| `run_type`                                               | [Optional[models.RunType]](../models/runtype.md)         | :heavy_minus_sign:                                       | Filter by job run type                                   |
| `state`                                                  | *Optional[str]*                                          | :heavy_minus_sign:                                       | Filter by current job state, e.g. "running"              |
| `id`                                                     | *Optional[str]*                                          | :heavy_minus_sign:                                       | Filter by job id, e.g. "id=1608713335.3&id=1608713326.1" |
| `collector_id`                                           | *Optional[str]*                                          | :heavy_minus_sign:                                       | Filter by collector id, e.g. "collectorId=Prometheus-in" |
| `group_id`                                               | *Optional[str]*                                          | :heavy_minus_sign:                                       | Filter by worker group id, e.g. "defaultHybrid"          |