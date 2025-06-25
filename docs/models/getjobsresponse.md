# GetJobsResponse

a list of JobInfo objects


## Fields

| Field                                        | Type                                         | Required                                     | Description                                  |
| -------------------------------------------- | -------------------------------------------- | -------------------------------------------- | -------------------------------------------- |
| `offset`                                     | *Optional[int]*                              | :heavy_minus_sign:                           | pagination offset                            |
| `limit`                                      | *Optional[int]*                              | :heavy_minus_sign:                           | number of items present in the items array   |
| `items`                                      | List[[models.JobInfo](../models/jobinfo.md)] | :heavy_minus_sign:                           | the pre-limited items in the list of results |