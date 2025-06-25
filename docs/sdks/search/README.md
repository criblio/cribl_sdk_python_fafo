# Search
(*search*)

## Overview

Actions related to Search

### Available Operations

* [list_search_job](#list_search_job) - Get a list of SearchJob objects
* [create_search_job](#create_search_job) - Create SearchJob
* [get_search_job_by_id](#get_search_job_by_id) - Get SearchJob by ID
* [update_search_job_by_id](#update_search_job_by_id) - Update SearchJob
* [delete_search_job_by_id](#delete_search_job_by_id) - Delete SearchJob
* [create_search_job_dispatch_executors_by_id](#create_search_job_dispatch_executors_by_id) - internal endpoint, dispatch search *id* to worker nodes filtered by worker node filter using RPC
* [get_search_job_settings_by_id](#get_search_job_settings_by_id) - Get search job settings
* [create_search_job_settings_by_id](#create_search_job_settings_by_id) - Save search job settings
* [get_search_job_status_by_id](#get_search_job_status_by_id) - Get job status
* [get_search_job_timeline_by_id](#get_search_job_timeline_by_id) - Get search timeline
* [get_search_job_field_summaries_by_id](#get_search_job_field_summaries_by_id) - List field summaries
* [get_search_job_logs_by_id](#get_search_job_logs_by_id) - Get search logs
* [create_search_event_breaker_preview](#create_search_event_breaker_preview) - Runs an event breaker rule on the specified data
* [get_search_docs](#get_search_docs) - Get Search documentation
* [get_search_healthcheck](#get_search_healthcheck) - Get health check metric for search
* [get_search_jobs_metrics_by_id](#get_search_jobs_metrics_by_id) - Get search job metrics
* [get_search_job_metrics](#get_search_job_metrics) - List metrics for all search jobs
* [create_search_preview](#create_search_preview) - Applies a query snippet on a set of input events for preview
* [get_search_jobs_diag_by_id](#get_search_jobs_diag_by_id) - Get full search job data
* [get_search_jobs_logs_by_id_and_filename](#get_search_jobs_logs_by_id_and_filename) - Get the contents of a log file
* [get_search_jobs_stages_results_by_id_and_stage_id](#get_search_jobs_stages_results_by_id_and_stage_id) - List search results for a given stage. Note that this cannot be the root stage!
* [get_search_jobs_results_by_id](#get_search_jobs_results_by_id) - List search results, when lower/upper bound is provided, offset is relative to the time range.
* [get_search_jobs_results_poll_by_id](#get_search_jobs_results_poll_by_id) - List search results

## list_search_job

Get a list of SearchJob objects

### Example Usage

```python
from cribl_sdk_python_fafo import CriblSDKPythonFafo, models
import os


with CriblSDKPythonFafo(
    server_url="https://api.example.com",
    security=models.Security(
        bearer_auth=os.getenv("CRIBLSDKPYTHONFAFO_BEARER_AUTH", ""),
    ),
) as cspf_client:

    res = cspf_client.search.list_search_job()

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.ListSearchJobResponse](../../models/listsearchjobresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| errors.Error     | 500              | application/json |
| errors.APIError  | 4XX, 5XX         | \*/\*            |

## create_search_job

Create SearchJob

### Example Usage

```python
from cribl_sdk_python_fafo import CriblSDKPythonFafo, models
import os


with CriblSDKPythonFafo(
    server_url="https://api.example.com",
    security=models.Security(
        bearer_auth=os.getenv("CRIBLSDKPYTHONFAFO_BEARER_AUTH", ""),
    ),
) as cspf_client:

    res = cspf_client.search.create_search_job(display_username="<value>", group="<value>", id="<id>", query="<value>", status=models.SearchJobStatus.CANCELED, time_created=328.87, time_started=4693.49, user="Alena71")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                                               | Type                                                                                    | Required                                                                                | Description                                                                             |
| --------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------- |
| `display_username`                                                                      | *str*                                                                                   | :heavy_check_mark:                                                                      | N/A                                                                                     |
| `group`                                                                                 | *str*                                                                                   | :heavy_check_mark:                                                                      | N/A                                                                                     |
| `id`                                                                                    | *str*                                                                                   | :heavy_check_mark:                                                                      | N/A                                                                                     |
| `query`                                                                                 | *str*                                                                                   | :heavy_check_mark:                                                                      | N/A                                                                                     |
| `status`                                                                                | [models.SearchJobStatus](../../models/searchjobstatus.md)                               | :heavy_check_mark:                                                                      | N/A                                                                                     |
| `time_created`                                                                          | *float*                                                                                 | :heavy_check_mark:                                                                      | N/A                                                                                     |
| `time_started`                                                                          | *float*                                                                                 | :heavy_check_mark:                                                                      | N/A                                                                                     |
| `user`                                                                                  | *str*                                                                                   | :heavy_check_mark:                                                                      | N/A                                                                                     |
| `accelerated`                                                                           | *Optional[bool]*                                                                        | :heavy_minus_sign:                                                                      | N/A                                                                                     |
| `alias_of_original_job_id`                                                              | *Optional[str]*                                                                         | :heavy_minus_sign:                                                                      | N/A                                                                                     |
| `compatibility_checks`                                                                  | [Optional[models.CompatibilityChecks]](../../models/compatibilitychecks.md)             | :heavy_minus_sign:                                                                      | N/A                                                                                     |
| `completion_info`                                                                       | *Optional[str]*                                                                         | :heavy_minus_sign:                                                                      | N/A                                                                                     |
| `context`                                                                               | *Optional[str]*                                                                         | :heavy_minus_sign:                                                                      | N/A                                                                                     |
| `correlation_id`                                                                        | *Optional[str]*                                                                         | :heavy_minus_sign:                                                                      | N/A                                                                                     |
| `cpu_metrics`                                                                           | [Optional[models.CPUTimeMetric]](../../models/cputimemetric.md)                         | :heavy_minus_sign:                                                                      | N/A                                                                                     |
| `datatype_overrides`                                                                    | [Optional[models.DatatypeOverrides]](../../models/datatypeoverrides.md)                 | :heavy_minus_sign:                                                                      | N/A                                                                                     |
| `disable_notifications`                                                                 | *Optional[bool]*                                                                        | :heavy_minus_sign:                                                                      | N/A                                                                                     |
| `earliest`                                                                              | [Optional[models.SearchJobEarliest]](../../models/searchjobearliest.md)                 | :heavy_minus_sign:                                                                      | N/A                                                                                     |
| `earliest_epoch`                                                                        | *Optional[float]*                                                                       | :heavy_minus_sign:                                                                      | N/A                                                                                     |
| `error_state_config`                                                                    | [Optional[models.SearchJobErrorStateConfig]](../../models/searchjoberrorstateconfig.md) | :heavy_minus_sign:                                                                      | N/A                                                                                     |
| `is_private`                                                                            | *Optional[bool]*                                                                        | :heavy_minus_sign:                                                                      | N/A                                                                                     |
| `latest`                                                                                | [Optional[models.SearchJobLatest]](../../models/searchjoblatest.md)                     | :heavy_minus_sign:                                                                      | N/A                                                                                     |
| `latest_epoch`                                                                          | *Optional[float]*                                                                       | :heavy_minus_sign:                                                                      | N/A                                                                                     |
| `metadata`                                                                              | [Optional[models.SearchJobMetadata]](../../models/searchjobmetadata.md)                 | :heavy_minus_sign:                                                                      | N/A                                                                                     |
| `notebook_id`                                                                           | *Optional[str]*                                                                         | :heavy_minus_sign:                                                                      | N/A                                                                                     |
| `num_events_after`                                                                      | *Optional[float]*                                                                       | :heavy_minus_sign:                                                                      | N/A                                                                                     |
| `num_events_before`                                                                     | *Optional[float]*                                                                       | :heavy_minus_sign:                                                                      | N/A                                                                                     |
| `query_with_macros_resolved`                                                            | *Optional[str]*                                                                         | :heavy_minus_sign:                                                                      | N/A                                                                                     |
| `sample_rate`                                                                           | *Optional[float]*                                                                       | :heavy_minus_sign:                                                                      | N/A                                                                                     |
| `saved_query_name`                                                                      | *Optional[str]*                                                                         | :heavy_minus_sign:                                                                      | N/A                                                                                     |
| `search_parameter_declarations`                                                         | List[[models.SearchParameter](../../models/searchparameter.md)]                         | :heavy_minus_sign:                                                                      | N/A                                                                                     |
| `search_parameter_values`                                                               | *Optional[Any]*                                                                         | :heavy_minus_sign:                                                                      | N/A                                                                                     |
| `stages`                                                                                | List[[models.SearchJobStageConfig](../../models/searchjobstageconfig.md)]               | :heavy_minus_sign:                                                                      | N/A                                                                                     |
| `table_config`                                                                          | [Optional[models.TableViewSettings]](../../models/tableviewsettings.md)                 | :heavy_minus_sign:                                                                      | N/A                                                                                     |
| `target_event_time`                                                                     | *Optional[float]*                                                                       | :heavy_minus_sign:                                                                      | N/A                                                                                     |
| `time_completed`                                                                        | *Optional[float]*                                                                       | :heavy_minus_sign:                                                                      | N/A                                                                                     |
| `time_to_first_byte`                                                                    | *Optional[float]*                                                                       | :heavy_minus_sign:                                                                      | N/A                                                                                     |
| `total_bytes_scanned`                                                                   | *Optional[float]*                                                                       | :heavy_minus_sign:                                                                      | N/A                                                                                     |
| `total_event_count`                                                                     | *Optional[float]*                                                                       | :heavy_minus_sign:                                                                      | N/A                                                                                     |
| `type`                                                                                  | [Optional[models.SearchJobType]](../../models/searchjobtype.md)                         | :heavy_minus_sign:                                                                      | N/A                                                                                     |
| `usage_group_id`                                                                        | *Optional[str]*                                                                         | :heavy_minus_sign:                                                                      | N/A                                                                                     |
| `usage_metrics`                                                                         | [Optional[models.SearchAuditMetrics]](../../models/searchauditmetrics.md)               | :heavy_minus_sign:                                                                      | N/A                                                                                     |
| `retries`                                                                               | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)                        | :heavy_minus_sign:                                                                      | Configuration to override the default retry behavior of the client.                     |

### Response

**[models.CreateSearchJobResponse](../../models/createsearchjobresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| errors.Error     | 500              | application/json |
| errors.APIError  | 4XX, 5XX         | \*/\*            |

## get_search_job_by_id

Get SearchJob by ID

### Example Usage

```python
from cribl_sdk_python_fafo import CriblSDKPythonFafo, models
import os


with CriblSDKPythonFafo(
    server_url="https://api.example.com",
    security=models.Security(
        bearer_auth=os.getenv("CRIBLSDKPYTHONFAFO_BEARER_AUTH", ""),
    ),
) as cspf_client:

    res = cspf_client.search.get_search_job_by_id(id="<id>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `id`                                                                | *str*                                                               | :heavy_check_mark:                                                  | Unique ID to GET                                                    |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.GetSearchJobByIDResponse](../../models/getsearchjobbyidresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| errors.Error     | 500              | application/json |
| errors.APIError  | 4XX, 5XX         | \*/\*            |

## update_search_job_by_id

Update SearchJob

### Example Usage

```python
from cribl_sdk_python_fafo import CriblSDKPythonFafo, models
import os


with CriblSDKPythonFafo(
    server_url="https://api.example.com",
    security=models.Security(
        bearer_auth=os.getenv("CRIBLSDKPYTHONFAFO_BEARER_AUTH", ""),
    ),
) as cspf_client:

    res = cspf_client.search.update_search_job_by_id(id_param="<value>", display_username="<value>", group="<value>", id="<id>", query="<value>", status=models.SearchJobStatus.RUNNING, time_created=6068.64, time_started=6166.23, user="Karlee.Blick60")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                                               | Type                                                                                    | Required                                                                                | Description                                                                             |
| --------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------- |
| `id_param`                                                                              | *str*                                                                                   | :heavy_check_mark:                                                                      | Unique ID to PATCH                                                                      |
| `display_username`                                                                      | *str*                                                                                   | :heavy_check_mark:                                                                      | N/A                                                                                     |
| `group`                                                                                 | *str*                                                                                   | :heavy_check_mark:                                                                      | N/A                                                                                     |
| `id`                                                                                    | *str*                                                                                   | :heavy_check_mark:                                                                      | N/A                                                                                     |
| `query`                                                                                 | *str*                                                                                   | :heavy_check_mark:                                                                      | N/A                                                                                     |
| `status`                                                                                | [models.SearchJobStatus](../../models/searchjobstatus.md)                               | :heavy_check_mark:                                                                      | N/A                                                                                     |
| `time_created`                                                                          | *float*                                                                                 | :heavy_check_mark:                                                                      | N/A                                                                                     |
| `time_started`                                                                          | *float*                                                                                 | :heavy_check_mark:                                                                      | N/A                                                                                     |
| `user`                                                                                  | *str*                                                                                   | :heavy_check_mark:                                                                      | N/A                                                                                     |
| `accelerated`                                                                           | *Optional[bool]*                                                                        | :heavy_minus_sign:                                                                      | N/A                                                                                     |
| `alias_of_original_job_id`                                                              | *Optional[str]*                                                                         | :heavy_minus_sign:                                                                      | N/A                                                                                     |
| `compatibility_checks`                                                                  | [Optional[models.CompatibilityChecks]](../../models/compatibilitychecks.md)             | :heavy_minus_sign:                                                                      | N/A                                                                                     |
| `completion_info`                                                                       | *Optional[str]*                                                                         | :heavy_minus_sign:                                                                      | N/A                                                                                     |
| `context`                                                                               | *Optional[str]*                                                                         | :heavy_minus_sign:                                                                      | N/A                                                                                     |
| `correlation_id`                                                                        | *Optional[str]*                                                                         | :heavy_minus_sign:                                                                      | N/A                                                                                     |
| `cpu_metrics`                                                                           | [Optional[models.CPUTimeMetric]](../../models/cputimemetric.md)                         | :heavy_minus_sign:                                                                      | N/A                                                                                     |
| `datatype_overrides`                                                                    | [Optional[models.DatatypeOverrides]](../../models/datatypeoverrides.md)                 | :heavy_minus_sign:                                                                      | N/A                                                                                     |
| `disable_notifications`                                                                 | *Optional[bool]*                                                                        | :heavy_minus_sign:                                                                      | N/A                                                                                     |
| `earliest`                                                                              | [Optional[models.SearchJobEarliest]](../../models/searchjobearliest.md)                 | :heavy_minus_sign:                                                                      | N/A                                                                                     |
| `earliest_epoch`                                                                        | *Optional[float]*                                                                       | :heavy_minus_sign:                                                                      | N/A                                                                                     |
| `error_state_config`                                                                    | [Optional[models.SearchJobErrorStateConfig]](../../models/searchjoberrorstateconfig.md) | :heavy_minus_sign:                                                                      | N/A                                                                                     |
| `is_private`                                                                            | *Optional[bool]*                                                                        | :heavy_minus_sign:                                                                      | N/A                                                                                     |
| `latest`                                                                                | [Optional[models.SearchJobLatest]](../../models/searchjoblatest.md)                     | :heavy_minus_sign:                                                                      | N/A                                                                                     |
| `latest_epoch`                                                                          | *Optional[float]*                                                                       | :heavy_minus_sign:                                                                      | N/A                                                                                     |
| `metadata`                                                                              | [Optional[models.SearchJobMetadata]](../../models/searchjobmetadata.md)                 | :heavy_minus_sign:                                                                      | N/A                                                                                     |
| `notebook_id`                                                                           | *Optional[str]*                                                                         | :heavy_minus_sign:                                                                      | N/A                                                                                     |
| `num_events_after`                                                                      | *Optional[float]*                                                                       | :heavy_minus_sign:                                                                      | N/A                                                                                     |
| `num_events_before`                                                                     | *Optional[float]*                                                                       | :heavy_minus_sign:                                                                      | N/A                                                                                     |
| `query_with_macros_resolved`                                                            | *Optional[str]*                                                                         | :heavy_minus_sign:                                                                      | N/A                                                                                     |
| `sample_rate`                                                                           | *Optional[float]*                                                                       | :heavy_minus_sign:                                                                      | N/A                                                                                     |
| `saved_query_name`                                                                      | *Optional[str]*                                                                         | :heavy_minus_sign:                                                                      | N/A                                                                                     |
| `search_parameter_declarations`                                                         | List[[models.SearchParameter](../../models/searchparameter.md)]                         | :heavy_minus_sign:                                                                      | N/A                                                                                     |
| `search_parameter_values`                                                               | *Optional[Any]*                                                                         | :heavy_minus_sign:                                                                      | N/A                                                                                     |
| `stages`                                                                                | List[[models.SearchJobStageConfig](../../models/searchjobstageconfig.md)]               | :heavy_minus_sign:                                                                      | N/A                                                                                     |
| `table_config`                                                                          | [Optional[models.TableViewSettings]](../../models/tableviewsettings.md)                 | :heavy_minus_sign:                                                                      | N/A                                                                                     |
| `target_event_time`                                                                     | *Optional[float]*                                                                       | :heavy_minus_sign:                                                                      | N/A                                                                                     |
| `time_completed`                                                                        | *Optional[float]*                                                                       | :heavy_minus_sign:                                                                      | N/A                                                                                     |
| `time_to_first_byte`                                                                    | *Optional[float]*                                                                       | :heavy_minus_sign:                                                                      | N/A                                                                                     |
| `total_bytes_scanned`                                                                   | *Optional[float]*                                                                       | :heavy_minus_sign:                                                                      | N/A                                                                                     |
| `total_event_count`                                                                     | *Optional[float]*                                                                       | :heavy_minus_sign:                                                                      | N/A                                                                                     |
| `type`                                                                                  | [Optional[models.SearchJobType]](../../models/searchjobtype.md)                         | :heavy_minus_sign:                                                                      | N/A                                                                                     |
| `usage_group_id`                                                                        | *Optional[str]*                                                                         | :heavy_minus_sign:                                                                      | N/A                                                                                     |
| `usage_metrics`                                                                         | [Optional[models.SearchAuditMetrics]](../../models/searchauditmetrics.md)               | :heavy_minus_sign:                                                                      | N/A                                                                                     |
| `retries`                                                                               | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)                        | :heavy_minus_sign:                                                                      | Configuration to override the default retry behavior of the client.                     |

### Response

**[models.UpdateSearchJobByIDResponse](../../models/updatesearchjobbyidresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| errors.Error     | 500              | application/json |
| errors.APIError  | 4XX, 5XX         | \*/\*            |

## delete_search_job_by_id

Delete SearchJob

### Example Usage

```python
from cribl_sdk_python_fafo import CriblSDKPythonFafo, models
import os


with CriblSDKPythonFafo(
    server_url="https://api.example.com",
    security=models.Security(
        bearer_auth=os.getenv("CRIBLSDKPYTHONFAFO_BEARER_AUTH", ""),
    ),
) as cspf_client:

    res = cspf_client.search.delete_search_job_by_id(id="<id>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `id`                                                                | *str*                                                               | :heavy_check_mark:                                                  | Unique ID to DELETE                                                 |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.DeleteSearchJobByIDResponse](../../models/deletesearchjobbyidresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| errors.Error     | 500              | application/json |
| errors.APIError  | 4XX, 5XX         | \*/\*            |

## create_search_job_dispatch_executors_by_id

internal endpoint, dispatch search *id* to worker nodes filtered by worker node filter using RPC

### Example Usage

```python
from cribl_sdk_python_fafo import CriblSDKPythonFafo, models
import os


with CriblSDKPythonFafo(
    server_url="https://api.example.com",
    security=models.Security(
        bearer_auth=os.getenv("CRIBLSDKPYTHONFAFO_BEARER_AUTH", ""),
    ),
) as cspf_client:

    res = cspf_client.search.create_search_job_dispatch_executors_by_id(id="<id>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `id`                                                                | *str*                                                               | :heavy_check_mark:                                                  | search job id                                                       |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.CreateSearchJobDispatchExecutorsByIDResponse](../../models/createsearchjobdispatchexecutorsbyidresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| errors.Error     | 500              | application/json |
| errors.APIError  | 4XX, 5XX         | \*/\*            |

## get_search_job_settings_by_id

Get search job settings

### Example Usage

```python
from cribl_sdk_python_fafo import CriblSDKPythonFafo, models
import os


with CriblSDKPythonFafo(
    server_url="https://api.example.com",
    security=models.Security(
        bearer_auth=os.getenv("CRIBLSDKPYTHONFAFO_BEARER_AUTH", ""),
    ),
) as cspf_client:

    res = cspf_client.search.get_search_job_settings_by_id(id="<id>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `id`                                                                | *str*                                                               | :heavy_check_mark:                                                  | search job id                                                       |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.SearchJobSettings](../../models/searchjobsettings.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| errors.Error     | 500              | application/json |
| errors.APIError  | 4XX, 5XX         | \*/\*            |

## create_search_job_settings_by_id

Save search job settings

### Example Usage

```python
from cribl_sdk_python_fafo import CriblSDKPythonFafo, models
import os


with CriblSDKPythonFafo(
    server_url="https://api.example.com",
    security=models.Security(
        bearer_auth=os.getenv("CRIBLSDKPYTHONFAFO_BEARER_AUTH", ""),
    ),
) as cspf_client:

    res = cspf_client.search.create_search_job_settings_by_id(id="<id>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `id`                                                                | *str*                                                               | :heavy_check_mark:                                                  | search job id                                                       |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.SearchJobSettings](../../models/searchjobsettings.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| errors.Error     | 500              | application/json |
| errors.APIError  | 4XX, 5XX         | \*/\*            |

## get_search_job_status_by_id

Get job status

### Example Usage

```python
from cribl_sdk_python_fafo import CriblSDKPythonFafo, models
import os


with CriblSDKPythonFafo(
    server_url="https://api.example.com",
    security=models.Security(
        bearer_auth=os.getenv("CRIBLSDKPYTHONFAFO_BEARER_AUTH", ""),
    ),
) as cspf_client:

    res = cspf_client.search.get_search_job_status_by_id(id="<id>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `id`                                                                | *str*                                                               | :heavy_check_mark:                                                  | search job id                                                       |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.StatusResponse](../../models/statusresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| errors.Error     | 500              | application/json |
| errors.APIError  | 4XX, 5XX         | \*/\*            |

## get_search_job_timeline_by_id

Get search timeline

### Example Usage

```python
from cribl_sdk_python_fafo import CriblSDKPythonFafo, models
import os


with CriblSDKPythonFafo(
    server_url="https://api.example.com",
    security=models.Security(
        bearer_auth=os.getenv("CRIBLSDKPYTHONFAFO_BEARER_AUTH", ""),
    ),
) as cspf_client:

    res = cspf_client.search.get_search_job_timeline_by_id(id="<id>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `id`                                                                | *str*                                                               | :heavy_check_mark:                                                  | search job id                                                       |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.SearchTimeline](../../models/searchtimeline.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| errors.Error     | 500              | application/json |
| errors.APIError  | 4XX, 5XX         | \*/\*            |

## get_search_job_field_summaries_by_id

List field summaries

### Example Usage

```python
from cribl_sdk_python_fafo import CriblSDKPythonFafo, models
import os


with CriblSDKPythonFafo(
    server_url="https://api.example.com",
    security=models.Security(
        bearer_auth=os.getenv("CRIBLSDKPYTHONFAFO_BEARER_AUTH", ""),
    ),
) as cspf_client:

    res = cspf_client.search.get_search_job_field_summaries_by_id(id="<id>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `id`                                                                | *str*                                                               | :heavy_check_mark:                                                  | search job id                                                       |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.FieldSummaries](../../models/fieldsummaries.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| errors.Error     | 500              | application/json |
| errors.APIError  | 4XX, 5XX         | \*/\*            |

## get_search_job_logs_by_id

Get search logs

### Example Usage

```python
from cribl_sdk_python_fafo import CriblSDKPythonFafo, models
import os


with CriblSDKPythonFafo(
    server_url="https://api.example.com",
    security=models.Security(
        bearer_auth=os.getenv("CRIBLSDKPYTHONFAFO_BEARER_AUTH", ""),
    ),
) as cspf_client:

    res = cspf_client.search.get_search_job_logs_by_id(id="<id>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `id`                                                                | *str*                                                               | :heavy_check_mark:                                                  | search job id                                                       |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.GetSearchJobLogsByIDResponse](../../models/getsearchjoblogsbyidresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| errors.Error     | 500              | application/json |
| errors.APIError  | 4XX, 5XX         | \*/\*            |

## create_search_event_breaker_preview

Runs an event breaker rule on the specified data

### Example Usage

```python
from cribl_sdk_python_fafo import CriblSDKPythonFafo, models
import os


with CriblSDKPythonFafo(
    server_url="https://api.example.com",
    security=models.Security(
        bearer_auth=os.getenv("CRIBLSDKPYTHONFAFO_BEARER_AUTH", ""),
    ),
) as cspf_client:

    res = cspf_client.search.create_search_event_breaker_preview(input_={
        "dataset": "<value>",
        "type": models.DatatypePreviewInputTypeDataset.DATASET,
    })

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                             | Type                                                                  | Required                                                              | Description                                                           |
| --------------------------------------------------------------------- | --------------------------------------------------------------------- | --------------------------------------------------------------------- | --------------------------------------------------------------------- |
| `input`                                                               | [models.DatatypePreviewInput](../../models/datatypepreviewinput.md)   | :heavy_check_mark:                                                    | N/A                                                                   |
| `event_breaker_rule`                                                  | [Optional[models.EventBreakerRule]](../../models/eventbreakerrule.md) | :heavy_minus_sign:                                                    | N/A                                                                   |
| `retries`                                                             | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)      | :heavy_minus_sign:                                                    | Configuration to override the default retry behavior of the client.   |

### Response

**[models.CreateSearchEventBreakerPreviewResponse](../../models/createsearcheventbreakerpreviewresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| errors.Error     | 500              | application/json |
| errors.APIError  | 4XX, 5XX         | \*/\*            |

## get_search_docs

Get Search documentation

### Example Usage

```python
from cribl_sdk_python_fafo import CriblSDKPythonFafo, models
import os


with CriblSDKPythonFafo(
    server_url="https://api.example.com",
    security=models.Security(
        bearer_auth=os.getenv("CRIBLSDKPYTHONFAFO_BEARER_AUTH", ""),
    ),
) as cspf_client:

    res = cspf_client.search.get_search_docs()

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[str](../../models/.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| errors.Error     | 500              | application/json |
| errors.APIError  | 4XX, 5XX         | \*/\*            |

## get_search_healthcheck

Get health check metric for search

### Example Usage

```python
from cribl_sdk_python_fafo import CriblSDKPythonFafo, models
import os


with CriblSDKPythonFafo(
    server_url="https://api.example.com",
    security=models.Security(
        bearer_auth=os.getenv("CRIBLSDKPYTHONFAFO_BEARER_AUTH", ""),
    ),
) as cspf_client:

    res = cspf_client.search.get_search_healthcheck()

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.GetSearchHealthcheckResponse](../../models/getsearchhealthcheckresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| errors.Error     | 500              | application/json |
| errors.APIError  | 4XX, 5XX         | \*/\*            |

## get_search_jobs_metrics_by_id

Get search job metrics

### Example Usage

```python
from cribl_sdk_python_fafo import CriblSDKPythonFafo, models
import os


with CriblSDKPythonFafo(
    server_url="https://api.example.com",
    security=models.Security(
        bearer_auth=os.getenv("CRIBLSDKPYTHONFAFO_BEARER_AUTH", ""),
    ),
) as cspf_client:

    res = cspf_client.search.get_search_jobs_metrics_by_id(id="<id>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `id`                                                                | *str*                                                               | :heavy_check_mark:                                                  | search job id                                                       |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[str](../../models/.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| errors.Error     | 500              | application/json |
| errors.APIError  | 4XX, 5XX         | \*/\*            |

## get_search_job_metrics

List metrics for all search jobs

### Example Usage

```python
from cribl_sdk_python_fafo import CriblSDKPythonFafo, models
import os


with CriblSDKPythonFafo(
    server_url="https://api.example.com",
    security=models.Security(
        bearer_auth=os.getenv("CRIBLSDKPYTHONFAFO_BEARER_AUTH", ""),
    ),
) as cspf_client:

    res = cspf_client.search.get_search_job_metrics()

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[str](../../models/.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| errors.Error     | 500              | application/json |
| errors.APIError  | 4XX, 5XX         | \*/\*            |

## create_search_preview

Applies a query snippet on a set of input events for preview

### Example Usage

```python
from cribl_sdk_python_fafo import CriblSDKPythonFafo, models
import os


with CriblSDKPythonFafo(
    server_url="https://api.example.com",
    security=models.Security(
        bearer_auth=os.getenv("CRIBLSDKPYTHONFAFO_BEARER_AUTH", ""),
    ),
) as cspf_client:

    res = cspf_client.search.create_search_preview(events=[], query="<value>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `events`                                                            | List[*Any*]                                                         | :heavy_check_mark:                                                  | N/A                                                                 |
| `query`                                                             | *str*                                                               | :heavy_check_mark:                                                  | N/A                                                                 |
| `options`                                                           | [Optional[models.PreviewOptions]](../../models/previewoptions.md)   | :heavy_minus_sign:                                                  | N/A                                                                 |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.CreateSearchPreviewResponse](../../models/createsearchpreviewresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| errors.Error     | 500              | application/json |
| errors.APIError  | 4XX, 5XX         | \*/\*            |

## get_search_jobs_diag_by_id

Get full search job data

### Example Usage

```python
from cribl_sdk_python_fafo import CriblSDKPythonFafo, models
import os


with CriblSDKPythonFafo(
    server_url="https://api.example.com",
    security=models.Security(
        bearer_auth=os.getenv("CRIBLSDKPYTHONFAFO_BEARER_AUTH", ""),
    ),
) as cspf_client:

    res = cspf_client.search.get_search_jobs_diag_by_id(id="<id>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `id`                                                                | *str*                                                               | :heavy_check_mark:                                                  | search job id                                                       |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[str](../../models/.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| errors.Error     | 500              | application/json |
| errors.APIError  | 4XX, 5XX         | \*/\*            |

## get_search_jobs_logs_by_id_and_filename

Get the contents of a log file

### Example Usage

```python
from cribl_sdk_python_fafo import CriblSDKPythonFafo, models
import os


with CriblSDKPythonFafo(
    server_url="https://api.example.com",
    security=models.Security(
        bearer_auth=os.getenv("CRIBLSDKPYTHONFAFO_BEARER_AUTH", ""),
    ),
) as cspf_client:

    res = cspf_client.search.get_search_jobs_logs_by_id_and_filename(id="<id>", filename="example.file")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `id`                                                                | *str*                                                               | :heavy_check_mark:                                                  | search job id                                                       |
| `filename`                                                          | *str*                                                               | :heavy_check_mark:                                                  | name of the log file to get                                         |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[str](../../models/.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| errors.Error     | 500              | application/json |
| errors.APIError  | 4XX, 5XX         | \*/\*            |

## get_search_jobs_stages_results_by_id_and_stage_id

List search results for a given stage. Note that this cannot be the root stage!

### Example Usage

```python
from cribl_sdk_python_fafo import CriblSDKPythonFafo, models
import os


with CriblSDKPythonFafo(
    server_url="https://api.example.com",
    security=models.Security(
        bearer_auth=os.getenv("CRIBLSDKPYTHONFAFO_BEARER_AUTH", ""),
    ),
) as cspf_client:

    res = cspf_client.search.get_search_jobs_stages_results_by_id_and_stage_id(id="<id>", stage_id="<id>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `id`                                                                | *str*                                                               | :heavy_check_mark:                                                  | search job ID                                                       |
| `stage_id`                                                          | *str*                                                               | :heavy_check_mark:                                                  | id of the search job stage                                          |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[str](../../models/.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| errors.Error     | 500              | application/json |
| errors.APIError  | 4XX, 5XX         | \*/\*            |

## get_search_jobs_results_by_id

List search results, when lower/upper bound is provided, offset is relative to the time range.

### Example Usage

```python
from cribl_sdk_python_fafo import CriblSDKPythonFafo, models
import os


with CriblSDKPythonFafo(
    server_url="https://api.example.com",
    security=models.Security(
        bearer_auth=os.getenv("CRIBLSDKPYTHONFAFO_BEARER_AUTH", ""),
    ),
) as cspf_client:

    res = cspf_client.search.get_search_jobs_results_by_id(id="<id>")

    with res as jsonl_stream:
        for event in jsonl_stream:
            # handle event
            print(event, flush=True)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `id`                                                                | *str*                                                               | :heavy_check_mark:                                                  | search job id                                                       |
| `limit`                                                             | *Optional[float]*                                                   | :heavy_minus_sign:                                                  | maximum number of events returned                                   |
| `offset`                                                            | *Optional[float]*                                                   | :heavy_minus_sign:                                                  | starting offset of the events                                       |
| `lower_bound`                                                       | *Optional[float]*                                                   | :heavy_minus_sign:                                                  | lower bound of the time range, inclusive                            |
| `upper_bound`                                                       | *Optional[float]*                                                   | :heavy_minus_sign:                                                  | upper bound of the time range, exclusive                            |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[Union[jsonl.JsonLStream[models.GetSearchJobsResultsByIDResponseBody], jsonl.JsonLStreamAsync[models.GetSearchJobsResultsByIDResponseBody]]](../../models/.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| errors.Error     | 500              | application/json |
| errors.APIError  | 4XX, 5XX         | \*/\*            |

## get_search_jobs_results_poll_by_id

List search results

### Example Usage

```python
from cribl_sdk_python_fafo import CriblSDKPythonFafo, models
import os


with CriblSDKPythonFafo(
    server_url="https://api.example.com",
    security=models.Security(
        bearer_auth=os.getenv("CRIBLSDKPYTHONFAFO_BEARER_AUTH", ""),
    ),
) as cspf_client:

    res = cspf_client.search.get_search_jobs_results_poll_by_id(id="<id>")

    with res as jsonl_stream:
        for event in jsonl_stream:
            # handle event
            print(event, flush=True)

```

### Parameters

| Parameter                                                                                                   | Type                                                                                                        | Required                                                                                                    | Description                                                                                                 |
| ----------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------- |
| `id`                                                                                                        | *str*                                                                                                       | :heavy_check_mark:                                                                                          | search job id                                                                                               |
| `limit`                                                                                                     | *Optional[float]*                                                                                           | :heavy_minus_sign:                                                                                          | maximum number of events returned                                                                           |
| `offset`                                                                                                    | *Optional[float]*                                                                                           | :heavy_minus_sign:                                                                                          | starting offset of the events                                                                               |
| `lower_bound`                                                                                               | *Optional[float]*                                                                                           | :heavy_minus_sign:                                                                                          | lower bound of the time range, inclusive                                                                    |
| `upper_bound`                                                                                               | *Optional[float]*                                                                                           | :heavy_minus_sign:                                                                                          | upper bound of the time range, exclusive                                                                    |
| `last_job_status`                                                                                           | *Optional[str]*                                                                                             | :heavy_minus_sign:                                                                                          | last known status of the Search Job. Used to return immediatelyupon status change if the status was queued. |
| `retries`                                                                                                   | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)                                            | :heavy_minus_sign:                                                                                          | Configuration to override the default retry behavior of the client.                                         |

### Response

**[Union[jsonl.JsonLStream[models.SearchJobResults], jsonl.JsonLStreamAsync[models.SearchJobResults]]](../../models/.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| errors.Error     | 500              | application/json |
| errors.APIError  | 4XX, 5XX         | \*/\*            |