# Projects
(*projects*)

## Overview

Actions related to Projects

### Available Operations

* [get_system_projects_subscriptions_by_group_id_by_and_project_id](#get_system_projects_subscriptions_by_group_id_by_and_project_id) - Get the Subscriptions associated with the Project
* [get_system_projects_version_count_by_group_id_and_project_id](#get_system_projects_version_count_by_group_id_and_project_id) - Get the count of files of changed
* [get_system_projects_version_diff_by_group_id_and_project_id](#get_system_projects_version_diff_by_group_id_and_project_id) - Get the textual diff for given commit
* [get_system_projects_version_files_by_group_id_and_project_id](#get_system_projects_version_files_by_group_id_and_project_id) - Get the files changed
* [create_system_projects_version_commit_by_group_id_and_project_id](#create_system_projects_version_commit_by_group_id_and_project_id) - Commit project changes
* [create_system_projects_subscriptions_capture_by_group_id_and_subscription_id](#create_system_projects_subscriptions_capture_by_group_id_and_subscription_id) - Capture live incoming data from a particular Project and Subscription at the Subscription
* [create_system_projects_capture_by_group_id_and_project_id](#create_system_projects_capture_by_group_id_and_project_id) - Capture live incoming data from a particular Project and Subscription at the Destination
* [create_system_projects_preview_by_group_id_and_project_id](#create_system_projects_preview_by_group_id_and_project_id) - Sends sample events through a Pipeline  for specified Project and returns the results
* [get_system_projects_pipelines_by_group_id_and_project_id](#get_system_projects_pipelines_by_group_id_and_project_id) - Get A list of Pipeline objects for specified Project
* [create_system_projects_pipelines_by_group_id_and_project_id](#create_system_projects_pipelines_by_group_id_and_project_id) - Create Pipeline
* [get_system_projects_pipelines_by_group_id_and_project_id_and_pipeline_id](#get_system_projects_pipelines_by_group_id_and_project_id_and_pipeline_id) - Get Pipeline by ID in specified Project
* [update_system_projects_pipelines_by_group_id_and_project_id_and_pipeline_id](#update_system_projects_pipelines_by_group_id_and_project_id_and_pipeline_id) - Update Pipeline in specified Project
* [delete_system_projects_pipelines_by_group_id_and_project_id_and_pipeline_id](#delete_system_projects_pipelines_by_group_id_and_project_id_and_pipeline_id) - Delete Pipeline in specified Project
* [create_system_projects_version_commit_by_project_id](#create_system_projects_version_commit_by_project_id) - Commit project changes.
* [get_system_projects_version_count_by_project_id](#get_system_projects_version_count_by_project_id) - get the count of files of changed
* [get_system_projects_version_diff_by_project_id](#get_system_projects_version_diff_by_project_id) - get the textual diff for given commit
* [get_system_projects_version_files_by_project_id](#get_system_projects_version_files_by_project_id) - get the files changed
* [create_system_projects_version_revert_by_project_id](#create_system_projects_version_revert_by_project_id) - Revert project changes.
* [get_system_projects_version_show_by_project_id](#get_system_projects_version_show_by_project_id) - Show project changes.
* [list_project](#list_project) - Get a list of Project objects
* [create_project](#create_project) - Create Project
* [get_project_by_id](#get_project_by_id) - Get Project by ID
* [update_project_by_id](#update_project_by_id) - Update Project
* [delete_project_by_id](#delete_project_by_id) - Delete Project
* [get_project_acl_by_id](#get_project_acl_by_id) - Get Project ACL
* [create_project_acl_apply_by_id](#create_project_acl_apply_by_id) - Modify Project ACL
* [get_project_acl_teams_by_id](#get_project_acl_teams_by_id) - Get Project Teams
* [create_project_acl_teams_apply_by_id](#create_project_acl_teams_apply_by_id) - Modify Project Teams ACL
* [get_project_destinations_by_project_id](#get_project_destinations_by_project_id) - Lists destinations associated with this project.
* [get_subscription_by_project_id](#get_subscription_by_project_id) - Get the subscriptions associated with the project

## get_system_projects_subscriptions_by_group_id_by_and_project_id

Get the Subscriptions associated with the Project

### Example Usage

```python
from cribl import Cribl
import os


with Cribl(
    bearer_auth=os.getenv("CRIBL_BEARER_AUTH", ""),
) as c_client:

    res = c_client.projects.get_system_projects_subscriptions_by_group_id_by_and_project_id(group_id="<id>", project_id="<id>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `group_id`                                                          | *str*                                                               | :heavy_check_mark:                                                  | Group Id                                                            |
| `project_id`                                                        | *str*                                                               | :heavy_check_mark:                                                  | Project Id                                                          |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.GetSystemProjectsSubscriptionsByGroupIDByAndProjectIDResponseBody](../../models/getsystemprojectssubscriptionsbygroupidbyandprojectidresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |

## get_system_projects_version_count_by_group_id_and_project_id

Get the count of files of changed

### Example Usage

```python
from cribl import Cribl
import os


with Cribl(
    bearer_auth=os.getenv("CRIBL_BEARER_AUTH", ""),
) as c_client:

    res = c_client.projects.get_system_projects_version_count_by_group_id_and_project_id(group_id="<id>", project_id="<id>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `group_id`                                                          | *str*                                                               | :heavy_check_mark:                                                  | Group Id                                                            |
| `project_id`                                                        | *str*                                                               | :heavy_check_mark:                                                  | Project Id                                                          |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.GetSystemProjectsVersionCountByGroupIDAndProjectIDResponseBody](../../models/getsystemprojectsversioncountbygroupidandprojectidresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |

## get_system_projects_version_diff_by_group_id_and_project_id

Get the textual diff for given commit

### Example Usage

```python
from cribl import Cribl
import os


with Cribl(
    bearer_auth=os.getenv("CRIBL_BEARER_AUTH", ""),
) as c_client:

    res = c_client.projects.get_system_projects_version_diff_by_group_id_and_project_id(group_id="<id>", project_id="<id>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `group_id`                                                          | *str*                                                               | :heavy_check_mark:                                                  | Group Id                                                            |
| `project_id`                                                        | *str*                                                               | :heavy_check_mark:                                                  | Project Id                                                          |
| `commit`                                                            | *Optional[str]*                                                     | :heavy_minus_sign:                                                  | N/A                                                                 |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.GetSystemProjectsVersionDiffByGroupIDAndProjectIDResponseBody](../../models/getsystemprojectsversiondiffbygroupidandprojectidresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |

## get_system_projects_version_files_by_group_id_and_project_id

Get the files changed

### Example Usage

```python
from cribl import Cribl
import os


with Cribl(
    bearer_auth=os.getenv("CRIBL_BEARER_AUTH", ""),
) as c_client:

    res = c_client.projects.get_system_projects_version_files_by_group_id_and_project_id(group_id="<id>", project_id="<id>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `group_id`                                                          | *str*                                                               | :heavy_check_mark:                                                  | Group Id                                                            |
| `project_id`                                                        | *str*                                                               | :heavy_check_mark:                                                  | Project Id                                                          |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.GetSystemProjectsVersionFilesByGroupIDAndProjectIDResponseBody](../../models/getsystemprojectsversionfilesbygroupidandprojectidresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |

## create_system_projects_version_commit_by_group_id_and_project_id

Commit project changes

### Example Usage

```python
from cribl import Cribl
import os


with Cribl(
    bearer_auth=os.getenv("CRIBL_BEARER_AUTH", ""),
) as c_client:

    res = c_client.projects.create_system_projects_version_commit_by_group_id_and_project_id(group_id="<id>", project_id="<id>", message="<value>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `group_id`                                                          | *str*                                                               | :heavy_check_mark:                                                  | Group Id                                                            |
| `project_id`                                                        | *str*                                                               | :heavy_check_mark:                                                  | Project Id                                                          |
| `message`                                                           | *str*                                                               | :heavy_check_mark:                                                  | N/A                                                                 |
| `effective`                                                         | *Optional[bool]*                                                    | :heavy_minus_sign:                                                  | N/A                                                                 |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.CreateSystemProjectsVersionCommitByGroupIDAndProjectIDResponseBody](../../models/createsystemprojectsversioncommitbygroupidandprojectidresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |

## create_system_projects_subscriptions_capture_by_group_id_and_subscription_id

Capture live incoming data from a particular Project and Subscription at the Subscription

### Example Usage

```python
from cribl import Cribl
import os


with Cribl(
    bearer_auth=os.getenv("CRIBL_BEARER_AUTH", ""),
) as c_client:

    res = c_client.projects.create_system_projects_subscriptions_capture_by_group_id_and_subscription_id(group_id="<id>", project_id="<id>", subscription_id="<id>", duration=4923.8, filter_="<value>", level=3160.52, max_events=7440.79)

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `group_id`                                                          | *str*                                                               | :heavy_check_mark:                                                  | Group Id                                                            |
| `project_id`                                                        | *str*                                                               | :heavy_check_mark:                                                  | Project Id                                                          |
| `subscription_id`                                                   | *str*                                                               | :heavy_check_mark:                                                  | Subscription Id                                                     |
| `duration`                                                          | *float*                                                             | :heavy_check_mark:                                                  | N/A                                                                 |
| `filter_`                                                           | *str*                                                               | :heavy_check_mark:                                                  | N/A                                                                 |
| `level`                                                             | *float*                                                             | :heavy_check_mark:                                                  | N/A                                                                 |
| `max_events`                                                        | *float*                                                             | :heavy_check_mark:                                                  | N/A                                                                 |
| `step_duration`                                                     | *Optional[float]*                                                   | :heavy_minus_sign:                                                  | N/A                                                                 |
| `worker_id`                                                         | *Optional[str]*                                                     | :heavy_minus_sign:                                                  | N/A                                                                 |
| `worker_threshold`                                                  | *Optional[float]*                                                   | :heavy_minus_sign:                                                  | N/A                                                                 |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.CreateSystemProjectsSubscriptionsCaptureByGroupIDAndSubscriptionIDResponseBody](../../models/createsystemprojectssubscriptionscapturebygroupidandsubscriptionidresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |

## create_system_projects_capture_by_group_id_and_project_id

Capture live incoming data from a particular Project and Subscription at the Destination

### Example Usage

```python
from cribl import Cribl
import os


with Cribl(
    bearer_auth=os.getenv("CRIBL_BEARER_AUTH", ""),
) as c_client:

    res = c_client.projects.create_system_projects_capture_by_group_id_and_project_id(group_id="<id>", project_id="<id>", duration=5838.43, filter_="<value>", level=9104.01, max_events=8081.96)

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `group_id`                                                          | *str*                                                               | :heavy_check_mark:                                                  | Group Id                                                            |
| `project_id`                                                        | *str*                                                               | :heavy_check_mark:                                                  | Project Id                                                          |
| `duration`                                                          | *float*                                                             | :heavy_check_mark:                                                  | N/A                                                                 |
| `filter_`                                                           | *str*                                                               | :heavy_check_mark:                                                  | N/A                                                                 |
| `level`                                                             | *float*                                                             | :heavy_check_mark:                                                  | N/A                                                                 |
| `max_events`                                                        | *float*                                                             | :heavy_check_mark:                                                  | N/A                                                                 |
| `step_duration`                                                     | *Optional[float]*                                                   | :heavy_minus_sign:                                                  | N/A                                                                 |
| `worker_id`                                                         | *Optional[str]*                                                     | :heavy_minus_sign:                                                  | N/A                                                                 |
| `worker_threshold`                                                  | *Optional[float]*                                                   | :heavy_minus_sign:                                                  | N/A                                                                 |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.CreateSystemProjectsCaptureByGroupIDAndProjectIDResponseBody](../../models/createsystemprojectscapturebygroupidandprojectidresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |

## create_system_projects_preview_by_group_id_and_project_id

Sends sample events through a Pipeline  for specified Project and returns the results

### Example Usage

```python
import cribl
from cribl import Cribl
import os


with Cribl(
    bearer_auth=os.getenv("CRIBL_BEARER_AUTH", ""),
) as c_client:

    res = c_client.projects.create_system_projects_preview_by_group_id_and_project_id(group_id="<id>", project_id="<id>", mode=cribl.Mode.ROUTE_AND_SEND, pipeline_id="<id>", sample_id="<id>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `group_id`                                                          | *str*                                                               | :heavy_check_mark:                                                  | Group Id                                                            |
| `project_id`                                                        | *str*                                                               | :heavy_check_mark:                                                  | Project Id                                                          |
| `mode`                                                              | [models.Mode](../../models/mode.md)                                 | :heavy_check_mark:                                                  | N/A                                                                 |
| `pipeline_id`                                                       | *str*                                                               | :heavy_check_mark:                                                  | N/A                                                                 |
| `sample_id`                                                         | *str*                                                               | :heavy_check_mark:                                                  | N/A                                                                 |
| `cpu_profile`                                                       | *Optional[bool]*                                                    | :heavy_minus_sign:                                                  | N/A                                                                 |
| `dropped`                                                           | *Optional[bool]*                                                    | :heavy_minus_sign:                                                  | N/A                                                                 |
| `enhance_metrics_output`                                            | *Optional[bool]*                                                    | :heavy_minus_sign:                                                  | N/A                                                                 |
| `events`                                                            | List[Dict[str, *Any*]]                                              | :heavy_minus_sign:                                                  | N/A                                                                 |
| `input_id`                                                          | *Optional[str]*                                                     | :heavy_minus_sign:                                                  | N/A                                                                 |
| `level`                                                             | *Optional[float]*                                                   | :heavy_minus_sign:                                                  | N/A                                                                 |
| `memory`                                                            | *Optional[float]*                                                   | :heavy_minus_sign:                                                  | N/A                                                                 |
| `sample_pipeline_id`                                                | *Optional[str]*                                                     | :heavy_minus_sign:                                                  | N/A                                                                 |
| `timeout`                                                           | *Optional[float]*                                                   | :heavy_minus_sign:                                                  | N/A                                                                 |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.CreateSystemProjectsPreviewByGroupIDAndProjectIDResponseBody](../../models/createsystemprojectspreviewbygroupidandprojectidresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |

## get_system_projects_pipelines_by_group_id_and_project_id

Get A list of Pipeline objects for specified Project

### Example Usage

```python
from cribl import Cribl
import os


with Cribl(
    bearer_auth=os.getenv("CRIBL_BEARER_AUTH", ""),
) as c_client:

    res = c_client.projects.get_system_projects_pipelines_by_group_id_and_project_id(group_id="<id>", project_id="<id>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `group_id`                                                          | *str*                                                               | :heavy_check_mark:                                                  | Group Id                                                            |
| `project_id`                                                        | *str*                                                               | :heavy_check_mark:                                                  | Project Id                                                          |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.GetSystemProjectsPipelinesByGroupIDAndProjectIDResponseBody](../../models/getsystemprojectspipelinesbygroupidandprojectidresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |

## create_system_projects_pipelines_by_group_id_and_project_id

Create Pipeline

### Example Usage

```python
from cribl import Cribl
import os


with Cribl(
    bearer_auth=os.getenv("CRIBL_BEARER_AUTH", ""),
) as c_client:

    res = c_client.projects.create_system_projects_pipelines_by_group_id_and_project_id(group_id="<id>", project_id="<id>", id="<id>", conf={})

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `group_id`                                                          | *str*                                                               | :heavy_check_mark:                                                  | Group Id                                                            |
| `project_id`                                                        | *str*                                                               | :heavy_check_mark:                                                  | Project Id                                                          |
| `id`                                                                | *str*                                                               | :heavy_check_mark:                                                  | N/A                                                                 |
| `conf`                                                              | [models.Conf](../../models/conf.md)                                 | :heavy_check_mark:                                                  | N/A                                                                 |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.CreateSystemProjectsPipelinesByGroupIDAndProjectIDResponseBody](../../models/createsystemprojectspipelinesbygroupidandprojectidresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |

## get_system_projects_pipelines_by_group_id_and_project_id_and_pipeline_id

Get Pipeline by ID in specified Project

### Example Usage

```python
from cribl import Cribl
import os


with Cribl(
    bearer_auth=os.getenv("CRIBL_BEARER_AUTH", ""),
) as c_client:

    res = c_client.projects.get_system_projects_pipelines_by_group_id_and_project_id_and_pipeline_id(group_id="<id>", project_id="<id>", pipeline_id="<id>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `group_id`                                                          | *str*                                                               | :heavy_check_mark:                                                  | Group Id                                                            |
| `project_id`                                                        | *str*                                                               | :heavy_check_mark:                                                  | Project Id                                                          |
| `pipeline_id`                                                       | *str*                                                               | :heavy_check_mark:                                                  | Pipeline Id                                                         |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.GetSystemProjectsPipelinesByGroupIDAndProjectIDAndPipelineIDResponseBody](../../models/getsystemprojectspipelinesbygroupidandprojectidandpipelineidresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |

## update_system_projects_pipelines_by_group_id_and_project_id_and_pipeline_id

Update Pipeline in specified Project

### Example Usage

```python
from cribl import Cribl
import os


with Cribl(
    bearer_auth=os.getenv("CRIBL_BEARER_AUTH", ""),
) as c_client:

    res = c_client.projects.update_system_projects_pipelines_by_group_id_and_project_id_and_pipeline_id(group_id="<id>", project_id="<id>", pipeline_id="<id>", id="<id>", conf={})

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `group_id`                                                          | *str*                                                               | :heavy_check_mark:                                                  | Group Id                                                            |
| `project_id`                                                        | *str*                                                               | :heavy_check_mark:                                                  | Project Id                                                          |
| `pipeline_id`                                                       | *str*                                                               | :heavy_check_mark:                                                  | Pipeline iD                                                         |
| `id`                                                                | *str*                                                               | :heavy_check_mark:                                                  | N/A                                                                 |
| `conf`                                                              | [models.Conf](../../models/conf.md)                                 | :heavy_check_mark:                                                  | N/A                                                                 |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.UpdateSystemProjectsPipelinesByGroupIDAndProjectIDAndPipelineIDResponseBody](../../models/updatesystemprojectspipelinesbygroupidandprojectidandpipelineidresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |

## delete_system_projects_pipelines_by_group_id_and_project_id_and_pipeline_id

Delete Pipeline in specified Project

### Example Usage

```python
from cribl import Cribl
import os


with Cribl(
    bearer_auth=os.getenv("CRIBL_BEARER_AUTH", ""),
) as c_client:

    res = c_client.projects.delete_system_projects_pipelines_by_group_id_and_project_id_and_pipeline_id(group_id="<id>", project_id="<id>", pipeline_id="<id>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `group_id`                                                          | *str*                                                               | :heavy_check_mark:                                                  | Group Id                                                            |
| `project_id`                                                        | *str*                                                               | :heavy_check_mark:                                                  | Project Id                                                          |
| `pipeline_id`                                                       | *str*                                                               | :heavy_check_mark:                                                  | Pipeline Id                                                         |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.DeleteSystemProjectsPipelinesByGroupIDAndProjectIDAndPipelineIDResponseBody](../../models/deletesystemprojectspipelinesbygroupidandprojectidandpipelineidresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |

## create_system_projects_version_commit_by_project_id

Commit project changes.

### Example Usage

```python
from cribl import Cribl
import os


with Cribl(
    bearer_auth=os.getenv("CRIBL_BEARER_AUTH", ""),
) as c_client:

    res = c_client.projects.create_system_projects_version_commit_by_project_id(project_id="<id>", message="<value>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `project_id`                                                        | *str*                                                               | :heavy_check_mark:                                                  | Project Id                                                          |
| `message`                                                           | *str*                                                               | :heavy_check_mark:                                                  | N/A                                                                 |
| `effective`                                                         | *Optional[bool]*                                                    | :heavy_minus_sign:                                                  | N/A                                                                 |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.CreateSystemProjectsVersionCommitByProjectIDResponseBody](../../models/createsystemprojectsversioncommitbyprojectidresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |

## get_system_projects_version_count_by_project_id

get the count of files of changed

### Example Usage

```python
from cribl import Cribl
import os


with Cribl(
    bearer_auth=os.getenv("CRIBL_BEARER_AUTH", ""),
) as c_client:

    res = c_client.projects.get_system_projects_version_count_by_project_id(project_id="<id>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `project_id`                                                        | *str*                                                               | :heavy_check_mark:                                                  | Project ID                                                          |
| `id`                                                                | *Optional[str]*                                                     | :heavy_minus_sign:                                                  | Commit ID                                                           |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.GetSystemProjectsVersionCountByProjectIDResponseBody](../../models/getsystemprojectsversioncountbyprojectidresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |

## get_system_projects_version_diff_by_project_id

get the textual diff for given commit

### Example Usage

```python
from cribl import Cribl
import os


with Cribl(
    bearer_auth=os.getenv("CRIBL_BEARER_AUTH", ""),
) as c_client:

    res = c_client.projects.get_system_projects_version_diff_by_project_id(project_id="<id>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `project_id`                                                        | *str*                                                               | :heavy_check_mark:                                                  | Project Id                                                          |
| `commit`                                                            | *Optional[str]*                                                     | :heavy_minus_sign:                                                  | Commit hash (default is HEAD)                                       |
| `filename`                                                          | *Optional[str]*                                                     | :heavy_minus_sign:                                                  | Filename                                                            |
| `diff_line_limit`                                                   | *Optional[float]*                                                   | :heavy_minus_sign:                                                  | Limit maximum lines in the diff                                     |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.GetSystemProjectsVersionDiffByProjectIDResponseBody](../../models/getsystemprojectsversiondiffbyprojectidresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |

## get_system_projects_version_files_by_project_id

get the files changed

### Example Usage

```python
from cribl import Cribl
import os


with Cribl(
    bearer_auth=os.getenv("CRIBL_BEARER_AUTH", ""),
) as c_client:

    res = c_client.projects.get_system_projects_version_files_by_project_id(project_id="<id>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `project_id`                                                        | *str*                                                               | :heavy_check_mark:                                                  | Project ID                                                          |
| `id`                                                                | *Optional[str]*                                                     | :heavy_minus_sign:                                                  | Commit ID                                                           |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.GetSystemProjectsVersionFilesByProjectIDResponseBody](../../models/getsystemprojectsversionfilesbyprojectidresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |

## create_system_projects_version_revert_by_project_id

Revert project changes.

### Example Usage

```python
from cribl import Cribl
import os


with Cribl(
    bearer_auth=os.getenv("CRIBL_BEARER_AUTH", ""),
) as c_client:

    res = c_client.projects.create_system_projects_version_revert_by_project_id(project_id="<id>", message="<value>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `project_id`                                                        | *str*                                                               | :heavy_check_mark:                                                  | Project Id                                                          |
| `message`                                                           | *str*                                                               | :heavy_check_mark:                                                  | N/A                                                                 |
| `effective`                                                         | *Optional[bool]*                                                    | :heavy_minus_sign:                                                  | N/A                                                                 |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.CreateSystemProjectsVersionRevertByProjectIDResponseBody](../../models/createsystemprojectsversionrevertbyprojectidresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |

## get_system_projects_version_show_by_project_id

Show project changes.

### Example Usage

```python
from cribl import Cribl
import os


with Cribl(
    bearer_auth=os.getenv("CRIBL_BEARER_AUTH", ""),
) as c_client:

    res = c_client.projects.get_system_projects_version_show_by_project_id(project_id="<id>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `project_id`                                                        | *str*                                                               | :heavy_check_mark:                                                  | Project Id                                                          |
| `id`                                                                | *Optional[str]*                                                     | :heavy_minus_sign:                                                  | Commit ID                                                           |
| `filename`                                                          | *Optional[str]*                                                     | :heavy_minus_sign:                                                  | Filename                                                            |
| `diff_line_limit`                                                   | *Optional[float]*                                                   | :heavy_minus_sign:                                                  | Limit maximum lines in the diff                                     |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.GetSystemProjectsVersionShowByProjectIDResponseBody](../../models/getsystemprojectsversionshowbyprojectidresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |

## list_project

Get a list of Project objects

### Example Usage

```python
from cribl import Cribl
import os


with Cribl(
    bearer_auth=os.getenv("CRIBL_BEARER_AUTH", ""),
) as c_client:

    res = c_client.projects.list_project()

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.ListProjectResponseBody](../../models/listprojectresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |

## create_project

Create Project

### Example Usage

```python
from cribl import Cribl
import os


with Cribl(
    bearer_auth=os.getenv("CRIBL_BEARER_AUTH", ""),
) as c_client:

    res = c_client.projects.create_project(destinations=[
        "<value>",
        "<value>",
    ], id="<id>", subscriptions=[
        "<value>",
        "<value>",
        "<value>",
    ])

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `destinations`                                                      | List[*str*]                                                         | :heavy_check_mark:                                                  | N/A                                                                 |
| `id`                                                                | *str*                                                               | :heavy_check_mark:                                                  | N/A                                                                 |
| `subscriptions`                                                     | List[*str*]                                                         | :heavy_check_mark:                                                  | N/A                                                                 |
| `consumers`                                                         | [Optional[models.Consumers]](../../models/consumers.md)             | :heavy_minus_sign:                                                  | N/A                                                                 |
| `description`                                                       | *Optional[str]*                                                     | :heavy_minus_sign:                                                  | N/A                                                                 |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.CreateProjectResponseBody](../../models/createprojectresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |

## get_project_by_id

Get Project by ID

### Example Usage

```python
from cribl import Cribl
import os


with Cribl(
    bearer_auth=os.getenv("CRIBL_BEARER_AUTH", ""),
) as c_client:

    res = c_client.projects.get_project_by_id(id="<id>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `id`                                                                | *str*                                                               | :heavy_check_mark:                                                  | Unique ID to GET                                                    |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.GetProjectByIDResponseBody](../../models/getprojectbyidresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |

## update_project_by_id

Update Project

### Example Usage

```python
from cribl import Cribl
import os


with Cribl(
    bearer_auth=os.getenv("CRIBL_BEARER_AUTH", ""),
) as c_client:

    res = c_client.projects.update_project_by_id(id_param="<value>", destinations=[

    ], id="<id>", subscriptions=[
        "<value>",
        "<value>",
    ])

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `id_param`                                                          | *str*                                                               | :heavy_check_mark:                                                  | Unique ID to PATCH                                                  |
| `destinations`                                                      | List[*str*]                                                         | :heavy_check_mark:                                                  | N/A                                                                 |
| `id`                                                                | *str*                                                               | :heavy_check_mark:                                                  | N/A                                                                 |
| `subscriptions`                                                     | List[*str*]                                                         | :heavy_check_mark:                                                  | N/A                                                                 |
| `consumers`                                                         | [Optional[models.Consumers]](../../models/consumers.md)             | :heavy_minus_sign:                                                  | N/A                                                                 |
| `description`                                                       | *Optional[str]*                                                     | :heavy_minus_sign:                                                  | N/A                                                                 |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.UpdateProjectByIDResponseBody](../../models/updateprojectbyidresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |

## delete_project_by_id

Delete Project

### Example Usage

```python
from cribl import Cribl
import os


with Cribl(
    bearer_auth=os.getenv("CRIBL_BEARER_AUTH", ""),
) as c_client:

    res = c_client.projects.delete_project_by_id(id="<id>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `id`                                                                | *str*                                                               | :heavy_check_mark:                                                  | Unique ID to DELETE                                                 |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.DeleteProjectByIDResponseBody](../../models/deleteprojectbyidresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |

## get_project_acl_by_id

List accesses to Project granted to users

### Example Usage

```python
from cribl import Cribl
import os


with Cribl(
    bearer_auth=os.getenv("CRIBL_BEARER_AUTH", ""),
) as c_client:

    res = c_client.projects.get_project_acl_by_id(id="<id>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `id`                                                                | *str*                                                               | :heavy_check_mark:                                                  | Unique ID for ACL Get                                               |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.GetProjectACLByIDResponseBody](../../models/getprojectaclbyidresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |

## create_project_acl_apply_by_id

Add/remove accesses to Project for users

### Example Usage

```python
from cribl import Cribl
import os


with Cribl(
    bearer_auth=os.getenv("CRIBL_BEARER_AUTH", ""),
) as c_client:

    c_client.projects.create_project_acl_apply_by_id(id="<id>")

    # Use the SDK ...

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `id`                                                                | *str*                                                               | :heavy_check_mark:                                                  | Unique ID for ACL Create                                            |
| `add`                                                               | [Optional[models.AccessControl]](../../models/accesscontrol.md)     | :heavy_minus_sign:                                                  | N/A                                                                 |
| `rm`                                                                | [Optional[models.AccessControl]](../../models/accesscontrol.md)     | :heavy_minus_sign:                                                  | N/A                                                                 |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |

## get_project_acl_teams_by_id

List accesses to Project granted to Teams

### Example Usage

```python
from cribl import Cribl
import os


with Cribl(
    bearer_auth=os.getenv("CRIBL_BEARER_AUTH", ""),
) as c_client:

    res = c_client.projects.get_project_acl_teams_by_id(id="<id>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `id`                                                                | *str*                                                               | :heavy_check_mark:                                                  | Unique ID for ACL Teams Get                                         |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.GetProjectACLTeamsByIDResponseBody](../../models/getprojectaclteamsbyidresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |

## create_project_acl_teams_apply_by_id

Add/remove accesses to Project for Teams

### Example Usage

```python
from cribl import Cribl
import os


with Cribl(
    bearer_auth=os.getenv("CRIBL_BEARER_AUTH", ""),
) as c_client:

    c_client.projects.create_project_acl_teams_apply_by_id(id="<id>")

    # Use the SDK ...

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `id`                                                                | *str*                                                               | :heavy_check_mark:                                                  | Unique ID for ACL Teams Create                                      |
| `add`                                                               | [Optional[models.AccessControl]](../../models/accesscontrol.md)     | :heavy_minus_sign:                                                  | N/A                                                                 |
| `rm`                                                                | [Optional[models.AccessControl]](../../models/accesscontrol.md)     | :heavy_minus_sign:                                                  | N/A                                                                 |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |

## get_project_destinations_by_project_id

Lists destinations associated with this project.

### Example Usage

```python
from cribl import Cribl
import os


with Cribl(
    bearer_auth=os.getenv("CRIBL_BEARER_AUTH", ""),
) as c_client:

    res = c_client.projects.get_project_destinations_by_project_id(project_id="<id>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `project_id`                                                        | *str*                                                               | :heavy_check_mark:                                                  | Project Id                                                          |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.GetProjectDestinationsByProjectIDResponseBody](../../models/getprojectdestinationsbyprojectidresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |

## get_subscription_by_project_id

Get the subscriptions associated with the project

### Example Usage

```python
from cribl import Cribl
import os


with Cribl(
    bearer_auth=os.getenv("CRIBL_BEARER_AUTH", ""),
) as c_client:

    res = c_client.projects.get_subscription_by_project_id(project_id="<id>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `project_id`                                                        | *str*                                                               | :heavy_check_mark:                                                  | Project Id                                                          |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.GetSubscriptionByProjectIDResponseBody](../../models/getsubscriptionbyprojectidresponsebody.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.Error     | 500              | application/json |
| models.APIError  | 4XX, 5XX         | \*/\*            |