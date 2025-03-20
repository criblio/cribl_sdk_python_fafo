# API


## Fields

| Field                                            | Type                                             | Required                                         | Description                                      |
| ------------------------------------------------ | ------------------------------------------------ | ------------------------------------------------ | ------------------------------------------------ |
| `disabled`                                       | *bool*                                           | :heavy_check_mark:                               | N/A                                              |
| `host`                                           | *str*                                            | :heavy_check_mark:                               | N/A                                              |
| `port`                                           | *float*                                          | :heavy_check_mark:                               | N/A                                              |
| `protocol`                                       | *str*                                            | :heavy_check_mark:                               | N/A                                              |
| `ssl`                                            | [models.Ssl](../models/ssl.md)                   | :heavy_check_mark:                               | N/A                                              |
| `worker_remote_access`                           | *bool*                                           | :heavy_check_mark:                               | N/A                                              |
| `base_url`                                       | *Optional[str]*                                  | :heavy_minus_sign:                               | N/A                                              |
| `disable_api_cache`                              | *Optional[bool]*                                 | :heavy_minus_sign:                               | N/A                                              |
| `headers`                                        | [Optional[models.Headers]](../models/headers.md) | :heavy_minus_sign:                               | N/A                                              |
| `idle_session_ttl`                               | *Optional[float]*                                | :heavy_minus_sign:                               | N/A                                              |
| `login_rate_limit`                               | *Optional[str]*                                  | :heavy_minus_sign:                               | N/A                                              |
| `scripts`                                        | *Optional[bool]*                                 | :heavy_minus_sign:                               | N/A                                              |
| `sensitive_fields`                               | List[*str*]                                      | :heavy_minus_sign:                               | N/A                                              |
| `sso_rate_limit`                                 | *Optional[str]*                                  | :heavy_minus_sign:                               | N/A                                              |