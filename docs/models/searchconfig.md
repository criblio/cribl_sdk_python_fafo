# SearchConfig


## Fields

| Field                                                | Type                                                 | Required                                             | Description                                          |
| ---------------------------------------------------- | ---------------------------------------------------- | ---------------------------------------------------- | ---------------------------------------------------- |
| `datasets`                                           | List[*str*]                                          | :heavy_check_mark:                                   | N/A                                                  |
| `has_send_operator`                                  | *bool*                                               | :heavy_check_mark:                                   | N/A                                                  |
| `ordered_field_names`                                | List[*str*]                                          | :heavy_check_mark:                                   | N/A                                                  |
| `search_terms`                                       | List[[models.SearchTerm](../models/searchterm.md)]   | :heavy_check_mark:                                   | N/A                                                  |
| `use_formatted_visualization`                        | *bool*                                               | :heavy_check_mark:                                   | N/A                                                  |
| `can_compute_metadata_distributively`                | *Optional[bool]*                                     | :heavy_minus_sign:                                   | N/A                                                  |
| `referenced_field_names`                             | List[*str*]                                          | :heavy_minus_sign:                                   | N/A                                                  |
| `sort_fields`                                        | List[[models.SortByField](../models/sortbyfield.md)] | :heavy_minus_sign:                                   | N/A                                                  |