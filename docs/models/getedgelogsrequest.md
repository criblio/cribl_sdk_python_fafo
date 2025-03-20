# GetEdgeLogsRequest


## Fields

| Field                                                                   | Type                                                                    | Required                                                                | Description                                                             |
| ----------------------------------------------------------------------- | ----------------------------------------------------------------------- | ----------------------------------------------------------------------- | ----------------------------------------------------------------------- |
| `mode`                                                                  | *Optional[str]*                                                         | :heavy_minus_sign:                                                      | Discovery Mode (default is "auto")                                      |
| `allow`                                                                 | *Optional[str]*                                                         | :heavy_minus_sign:                                                      | query array[string] optional List of allowed-filename wildcard patterns |
| `path`                                                                  | *Optional[str]*                                                         | :heavy_minus_sign:                                                      | Search directory for "manual" mode                                      |
| `depth`                                                                 | *Optional[float]*                                                       | :heavy_minus_sign:                                                      | Search depth for "manual" mode                                          |