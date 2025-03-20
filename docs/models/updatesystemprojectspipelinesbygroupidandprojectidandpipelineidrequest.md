# UpdateSystemProjectsPipelinesByGroupIDAndProjectIDAndPipelineIDRequest


## Fields

| Field                                              | Type                                               | Required                                           | Description                                        |
| -------------------------------------------------- | -------------------------------------------------- | -------------------------------------------------- | -------------------------------------------------- |
| `group_id`                                         | *str*                                              | :heavy_check_mark:                                 | Group Id                                           |
| `project_id`                                       | *str*                                              | :heavy_check_mark:                                 | Project Id                                         |
| `pipeline_id`                                      | *str*                                              | :heavy_check_mark:                                 | Pipeline iD                                        |
| `pipeline`                                         | [models.Pipeline](../models/pipeline.md)           | :heavy_check_mark:                                 | Pipeline object to be updated in specified Project |