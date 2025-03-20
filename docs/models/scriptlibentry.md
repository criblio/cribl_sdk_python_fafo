# ScriptLibEntry


## Fields

| Field                                                    | Type                                                     | Required                                                 | Description                                              |
| -------------------------------------------------------- | -------------------------------------------------------- | -------------------------------------------------------- | -------------------------------------------------------- |
| `id`                                                     | *str*                                                    | :heavy_check_mark:                                       | N/A                                                      |
| `command`                                                | *str*                                                    | :heavy_check_mark:                                       | Command to execute for this script                       |
| `description`                                            | *Optional[str]*                                          | :heavy_minus_sign:                                       | N/A                                                      |
| `args`                                                   | List[*str*]                                              | :heavy_minus_sign:                                       | Arguments to pass when executing this script             |
| `env`                                                    | Dict[str, *str*]                                         | :heavy_minus_sign:                                       | Extra environment variables to set when executing script |
| `__pydantic_extra__`                                     | Dict[str, *Any*]                                         | :heavy_minus_sign:                                       | N/A                                                      |