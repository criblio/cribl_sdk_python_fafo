# CreateEdgeFileIngestRequest


## Fields

| Field                                                           | Type                                                            | Required                                                        | Description                                                     |
| --------------------------------------------------------------- | --------------------------------------------------------------- | --------------------------------------------------------------- | --------------------------------------------------------------- |
| `file_path`                                                     | *Optional[str]*                                                 | :heavy_minus_sign:                                              | Absolute path to file to ingest.                                |
| `pipeline_id`                                                   | *Optional[str]*                                                 | :heavy_minus_sign:                                              | Id of the pipeline to use.                                      |
| `output_id`                                                     | *Optional[str]*                                                 | :heavy_minus_sign:                                              | Destination to send events to.                                  |
| `pre_processing_pipeline_id`                                    | *Optional[str]*                                                 | :heavy_minus_sign:                                              | Id to the pre-processing pipeline to use for routes.            |
| `send_to_routes`                                                | *Optional[str]*                                                 | :heavy_minus_sign:                                              | boolean condition required on whether to send events to routes. |
| `breaker_rule_set`                                              | *Optional[str]*                                                 | :heavy_minus_sign:                                              | Breaker rules to use on the file.                               |