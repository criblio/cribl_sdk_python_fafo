# ParserLibEntry


## Fields

| Field                                                                  | Type                                                                   | Required                                                               | Description                                                            |
| ---------------------------------------------------------------------- | ---------------------------------------------------------------------- | ---------------------------------------------------------------------- | ---------------------------------------------------------------------- |
| `id`                                                                   | *str*                                                                  | :heavy_check_mark:                                                     | N/A                                                                    |
| `lib`                                                                  | *Optional[str]*                                                        | :heavy_minus_sign:                                                     | N/A                                                                    |
| `description`                                                          | *Optional[str]*                                                        | :heavy_minus_sign:                                                     | Brief description of this parser (optional)                            |
| `tags`                                                                 | *Optional[str]*                                                        | :heavy_minus_sign:                                                     | One or more tags related to this parser (optional)                     |
| `type`                                                                 | [Optional[models.ParserLibEntryType]](../models/parserlibentrytype.md) | :heavy_minus_sign:                                                     | Parser or formatter type to use                                        |
| `__pydantic_extra__`                                                   | Dict[str, *Any*]                                                       | :heavy_minus_sign:                                                     | N/A                                                                    |