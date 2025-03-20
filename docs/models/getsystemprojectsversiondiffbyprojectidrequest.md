# GetSystemProjectsVersionDiffByProjectIDRequest


## Fields

| Field                           | Type                            | Required                        | Description                     |
| ------------------------------- | ------------------------------- | ------------------------------- | ------------------------------- |
| `project_id`                    | *str*                           | :heavy_check_mark:              | Project Id                      |
| `commit`                        | *Optional[str]*                 | :heavy_minus_sign:              | Commit hash (default is HEAD)   |
| `filename`                      | *Optional[str]*                 | :heavy_minus_sign:              | Filename                        |
| `diff_line_limit`               | *Optional[float]*               | :heavy_minus_sign:              | Limit maximum lines in the diff |