# SearchQueryMetric


## Fields

| Field                                                                  | Type                                                                   | Required                                                               | Description                                                            |
| ---------------------------------------------------------------------- | ---------------------------------------------------------------------- | ---------------------------------------------------------------------- | ---------------------------------------------------------------------- |
| `earliest`                                                             | [models.SearchQueryEarliest2](../models/searchqueryearliest2.md)       | :heavy_check_mark:                                                     | N/A                                                                    |
| `is_monitoring`                                                        | *Optional[bool]*                                                       | :heavy_minus_sign:                                                     | N/A                                                                    |
| `latest`                                                               | [models.SearchQueryLatest2](../models/searchquerylatest2.md)           | :heavy_check_mark:                                                     | N/A                                                                    |
| `queries`                                                              | List[[models.PanelQueryDefinition](../models/panelquerydefinition.md)] | :heavy_check_mark:                                                     | N/A                                                                    |
| `timezone`                                                             | *Optional[str]*                                                        | :heavy_minus_sign:                                                     | N/A                                                                    |
| `type`                                                                 | [models.TypeMetric](../models/typemetric.md)                           | :heavy_check_mark:                                                     | N/A                                                                    |