# SamplesModel


## Fields

| Field                                                                         | Type                                                                          | Required                                                                      | Description                                                                   |
| ----------------------------------------------------------------------------- | ----------------------------------------------------------------------------- | ----------------------------------------------------------------------------- | ----------------------------------------------------------------------------- |
| `sample`                                                                      | *str*                                                                         | :heavy_check_mark:                                                            | Name of the datagen file                                                      |
| `events_per_sec`                                                              | *Optional[float]*                                                             | :heavy_minus_sign:                                                            | Maximum no. of events to generate per second per worker node. Defaults to 10. |