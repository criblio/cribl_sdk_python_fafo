# API


## Fields

| Field                                            | Type                                             | Required                                         | Description                                      |
| ------------------------------------------------ | ------------------------------------------------ | ------------------------------------------------ | ------------------------------------------------ |
| `base_url`                                       | *Optional[str]*                                  | :heavy_minus_sign:                               | N/A                                              |
| `disable_api_cache`                              | *Optional[bool]*                                 | :heavy_minus_sign:                               | N/A                                              |
| `disabled`                                       | *bool*                                           | :heavy_check_mark:                               | N/A                                              |
| `headers`                                        | [Optional[models.Headers]](../models/headers.md) | :heavy_minus_sign:                               | N/A                                              |
| `host`                                           | *str*                                            | :heavy_check_mark:                               | N/A                                              |
| `idle_session_ttl`                               | *Optional[float]*                                | :heavy_minus_sign:                               | N/A                                              |
| `listen_on_port`                                 | *Optional[bool]*                                 | :heavy_minus_sign:                               | N/A                                              |
| `login_rate_limit`                               | *Optional[str]*                                  | :heavy_minus_sign:                               | N/A                                              |
| `port`                                           | *float*                                          | :heavy_check_mark:                               | N/A                                              |
| `protocol`                                       | *str*                                            | :heavy_check_mark:                               | N/A                                              |
| `scripts`                                        | *Optional[bool]*                                 | :heavy_minus_sign:                               | N/A                                              |
| `sensitive_fields`                               | List[*str*]                                      | :heavy_minus_sign:                               | N/A                                              |
| `ssl`                                            | [models.Ssl](../models/ssl.md)                   | :heavy_check_mark:                               | N/A                                              |
| `sso_rate_limit`                                 | *Optional[str]*                                  | :heavy_minus_sign:                               | N/A                                              |
| `worker_remote_access`                           | *bool*                                           | :heavy_check_mark:                               | N/A                                              |