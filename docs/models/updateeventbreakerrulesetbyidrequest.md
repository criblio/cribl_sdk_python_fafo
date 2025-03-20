# UpdateEventBreakerRulesetByIDRequest


## Fields

| Field                                                          | Type                                                           | Required                                                       | Description                                                    |
| -------------------------------------------------------------- | -------------------------------------------------------------- | -------------------------------------------------------------- | -------------------------------------------------------------- |
| `id_param`                                                     | *str*                                                          | :heavy_check_mark:                                             | Unique ID to PATCH                                             |
| `event_breaker_ruleset`                                        | [models.EventBreakerRuleset](../models/eventbreakerruleset.md) | :heavy_check_mark:                                             | Event Breaker Ruleset object to be updated                     |