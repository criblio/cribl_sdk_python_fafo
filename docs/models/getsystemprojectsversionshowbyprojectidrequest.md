# GetSystemProjectsVersionShowByProjectIDRequest


## Fields

| Field                           | Type                            | Required                        | Description                     |
| ------------------------------- | ------------------------------- | ------------------------------- | ------------------------------- |
| `project_id`                    | *str*                           | :heavy_check_mark:              | Project Id                      |
| `id`                            | *Optional[str]*                 | :heavy_minus_sign:              | Commit ID                       |
| `filename`                      | *Optional[str]*                 | :heavy_minus_sign:              | Filename                        |
| `diff_line_limit`               | *Optional[float]*               | :heavy_minus_sign:              | Limit maximum lines in the diff |