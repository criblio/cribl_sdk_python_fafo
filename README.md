# -cribl_sdk_python_fafo
 This is unofficial and is used to determine SpeakEasy's capabilities. 

<!-- Start Summary [summary] -->
## Summary

Cribl API Reference: This API Reference lists available REST endpoints, along with their supported operations for accessing, creating, updating, or deleting resources. See our complementary product documentation at [docs.cribl.io](http://docs.cribl.io).
<!-- End Summary [summary] -->

<!-- Start Table of Contents [toc] -->
## Table of Contents
<!-- $toc-max-depth=2 -->
* [-cribl_sdk_python_fafo](#criblsdkpythonfafo)
  * [SDK Installation](#sdk-installation)
  * [IDE Support](#ide-support)
  * [SDK Example Usage](#sdk-example-usage)
  * [Authentication](#authentication)
  * [Available Resources and Operations](#available-resources-and-operations)
  * [Retries](#retries)
  * [Error Handling](#error-handling)
  * [Custom HTTP Client](#custom-http-client)
  * [Resource Management](#resource-management)
  * [Debugging](#debugging)

<!-- End Table of Contents [toc] -->

<!-- Start SDK Installation [installation] -->
## SDK Installation

> [!TIP]
> To finish publishing your SDK to PyPI you must [run your first generation action](https://www.speakeasy.com/docs/github-setup#step-by-step-guide).


> [!NOTE]
> **Python version upgrade policy**
>
> Once a Python version reaches its [official end of life date](https://devguide.python.org/versions/), a 3-month grace period is provided for users to upgrade. Following this grace period, the minimum python version supported in the SDK will be updated.

The SDK can be installed with either *pip* or *poetry* package managers.

### PIP

*PIP* is the default package installer for Python, enabling easy installation and management of packages from PyPI via the command line.

```bash
pip install git+<UNSET>.git
```

### Poetry

*Poetry* is a modern tool that simplifies dependency management and package publishing by using a single `pyproject.toml` file to handle project metadata and dependencies.

```bash
poetry add git+<UNSET>.git
```

### Shell and script usage with `uv`

You can use this SDK in a Python shell with [uv](https://docs.astral.sh/uv/) and the `uvx` command that comes with it like so:

```shell
uvx --from cribl python
```

It's also possible to write a standalone Python script without needing to set up a whole project like so:

```python
#!/usr/bin/env -S uv run --script
# /// script
# requires-python = ">=3.9"
# dependencies = [
#     "cribl",
# ]
# ///

from cribl import Cribl

sdk = Cribl(
  # SDK arguments
)

# Rest of script here...
```

Once that is saved to a file, you can run it with `uv run script.py` where
`script.py` can be replaced with the actual file name.
<!-- End SDK Installation [installation] -->

<!-- Start IDE Support [idesupport] -->
## IDE Support

### PyCharm

Generally, the SDK will work well with most IDEs out of the box. However, when using PyCharm, you can enjoy much better integration with Pydantic by installing an additional plugin.

- [PyCharm Pydantic Plugin](https://docs.pydantic.dev/latest/integrations/pycharm/)
<!-- End IDE Support [idesupport] -->

<!-- Start SDK Example Usage [usage] -->
## SDK Example Usage

### Example

```python
# Synchronous Example
import cribl
from cribl import Cribl
import os


with Cribl(
    server_url="https://api.example.com",
    bearer_auth=os.getenv("CRIBL_BEARER_AUTH", ""),
) as c_client:

    res = c_client.billing.get_usage(organization_id="<id>", metric_type=cribl.MetricType.HYBRID_WORKER_G_BS_RECEIVED, starting_on="<value>", ending_before="<value>")

    # Handle response
    print(res)
```

</br>

The same SDK client can also be used to make asychronous requests by importing asyncio.
```python
# Asynchronous Example
import asyncio
import cribl
from cribl import Cribl
import os

async def main():

    async with Cribl(
        server_url="https://api.example.com",
        bearer_auth=os.getenv("CRIBL_BEARER_AUTH", ""),
    ) as c_client:

        res = await c_client.billing.get_usage_async(organization_id="<id>", metric_type=cribl.MetricType.HYBRID_WORKER_G_BS_RECEIVED, starting_on="<value>", ending_before="<value>")

        # Handle response
        print(res)

asyncio.run(main())
```
<!-- End SDK Example Usage [usage] -->

<!-- Start Authentication [security] -->
## Authentication

### Per-Client Security Schemes

This SDK supports the following security scheme globally:

| Name          | Type | Scheme      | Environment Variable |
| ------------- | ---- | ----------- | -------------------- |
| `bearer_auth` | http | HTTP Bearer | `CRIBL_BEARER_AUTH`  |

To authenticate with the API the `bearer_auth` parameter must be set when initializing the SDK client instance. For example:
```python
import cribl
from cribl import Cribl
import os


with Cribl(
    server_url="https://api.example.com",
    bearer_auth=os.getenv("CRIBL_BEARER_AUTH", ""),
) as c_client:

    res = c_client.billing.get_usage(organization_id="<id>", metric_type=cribl.MetricType.HYBRID_WORKER_G_BS_RECEIVED, starting_on="<value>", ending_before="<value>")

    # Handle response
    print(res)

```
<!-- End Authentication [security] -->

<!-- Start Available Resources and Operations [operations] -->
## Available Resources and Operations

<details open>
<summary>Available methods</summary>

### [appscope_configs](docs/sdks/appscopeconfigs/README.md)

* [list_appscope_lib_entry](docs/sdks/appscopeconfigs/README.md#list_appscope_lib_entry) - Get a list of AppscopeLibEntry objects
* [create_appscope_lib_entry](docs/sdks/appscopeconfigs/README.md#create_appscope_lib_entry) - Create AppscopeLibEntry
* [get_appscope_lib_entry_by_id](docs/sdks/appscopeconfigs/README.md#get_appscope_lib_entry_by_id) - Get AppscopeLibEntry by ID
* [update_appscope_lib_entry_by_id](docs/sdks/appscopeconfigs/README.md#update_appscope_lib_entry_by_id) - Update AppscopeLibEntry
* [delete_appscope_lib_entry_by_id](docs/sdks/appscopeconfigs/README.md#delete_appscope_lib_entry_by_id) - Delete AppscopeLibEntry

### [auth](docs/sdks/auth/README.md)

* [get_auth_authorization_code_callback](docs/sdks/auth/README.md#get_auth_authorization_code_callback) - API call that the IDP should use for an authorization code callback
* [get_auth_metadata](docs/sdks/auth/README.md#get_auth_metadata) - Obtain metadata which Cribl Stream/Edge uses when acting as a Service Provider
* [login](docs/sdks/auth/README.md#login) - Log in and obtain Auth token
* [logout](docs/sdks/auth/README.md#logout) - Log current user out
* [create_auth_slo_callback](docs/sdks/auth/README.md#create_auth_slo_callback) - API call that the IDP should use for a logout request
* [get_auth_slo_callback](docs/sdks/auth/README.md#get_auth_slo_callback) - Accepts a logout request from an IDP and logs out the user
* [get_auth_slo](docs/sdks/auth/README.md#get_auth_slo) - Redirect user to IDP with logout request
* [create_auth_sso_callback](docs/sdks/auth/README.md#create_auth_sso_callback) - API call that the IDP should use for an authentication request
* [get_auth_sso_callback](docs/sdks/auth/README.md#get_auth_sso_callback) - Accepts an authentication request from an IDP and authenticates the user
* [get_auth_sso](docs/sdks/auth/README.md#get_auth_sso) - Obtain redirect information
* [get_auth_groups](docs/sdks/auth/README.md#get_auth_groups) - List the external authentication system's groups
* [get_auth_multi_factor](docs/sdks/auth/README.md#get_auth_multi_factor) - Get PIV configuration
* [delete_auth_users_token_by_id](docs/sdks/auth/README.md#delete_auth_users_token_by_id) - Invalidate token(s) for user *id*

### [authorize](docs/sdks/authorize/README.md)

* [get_authorize_policy](docs/sdks/authorize/README.md#get_authorize_policy) - get the client's authorization policy
* [get_authorize_roles](docs/sdks/authorize/README.md#get_authorize_roles) - get the client's roles

### [banners](docs/sdks/banners/README.md)

* [list_banner_message](docs/sdks/banners/README.md#list_banner_message) - Get a list of BannerMessage objects
* [create_banner_message](docs/sdks/banners/README.md#create_banner_message) - Create BannerMessage
* [get_banner_message_by_id](docs/sdks/banners/README.md#get_banner_message_by_id) - Get BannerMessage by ID
* [update_banner_message_by_id](docs/sdks/banners/README.md#update_banner_message_by_id) - Update BannerMessage
* [delete_banner_message_by_id](docs/sdks/banners/README.md#delete_banner_message_by_id) - Delete BannerMessage

### [billing](docs/sdks/billing/README.md)

* [get_usage](docs/sdks/billing/README.md#get_usage)
* [get_credits](docs/sdks/billing/README.md#get_credits)
* [get_costs](docs/sdks/billing/README.md#get_costs)
* [get_invoices](docs/sdks/billing/README.md#get_invoices)
* [get_invoice](docs/sdks/billing/README.md#get_invoice)
* [get_plan](docs/sdks/billing/README.md#get_plan)

### [certificates](docs/sdks/certificates/README.md)

* [list_certificate](docs/sdks/certificates/README.md#list_certificate) - Get a list of Certificate objects
* [create_certificate](docs/sdks/certificates/README.md#create_certificate) - Create Certificate
* [get_certificate_by_id](docs/sdks/certificates/README.md#get_certificate_by_id) - Get Certificate by ID
* [update_certificate_by_id](docs/sdks/certificates/README.md#update_certificate_by_id) - Update Certificate
* [delete_certificate_by_id](docs/sdks/certificates/README.md#delete_certificate_by_id) - Delete Certificate

### [changelog](docs/sdks/changelog/README.md)

* [get_changelog_viewed](docs/sdks/changelog/README.md#get_changelog_viewed) - Get changelog viewed state

### [click_house](docs/sdks/clickhouse/README.md)

* [create_output_click_house_describe_table](docs/sdks/clickhouse/README.md#create_output_click_house_describe_table) - Retrieve the description of the configured ClickHouse table

### [clui](docs/sdks/clui/README.md)

* [get_clui](docs/sdks/clui/README.md#get_clui) - Get CLUI search results

### [collectors](docs/sdks/collectors/README.md)

* [list_collector](docs/sdks/collectors/README.md#list_collector) - Get a list of Collector objects
* [get_collector_by_id](docs/sdks/collectors/README.md#get_collector_by_id) - Get Collector by ID

### [conditions](docs/sdks/conditions/README.md)

* [list_condition](docs/sdks/conditions/README.md#list_condition) - Get a list of Condition objects
* [get_condition_by_id](docs/sdks/conditions/README.md#get_condition_by_id) - Get Condition by ID

### [consent](docs/sdks/consent/README.md)

* [get_ai_consent](docs/sdks/consent/README.md#get_ai_consent) - Fetches the AI consent information, specifically the org GUID and accepted boolean.
* [create_ai_consent](docs/sdks/consent/README.md#create_ai_consent) - Stores the AI consent information, specifically the org GUID and accepted boolean.


### [dashboard_categories](docs/sdks/dashboardcategories/README.md)

* [list_dashboard_category](docs/sdks/dashboardcategories/README.md#list_dashboard_category) - Get a list of DashboardCategory objects
* [create_dashboard_category](docs/sdks/dashboardcategories/README.md#create_dashboard_category) - Create DashboardCategory
* [get_dashboard_category_by_id](docs/sdks/dashboardcategories/README.md#get_dashboard_category_by_id) - Get DashboardCategory by ID
* [update_dashboard_category_by_id](docs/sdks/dashboardcategories/README.md#update_dashboard_category_by_id) - Update DashboardCategory
* [delete_dashboard_category_by_id](docs/sdks/dashboardcategories/README.md#delete_dashboard_category_by_id) - Delete DashboardCategory

### [dashboards](docs/sdks/dashboards/README.md)

* [list_search_dashboard](docs/sdks/dashboards/README.md#list_search_dashboard) - Get a list of SearchDashboard objects
* [create_search_dashboard](docs/sdks/dashboards/README.md#create_search_dashboard) - Create SearchDashboard
* [get_search_dashboard_by_id](docs/sdks/dashboards/README.md#get_search_dashboard_by_id) - Get SearchDashboard by ID
* [update_search_dashboard_by_id](docs/sdks/dashboards/README.md#update_search_dashboard_by_id) - Update SearchDashboard
* [delete_search_dashboard_by_id](docs/sdks/dashboards/README.md#delete_search_dashboard_by_id) - Delete SearchDashboard
* [get_search_dashboard_acl_by_id](docs/sdks/dashboards/README.md#get_search_dashboard_acl_by_id) - Get SearchDashboard ACL
* [create_search_dashboard_acl_apply_by_id](docs/sdks/dashboards/README.md#create_search_dashboard_acl_apply_by_id) - Modify SearchDashboard ACL
* [get_search_dashboard_acl_teams_by_id](docs/sdks/dashboards/README.md#get_search_dashboard_acl_teams_by_id) - Get SearchDashboard Teams
* [create_search_dashboard_acl_teams_apply_by_id](docs/sdks/dashboards/README.md#create_search_dashboard_acl_teams_apply_by_id) - Modify SearchDashboard Teams ACL

### [database_connections](docs/sdks/databaseconnections/README.md)

* [get_database_connection_config](docs/sdks/databaseconnections/README.md#get_database_connection_config) - Get a list of DatabaseConnection objects
* [create_database_connection_config](docs/sdks/databaseconnections/README.md#create_database_connection_config) - Create DatabaseConnectionConfig
* [get_database_connection_config_by_id](docs/sdks/databaseconnections/README.md#get_database_connection_config_by_id) - Get DatabaseConnectionConfig by ID
* [update_database_connection_config_by_id](docs/sdks/databaseconnections/README.md#update_database_connection_config_by_id) - Update DatabaseConnectionConfig
* [delete_database_connection_config_by_id](docs/sdks/databaseconnections/README.md#delete_database_connection_config_by_id) - Delete DatabaseConnectionConfig
* [create_lib_database_connections_test](docs/sdks/databaseconnections/README.md#create_lib_database_connections_test) - Test a database connection given a type and connectionString

### [datasets](docs/sdks/datasets/README.md)

* [list_dataset_provider_type](docs/sdks/datasets/README.md#list_dataset_provider_type) - Get a list of DatasetProviderType objects
* [create_dataset_provider_type](docs/sdks/datasets/README.md#create_dataset_provider_type) - Create DatasetProviderType
* [get_dataset_provider_type_by_id](docs/sdks/datasets/README.md#get_dataset_provider_type_by_id) - Get DatasetProviderType by ID
* [update_dataset_provider_type_by_id](docs/sdks/datasets/README.md#update_dataset_provider_type_by_id) - Update DatasetProviderType
* [delete_dataset_provider_type_by_id](docs/sdks/datasets/README.md#delete_dataset_provider_type_by_id) - Delete DatasetProviderType
* [list_dataset_provider](docs/sdks/datasets/README.md#list_dataset_provider) - Get a list of DatasetProvider objects
* [create_dataset_provider](docs/sdks/datasets/README.md#create_dataset_provider) - Create DatasetProvider
* [get_dataset_provider_by_id](docs/sdks/datasets/README.md#get_dataset_provider_by_id) - Get DatasetProvider by ID
* [update_dataset_provider_by_id](docs/sdks/datasets/README.md#update_dataset_provider_by_id) - Update DatasetProvider
* [delete_dataset_provider_by_id](docs/sdks/datasets/README.md#delete_dataset_provider_by_id) - Delete DatasetProvider
* [list_dataset](docs/sdks/datasets/README.md#list_dataset) - Get a list of Dataset objects
* [create_dataset](docs/sdks/datasets/README.md#create_dataset) - Create Dataset
* [get_dataset_by_id](docs/sdks/datasets/README.md#get_dataset_by_id) - Get Dataset by ID
* [update_dataset_by_id](docs/sdks/datasets/README.md#update_dataset_by_id) - Update Dataset
* [delete_dataset_by_id](docs/sdks/datasets/README.md#delete_dataset_by_id) - Delete Dataset
* [get_dataset_acl_by_id](docs/sdks/datasets/README.md#get_dataset_acl_by_id) - Get Dataset ACL
* [create_dataset_acl_apply_by_id](docs/sdks/datasets/README.md#create_dataset_acl_apply_by_id) - Modify Dataset ACL
* [get_dataset_acl_teams_by_id](docs/sdks/datasets/README.md#get_dataset_acl_teams_by_id) - Get Dataset Teams
* [create_dataset_acl_teams_apply_by_id](docs/sdks/datasets/README.md#create_dataset_acl_teams_apply_by_id) - Modify Dataset Teams ACL

### [diag](docs/sdks/diagsdk/README.md)

* [get_health_info](docs/sdks/diagsdk/README.md#get_health_info) - Provides health info for REST server
* [get_diag_bundle](docs/sdks/diagsdk/README.md#get_diag_bundle) - Returns a diag bundle as a tar.gz archive
* [get_system_info](docs/sdks/diagsdk/README.md#get_system_info) - Get basic system information
* [get_system_diag](docs/sdks/diagsdk/README.md#get_system_diag) - Get list of existing diag bundles
* [delete_system_diag](docs/sdks/diagsdk/README.md#delete_system_diag) - Remove diag bundle
* [create_system_diag_send](docs/sdks/diagsdk/README.md#create_system_diag_send) - Send a diag bundle (tar.gz archive) to Cribl

### [distributed](docs/sdks/distributed/README.md)

* [get_summary_workers](docs/sdks/distributed/README.md#get_summary_workers) - get worker and edge nodes count
* [get_workers](docs/sdks/distributed/README.md#get_workers) - get worker and edge nodes
* [update_workers_restart](docs/sdks/distributed/README.md#update_workers_restart) - restarts worker nodes
* [get_config_bundles_by_group_and_version](docs/sdks/distributed/README.md#get_config_bundles_by_group_and_version) - Download config bundle (used by remote nodes)
* [get_summary](docs/sdks/distributed/README.md#get_summary) - Get summary of Distributed deployment

### [edge](docs/sdks/edge/README.md)

* [create_edge_appscope_processes](docs/sdks/edge/README.md#create_edge_appscope_processes) - Attach AppScope to a process running on the edge host
* [get_edge_appscope_processes](docs/sdks/edge/README.md#get_edge_appscope_processes) - Get a detailed list of scoped processes running on the edge host
* [delete_edge_appscope_processes_by_pid](docs/sdks/edge/README.md#delete_edge_appscope_processes_by_pid) - Detach AppScope from a process running on the edge host
* [get_edge_appscope_processes_by_pid](docs/sdks/edge/README.md#get_edge_appscope_processes_by_pid) - Get details of a scoped process running on the edge host
* [update_edge_appscope_processes_by_pid](docs/sdks/edge/README.md#update_edge_appscope_processes_by_pid) - Update AppScope configuration for a process running on the edge host
* [get_edge_events_collectors](docs/sdks/edge/README.md#get_edge_events_collectors) - Get list of configured collectors
* [get_edge_fileinspect](docs/sdks/edge/README.md#get_edge_fileinspect) - Get details about a file on the edge host.
* [get_edge_ls_by_path](docs/sdks/edge/README.md#get_edge_ls_by_path) - Get a directory listing of the given path
* [create_products_edge_map_query](docs/sdks/edge/README.md#create_products_edge_map_query) - Data for the Map View for Edge Fleets (Leader only)
* [get_edge_metadata](docs/sdks/edge/README.md#get_edge_metadata) - Get the host's metadata structure
* [create_edge_file_ingest](docs/sdks/edge/README.md#create_edge_file_ingest) - Ingest a specified file through a specified pipeline to a specified destination or send to routes.
* [get_edge_file_sample](docs/sdks/edge/README.md#get_edge_file_sample) - Get some number of bytes from the file at the given path
* [create_edge_kube_logs](docs/sdks/edge/README.md#create_edge_kube_logs) - Make a request to the K8s API logs endpoint
* [get_edge_kube_proxy](docs/sdks/edge/README.md#get_edge_kube_proxy) - Make a GET request to the K8s API
* [get_edge_containers_by_id](docs/sdks/edge/README.md#get_edge_containers_by_id) - Get details for a single container on the edge host. Add stream=true to get a stream instead.
* [get_edge_containers](docs/sdks/edge/README.md#get_edge_containers) - Get a detailed list of containers running on the edge host.
* [get_edge_logs](docs/sdks/edge/README.md#get_edge_logs) - list log files
* [get_edge_processes_by_pid](docs/sdks/edge/README.md#get_edge_processes_by_pid) - Get details of a process running on the edge host
* [get_edge_processes](docs/sdks/edge/README.md#get_edge_processes) - Get a detailed list of processes running on the edge host

### [edge_app_scope_processes](docs/sdks/edgeappscopeprocesses/README.md)

* [create_edge_appscope_processes](docs/sdks/edgeappscopeprocesses/README.md#create_edge_appscope_processes) - Attach AppScope to a process running on the edge host
* [get_edge_appscope_processes](docs/sdks/edgeappscopeprocesses/README.md#get_edge_appscope_processes) - Get a detailed list of scoped processes running on the edge host
* [delete_edge_appscope_processes_by_pid](docs/sdks/edgeappscopeprocesses/README.md#delete_edge_appscope_processes_by_pid) - Detach AppScope from a process running on the edge host
* [get_edge_appscope_processes_by_pid](docs/sdks/edgeappscopeprocesses/README.md#get_edge_appscope_processes_by_pid) - Get details of a scoped process running on the edge host
* [update_edge_appscope_processes_by_pid](docs/sdks/edgeappscopeprocesses/README.md#update_edge_appscope_processes_by_pid) - Update AppScope configuration for a process running on the edge host

### [edge_containers](docs/sdks/edgecontainers/README.md)

* [get_edge_containers_by_id](docs/sdks/edgecontainers/README.md#get_edge_containers_by_id) - Get details for a single container on the edge host. Add stream=true to get a stream instead.
* [get_edge_containers](docs/sdks/edgecontainers/README.md#get_edge_containers) - Get a detailed list of containers running on the edge host.

### [edge_events](docs/sdks/edgeevents/README.md)

* [get_edge_events_collectors](docs/sdks/edgeevents/README.md#get_edge_events_collectors) - Get list of configured collectors

### [edge_files](docs/sdks/edgefiles/README.md)

* [get_edge_fileinspect](docs/sdks/edgefiles/README.md#get_edge_fileinspect) - Get details about a file on the edge host.

### [edge_ls](docs/sdks/edgels/README.md)

* [get_edge_ls_by_path](docs/sdks/edgels/README.md#get_edge_ls_by_path) - Get a directory listing of the given path

### [edge_processes](docs/sdks/edgeprocesses/README.md)

* [get_edge_processes_by_pid](docs/sdks/edgeprocesses/README.md#get_edge_processes_by_pid) - Get details of a process running on the edge host
* [get_edge_processes](docs/sdks/edgeprocesses/README.md#get_edge_processes) - Get a detailed list of processes running on the edge host

### [event_breaker_rules](docs/sdks/eventbreakerrules/README.md)

* [list_event_breaker_ruleset](docs/sdks/eventbreakerrules/README.md#list_event_breaker_ruleset) - Get a list of Event Breaker Ruleset objects
* [create_event_breaker_ruleset](docs/sdks/eventbreakerrules/README.md#create_event_breaker_ruleset) - Create Event Breaker Ruleset
* [get_event_breaker_ruleset_by_id](docs/sdks/eventbreakerrules/README.md#get_event_breaker_ruleset_by_id) - Get Event Breaker Ruleset by ID
* [update_event_breaker_ruleset_by_id](docs/sdks/eventbreakerrules/README.md#update_event_breaker_ruleset_by_id) - Update Event Breaker Ruleset
* [delete_event_breaker_ruleset_by_id](docs/sdks/eventbreakerrules/README.md#delete_event_breaker_ruleset_by_id) - Delete Event Breaker Ruleset

### [events](docs/sdks/events/README.md)

* [get_edge_events_query](docs/sdks/events/README.md#get_edge_events_query) - Get events generated by a specified source

### [executors](docs/sdks/executors/README.md)

* [list_executor](docs/sdks/executors/README.md#list_executor) - Get a list of Executor objects
* [get_executor_by_id](docs/sdks/executors/README.md#get_executor_by_id) - Get Executor by ID

### [expressions](docs/sdks/expressions/README.md)

* [create_lib_expression](docs/sdks/expressions/README.md#create_lib_expression) - Evaluate JavaScript expression

### [features](docs/sdks/features/README.md)

* [get_features_entry_by_id](docs/sdks/features/README.md#get_features_entry_by_id) - Get feature by id (i.e. 'type-name`)
* [get_features_entry](docs/sdks/features/README.md#get_features_entry) - List all features

### [file](docs/sdks/file/README.md)

* [create_edge_file_ingest](docs/sdks/file/README.md#create_edge_file_ingest) - Ingest a specified file through a specified pipeline to a specified destination or send to routes.

### [file_sampler](docs/sdks/filesampler/README.md)

* [get_edge_file_sample](docs/sdks/filesampler/README.md#get_edge_file_sample) - Get some number of bytes from the file at the given path

### [functions](docs/sdks/functions/README.md)

* [list_function](docs/sdks/functions/README.md#list_function) - Get a list of Function objects
* [get_function_by_id](docs/sdks/functions/README.md#get_function_by_id) - Get Function by ID
* [get_function_by_pack](docs/sdks/functions/README.md#get_function_by_pack) - Get a list of Function objects within a Pack
* [get_function_by_pack_and_id](docs/sdks/functions/README.md#get_function_by_pack_and_id) - Get Function by ID within a Pack

### [git](docs/sdks/git/README.md)

* [get_system_projects_version_count_by_group_id_and_project_id](docs/sdks/git/README.md#get_system_projects_version_count_by_group_id_and_project_id) - Get the count of files of changed
* [get_system_projects_version_diff_by_group_id_and_project_id](docs/sdks/git/README.md#get_system_projects_version_diff_by_group_id_and_project_id) - Get the textual diff for given commit
* [get_system_projects_version_files_by_group_id_and_project_id](docs/sdks/git/README.md#get_system_projects_version_files_by_group_id_and_project_id) - Get the files changed
* [create_system_projects_version_commit_by_group_id_and_project_id](docs/sdks/git/README.md#create_system_projects_version_commit_by_group_id_and_project_id) - Commit project changes
* [create_system_projects_version_commit_by_project_id](docs/sdks/git/README.md#create_system_projects_version_commit_by_project_id) - Commit project changes.
* [get_system_projects_version_count_by_project_id](docs/sdks/git/README.md#get_system_projects_version_count_by_project_id) - get the count of files of changed
* [get_system_projects_version_diff_by_project_id](docs/sdks/git/README.md#get_system_projects_version_diff_by_project_id) - get the textual diff for given commit
* [get_system_projects_version_files_by_project_id](docs/sdks/git/README.md#get_system_projects_version_files_by_project_id) - get the files changed
* [create_system_projects_version_revert_by_project_id](docs/sdks/git/README.md#create_system_projects_version_revert_by_project_id) - Revert project changes.
* [get_system_projects_version_show_by_project_id](docs/sdks/git/README.md#get_system_projects_version_show_by_project_id) - Show project changes.
* [get_system_settings_git_settings](docs/sdks/git/README.md#get_system_settings_git_settings) - Get git settings
* [update_system_settings_git_settings](docs/sdks/git/README.md#update_system_settings_git_settings) - Update git settings
* [undo_last_commit](docs/sdks/git/README.md#undo_last_commit) - undo the last commit
* [get_version_branch](docs/sdks/git/README.md#get_version_branch) - get the list of branches
* [create_version_commit](docs/sdks/git/README.md#create_version_commit) - create a new commit containing the current configs the given log message describing the changes.
* [get_version_count](docs/sdks/git/README.md#get_version_count) - get the count of files of changed
* [get_version_current_branch](docs/sdks/git/README.md#get_version_current_branch) - returns git branch that the config is checked out to, if any
* [get_version_diff](docs/sdks/git/README.md#get_version_diff) - get the textual diff for given commit
* [get_version_files](docs/sdks/git/README.md#get_version_files) - get the files changed
* [get_version_info](docs/sdks/git/README.md#get_version_info) - Get info about versioning availability
* [create_version_push](docs/sdks/git/README.md#create_version_push) - push the current configs to the remote repository.
* [create_version_revert](docs/sdks/git/README.md#create_version_revert) - revert a commit
* [get_version_show](docs/sdks/git/README.md#get_version_show) - get the log message and textual diff for given commit
* [get_version_status](docs/sdks/git/README.md#get_version_status) - get the the working tree status
* [create_version_sync](docs/sdks/git/README.md#create_version_sync) - syncs with remote repo via POST requests

### [global_variables](docs/sdks/globalvariables/README.md)

* [get_global_variable](docs/sdks/globalvariables/README.md#get_global_variable) - List all GlobalVars with references
* [create_global_variable](docs/sdks/globalvariables/README.md#create_global_variable) - Create Global Variable
* [get_global_variable_by_id](docs/sdks/globalvariables/README.md#get_global_variable_by_id) - Get Global Variable by ID
* [update_global_variable_by_id](docs/sdks/globalvariables/README.md#update_global_variable_by_id) - Update Global Variable
* [delete_global_variable_by_id](docs/sdks/globalvariables/README.md#delete_global_variable_by_id) - Delete Global Variable
* [get_global_variable_lib_vars_by_pack](docs/sdks/globalvariables/README.md#get_global_variable_lib_vars_by_pack) - List all GlobalVars with references within a Pack
* [create_global_variable_lib_vars_by_pack](docs/sdks/globalvariables/README.md#create_global_variable_lib_vars_by_pack) - Create Global Variable within a Pack
* [get_global_variable_lib_vars_by_pack_and_id](docs/sdks/globalvariables/README.md#get_global_variable_lib_vars_by_pack_and_id) - Get Global Variable by ID within a Pack
* [update_global_variable_lib_vars_by_pack_and_id](docs/sdks/globalvariables/README.md#update_global_variable_lib_vars_by_pack_and_id) - Update Global Variable within a Pack
* [delete_global_variable_lib_vars_by_pack_and_id](docs/sdks/globalvariables/README.md#delete_global_variable_lib_vars_by_pack_and_id) - Delete Global Variable within a Pack

### [grokfiles](docs/sdks/grokfiles/README.md)

* [list_grok_file](docs/sdks/grokfiles/README.md#list_grok_file) - Get a list of GrokFile objects
* [create_grok_file](docs/sdks/grokfiles/README.md#create_grok_file) - Create GrokFile
* [get_grok_file_by_id](docs/sdks/grokfiles/README.md#get_grok_file_by_id) - Get GrokFile by ID
* [update_grok_file_by_id](docs/sdks/grokfiles/README.md#update_grok_file_by_id) - Update GrokFile
* [delete_grok_file_by_id](docs/sdks/grokfiles/README.md#delete_grok_file_by_id) - Delete GrokFile

### [groups](docs/sdks/groups/README.md)

* [get_groups_config_version_by_id](docs/sdks/groups/README.md#get_groups_config_version_by_id) - Get effective bundle version for given Group
* [create_products_groups_by_product](docs/sdks/groups/README.md#create_products_groups_by_product) - Create a Fleet or Worker Group
* [get_products_groups_by_product](docs/sdks/groups/README.md#get_products_groups_by_product) - Get a list of ConfigGroup objects
* [update_groups_deploy_by_id](docs/sdks/groups/README.md#update_groups_deploy_by_id) - Deploy commits for a Fleet or Worker Group
* [get_groups_by_id](docs/sdks/groups/README.md#get_groups_by_id) - Get a specific ConfigGroup object
* [get_groups_acl_by_id](docs/sdks/groups/README.md#get_groups_acl_by_id) - ACL of members with permissions for resources in this Group

### [health](docs/sdks/health/README.md)

* [get_health_info](docs/sdks/health/README.md#get_health_info) - Provides health info for REST server

### [hmac_functions](docs/sdks/hmacfunctions/README.md)

* [list_hmac_function](docs/sdks/hmacfunctions/README.md#list_hmac_function) - Get a list of HmacFunction objects
* [create_hmac_function](docs/sdks/hmacfunctions/README.md#create_hmac_function) - Create HmacFunction
* [get_hmac_function_by_id](docs/sdks/hmacfunctions/README.md#get_hmac_function_by_id) - Get HmacFunction by ID
* [update_hmac_function_by_id](docs/sdks/hmacfunctions/README.md#update_hmac_function_by_id) - Update HmacFunction
* [delete_hmac_function_by_id](docs/sdks/hmacfunctions/README.md#delete_hmac_function_by_id) - Delete HmacFunction

### [ingest](docs/sdks/ingest/README.md)

* [create_edge_file_ingest](docs/sdks/ingest/README.md#create_edge_file_ingest) - Ingest a specified file through a specified pipeline to a specified destination or send to routes.

### [inputs](docs/sdks/inputs/README.md)

* [list_input](docs/sdks/inputs/README.md#list_input) - Get a list of Input objects
* [create_input](docs/sdks/inputs/README.md#create_input) - Create Input
* [get_input_by_id](docs/sdks/inputs/README.md#get_input_by_id) - Get Input by ID
* [update_input_by_id](docs/sdks/inputs/README.md#update_input_by_id) - Update Input
* [delete_input_by_id](docs/sdks/inputs/README.md#delete_input_by_id) - Delete Input
* [create_input_hec_token_by_id](docs/sdks/inputs/README.md#create_input_hec_token_by_id) - Add token and optional metadata to an existing hec input
* [update_input_hec_token_by_id_and_token](docs/sdks/inputs/README.md#update_input_hec_token_by_id_and_token) - Update token metadata on existing hec input
* [list_input_status](docs/sdks/inputs/README.md#list_input_status) - Get a list of InputStatus objects
* [get_input_status_by_id](docs/sdks/inputs/README.md#get_input_status_by_id) - Get InputStatus by ID

### [jobs](docs/sdks/jobs/README.md)

* [get_job_results_by_id](docs/sdks/jobs/README.md#get_job_results_by_id) - Get results for a discover job by instance id
* [update_jobs_cancel_by_id](docs/sdks/jobs/README.md#update_jobs_cancel_by_id) - Cancel a job by instance id
* [create_jobs](docs/sdks/jobs/README.md#create_jobs) - Run or schedule a job
* [get_jobs](docs/sdks/jobs/README.md#get_jobs) - Get info on jobs
* [delete_jobs_by_id](docs/sdks/jobs/README.md#delete_jobs_by_id) - Remove job from job inspector by instance id
* [get_jobs_by_id](docs/sdks/jobs/README.md#get_jobs_by_id) - Get job info by instance id
* [update_jobs_keep_by_id](docs/sdks/jobs/README.md#update_jobs_keep_by_id) - prevent job from being deleted automatically
* [update_jobs_pause_by_id](docs/sdks/jobs/README.md#update_jobs_pause_by_id) - Pause a job by instance id
* [update_jobs_resume_by_id](docs/sdks/jobs/README.md#update_jobs_resume_by_id) - Resume a job by instance id
* [get_jobs_results_by_id_and_group](docs/sdks/jobs/README.md#get_jobs_results_by_id_and_group) - Get results for a discover job by instance id
* [get_jobs_errors_by_id_and_group](docs/sdks/jobs/README.md#get_jobs_errors_by_id_and_group) - Get Task errors for a job by id
* [get_jobs_errors_by_id](docs/sdks/jobs/README.md#get_jobs_errors_by_id) - Get Task errors for a job by id

### [keys](docs/sdks/keys/README.md)

* [list_key_metadata_entity](docs/sdks/keys/README.md#list_key_metadata_entity) - Get a list of KeyMetadataEntity objects
* [create_key_metadata_entity](docs/sdks/keys/README.md#create_key_metadata_entity) - Create KeyMetadataEntity
* [get_key_metadata_entity_by_id](docs/sdks/keys/README.md#get_key_metadata_entity_by_id) - Get KeyMetadataEntity by ID
* [update_key_metadata_entity_by_id](docs/sdks/keys/README.md#update_key_metadata_entity_by_id) - Update KeyMetadataEntity
* [delete_key_metadata_entity_by_id](docs/sdks/keys/README.md#delete_key_metadata_entity_by_id) - Delete KeyMetadataEntity

### [kube_logs](docs/sdks/kubelogs/README.md)

* [create_edge_kube_logs](docs/sdks/kubelogs/README.md#create_edge_kube_logs) - Make a request to the K8s API logs endpoint

### [kube_proxy](docs/sdks/kubeproxy/README.md)

* [get_edge_kube_proxy](docs/sdks/kubeproxy/README.md#get_edge_kube_proxy) - Make a GET request to the K8s API

### [lake](docs/sdks/lake/README.md)

* [create_cribl_lake_dataset_by_lake_id](docs/sdks/lake/README.md#create_cribl_lake_dataset_by_lake_id) - Create a Dataset in the specified Lake
* [get_cribl_lake_dataset_by_lake_id](docs/sdks/lake/README.md#get_cribl_lake_dataset_by_lake_id) - Get the list of Dataset contained in the specified Lake
* [delete_cribl_lake_dataset_by_lake_id_and_id](docs/sdks/lake/README.md#delete_cribl_lake_dataset_by_lake_id_and_id) - Delete a Dataset in the specified Lake
* [get_cribl_lake_dataset_by_lake_id_and_id](docs/sdks/lake/README.md#get_cribl_lake_dataset_by_lake_id_and_id) - Get a Dataset in the specified Lake
* [update_cribl_lake_dataset_by_lake_id_and_id](docs/sdks/lake/README.md#update_cribl_lake_dataset_by_lake_id_and_id) - Update a Dataset in the specified Lake

### [licenses](docs/sdks/licenses/README.md)

* [list_license](docs/sdks/licenses/README.md#list_license) - Get a list of License objects
* [create_license](docs/sdks/licenses/README.md#create_license) - Add a license to your deployment
* [get_license_by_id](docs/sdks/licenses/README.md#get_license_by_id) - Get License by ID
* [delete_license_by_id](docs/sdks/licenses/README.md#delete_license_by_id) - Delete License
* [get_license](docs/sdks/licenses/README.md#get_license) - Get license usage metrics, aggregated by day, up to last 90 days

### [logger](docs/sdks/logger/README.md)

* [list_logger_config](docs/sdks/logger/README.md#list_logger_config) - Get a list of LoggerConfig objects
* [get_logger_config_by_id](docs/sdks/logger/README.md#get_logger_config_by_id) - Get LoggerConfig by ID
* [update_logger_config_by_id](docs/sdks/logger/README.md#update_logger_config_by_id) - Update LoggerConfig
* [delete_logger_config_by_id](docs/sdks/logger/README.md#delete_logger_config_by_id) - Delete LoggerConfig

### [logging](docs/sdks/logging/README.md)

* [get_system_jobs_logs_by_id_and_group_id](docs/sdks/logging/README.md#get_system_jobs_logs_by_id_and_group_id) - Get contents of the log file
* [get_system_logs_by_id](docs/sdks/logging/README.md#get_system_logs_by_id) - Get contents of the log file
* [get_system_logs](docs/sdks/logging/README.md#get_system_logs) - Get a list of log files
* [get_system_logs_search](docs/sdks/logging/README.md#get_system_logs_search) - Get contents of the log file

### [lookups](docs/sdks/lookups/README.md)

* [list_lookup_file](docs/sdks/lookups/README.md#list_lookup_file) - Get a list of LookupFile objects
* [create_lookup_file](docs/sdks/lookups/README.md#create_lookup_file) - Create LookupFile
* [update_lookup_file](docs/sdks/lookups/README.md#update_lookup_file) - Upload LookupFile
* [get_lookup_file_by_id](docs/sdks/lookups/README.md#get_lookup_file_by_id) - Get LookupFile by ID
* [update_lookup_file_by_id](docs/sdks/lookups/README.md#update_lookup_file_by_id) - Update LookupFile
* [delete_lookup_file_by_id](docs/sdks/lookups/README.md#delete_lookup_file_by_id) - Delete LookupFile

### [macros](docs/sdks/macros/README.md)

* [list_search_macro](docs/sdks/macros/README.md#list_search_macro) - Get a list of SearchMacro objects
* [create_search_macro](docs/sdks/macros/README.md#create_search_macro) - Create SearchMacro
* [get_search_macro_by_id](docs/sdks/macros/README.md#get_search_macro_by_id) - Get SearchMacro by ID
* [update_search_macro_by_id](docs/sdks/macros/README.md#update_search_macro_by_id) - Update SearchMacro
* [delete_search_macro_by_id](docs/sdks/macros/README.md#delete_search_macro_by_id) - Delete SearchMacro

### [messages](docs/sdks/messages/README.md)

* [list_bulletin_message](docs/sdks/messages/README.md#list_bulletin_message) - Get a list of BulletinMessage objects
* [create_bulletin_message](docs/sdks/messages/README.md#create_bulletin_message) - Create BulletinMessage
* [get_bulletin_message_by_id](docs/sdks/messages/README.md#get_bulletin_message_by_id) - Get BulletinMessage by ID
* [delete_bulletin_message_by_id](docs/sdks/messages/README.md#delete_bulletin_message_by_id) - Delete BulletinMessage

### [metrics](docs/sdks/metrics/README.md)

* [create_system_metrics_enum](docs/sdks/metrics/README.md#create_system_metrics_enum) - Enumerate all internal system metrics
* [get_system_metrics](docs/sdks/metrics/README.md#get_system_metrics) - Query raw internal system metrics
* [create_system_metrics_query](docs/sdks/metrics/README.md#create_system_metrics_query) - Aggregate raw internal system metrics

### [notification_targets](docs/sdks/notificationtargets/README.md)

* [list_notification_target](docs/sdks/notificationtargets/README.md#list_notification_target) - Get a list of NotificationTarget objects
* [create_notification_target](docs/sdks/notificationtargets/README.md#create_notification_target) - Create NotificationTarget
* [get_notification_target_by_id](docs/sdks/notificationtargets/README.md#get_notification_target_by_id) - Get NotificationTarget by ID
* [update_notification_target_by_id](docs/sdks/notificationtargets/README.md#update_notification_target_by_id) - Update NotificationTarget
* [delete_notification_target_by_id](docs/sdks/notificationtargets/README.md#delete_notification_target_by_id) - Delete NotificationTarget

### [notifications](docs/sdks/notifications/README.md)

* [list_notification](docs/sdks/notifications/README.md#list_notification) - Get a list of Notification objects
* [create_notification](docs/sdks/notifications/README.md#create_notification) - Create Notification
* [get_notification_by_id](docs/sdks/notifications/README.md#get_notification_by_id) - Get Notification by ID
* [update_notification_by_id](docs/sdks/notifications/README.md#update_notification_by_id) - Update Notification
* [delete_notification_by_id](docs/sdks/notifications/README.md#delete_notification_by_id) - Delete Notification

### [outputs](docs/sdks/outputs/README.md)

* [list_output](docs/sdks/outputs/README.md#list_output) - Get a list of Output objects
* [create_output](docs/sdks/outputs/README.md#create_output) - Create Output
* [get_output_by_id](docs/sdks/outputs/README.md#get_output_by_id) - Get Output by ID
* [update_output_by_id](docs/sdks/outputs/README.md#update_output_by_id) - Update Output
* [delete_output_by_id](docs/sdks/outputs/README.md#delete_output_by_id) - Delete Output
* [delete_output_pq_by_id](docs/sdks/outputs/README.md#delete_output_pq_by_id) - Clears destination persistent queue
* [get_output_pq_by_id](docs/sdks/outputs/README.md#get_output_pq_by_id) - Retrieves status of latest clear PQ job for an output
* [get_output_samples_by_id](docs/sdks/outputs/README.md#get_output_samples_by_id) - Retrieve samples data for the specified output. Used to get sample data for the test action.
* [create_output_test_by_id](docs/sdks/outputs/README.md#create_output_test_by_id) - Send sample data to an output to validate configuration or test connectivity
* [list_output_status](docs/sdks/outputs/README.md#list_output_status) - Get a list of OutputStatus objects
* [get_output_status_by_id](docs/sdks/outputs/README.md#get_output_status_by_id) - Get OutputStatus by ID

### [packs](docs/sdks/packs/README.md)

* [create_packs](docs/sdks/packs/README.md#create_packs) - Install Pack
* [get_packs](docs/sdks/packs/README.md#get_packs) - Get info on packs
* [update_packs](docs/sdks/packs/README.md#update_packs) - Upload Pack
* [delete_packs_by_id](docs/sdks/packs/README.md#delete_packs_by_id) - Uninstall Pack from the system
* [update_packs_by_id](docs/sdks/packs/README.md#update_packs_by_id) - Upgrade Pack
* [create_packs_clone](docs/sdks/packs/README.md#create_packs_clone) - Clone Pack
* [get_packs_export_by_id](docs/sdks/packs/README.md#get_packs_export_by_id) - Export Pack

### [parquetschemas](docs/sdks/parquetschemas/README.md)

* [list_schema](docs/sdks/parquetschemas/README.md#list_schema) - Get a list of Schema objects
* [create_schema](docs/sdks/parquetschemas/README.md#create_schema) - Create Schema
* [get_schema_by_id](docs/sdks/parquetschemas/README.md#get_schema_by_id) - Get Schema by ID
* [update_schema_by_id](docs/sdks/parquetschemas/README.md#update_schema_by_id) - Update Schema
* [delete_schema_by_id](docs/sdks/parquetschemas/README.md#delete_schema_by_id) - Delete Schema

### [parsers](docs/sdks/parsers/README.md)

* [list_parser](docs/sdks/parsers/README.md#list_parser) - Get a list of Parser objects
* [create_parser](docs/sdks/parsers/README.md#create_parser) - Create Parser
* [get_parser_by_id](docs/sdks/parsers/README.md#get_parser_by_id) - Get Parser by ID
* [update_parser_by_id](docs/sdks/parsers/README.md#update_parser_by_id) - Update Parser
* [delete_parser_by_id](docs/sdks/parsers/README.md#delete_parser_by_id) - Delete Parser

### [pipelines](docs/sdks/pipelines/README.md)

* [get_system_projects_pipelines_by_group_id_and_project_id](docs/sdks/pipelines/README.md#get_system_projects_pipelines_by_group_id_and_project_id) - Get A list of Pipeline objects for specified Project
* [create_system_projects_pipelines_by_group_id_and_project_id](docs/sdks/pipelines/README.md#create_system_projects_pipelines_by_group_id_and_project_id) - Create Pipeline
* [get_system_projects_pipelines_by_group_id_and_project_id_and_pipeline_id](docs/sdks/pipelines/README.md#get_system_projects_pipelines_by_group_id_and_project_id_and_pipeline_id) - Get Pipeline by ID in specified Project
* [update_system_projects_pipelines_by_group_id_and_project_id_and_pipeline_id](docs/sdks/pipelines/README.md#update_system_projects_pipelines_by_group_id_and_project_id_and_pipeline_id) - Update Pipeline in specified Project
* [delete_system_projects_pipelines_by_group_id_and_project_id_and_pipeline_id](docs/sdks/pipelines/README.md#delete_system_projects_pipelines_by_group_id_and_project_id_and_pipeline_id) - Delete Pipeline in specified Project
* [list_pipeline](docs/sdks/pipelines/README.md#list_pipeline) - Get a list of Pipeline objects
* [create_pipeline](docs/sdks/pipelines/README.md#create_pipeline) - Create Pipeline
* [get_pipeline_by_id](docs/sdks/pipelines/README.md#get_pipeline_by_id) - Get Pipeline by ID
* [update_pipeline_by_id](docs/sdks/pipelines/README.md#update_pipeline_by_id) - Update Pipeline
* [delete_pipeline_by_id](docs/sdks/pipelines/README.md#delete_pipeline_by_id) - Delete Pipeline
* [get_pipeline_by_pack](docs/sdks/pipelines/README.md#get_pipeline_by_pack) - Get a list of Pipeline objects within a Pack
* [create_pipeline_by_pack](docs/sdks/pipelines/README.md#create_pipeline_by_pack) - Create Pipeline within a Pack
* [get_pipeline_by_pack_and_id](docs/sdks/pipelines/README.md#get_pipeline_by_pack_and_id) - Get Pipeline by ID within a Pack
* [update_pipeline_by_pack_and_id](docs/sdks/pipelines/README.md#update_pipeline_by_pack_and_id) - Update Pipeline within a Pack
* [delete_pipeline_by_pack_and_id](docs/sdks/pipelines/README.md#delete_pipeline_by_pack_and_id) - Delete Pipeline within a Pack

### [policies](docs/sdks/policies/README.md)

* [list_policy_rule](docs/sdks/policies/README.md#list_policy_rule) - Get a list of PolicyRule objects
* [create_policy_rule](docs/sdks/policies/README.md#create_policy_rule) - Create PolicyRule
* [get_policy_rule_by_id](docs/sdks/policies/README.md#get_policy_rule_by_id) - Get PolicyRule by ID
* [update_policy_rule_by_id](docs/sdks/policies/README.md#update_policy_rule_by_id) - Update PolicyRule
* [delete_policy_rule_by_id](docs/sdks/policies/README.md#delete_policy_rule_by_id) - Delete PolicyRule

### [preview](docs/sdks/preview/README.md)

* [create_system_projects_subscriptions_capture_by_group_id_and_subscription_id](docs/sdks/preview/README.md#create_system_projects_subscriptions_capture_by_group_id_and_subscription_id) - Capture live incoming data from a particular Project and Subscription at the Subscription
* [create_system_projects_capture_by_group_id_and_project_id](docs/sdks/preview/README.md#create_system_projects_capture_by_group_id_and_project_id) - Capture live incoming data from a particular Project and Subscription at the Destination
* [create_system_projects_preview_by_group_id_and_project_id](docs/sdks/preview/README.md#create_system_projects_preview_by_group_id_and_project_id) - Sends sample events through a Pipeline  for specified Project and returns the results
* [create_system_capture](docs/sdks/preview/README.md#create_system_capture) - Capture live incoming data
* [create_system_projects_capture_by_project_id](docs/sdks/preview/README.md#create_system_projects_capture_by_project_id) - Capture live incoming data from a particular project and subscription at the destination
* [create_system_projects_subscriptions_capture_by_project_id_and_subscription_id](docs/sdks/preview/README.md#create_system_projects_subscriptions_capture_by_project_id_and_subscription_id) - Capture live incoming data from a particular project and subscription at the subscription
* [create_preview](docs/sdks/preview/README.md#create_preview) - Sends sample events through a pipeline and returns the results

### [processes](docs/sdks/processes/README.md)

* [get_system_processes](docs/sdks/processes/README.md#get_system_processes) - Get a list of processes under management

### [profiler](docs/sdks/profiler/README.md)

* [list_profiler_item](docs/sdks/profiler/README.md#list_profiler_item) - Get a list of ProfilerItem objects
* [create_profiler_item](docs/sdks/profiler/README.md#create_profiler_item) - Create ProfilerItem
* [get_profiler_item_by_id](docs/sdks/profiler/README.md#get_profiler_item_by_id) - Get ProfilerItem by ID
* [update_profiler_item_by_id](docs/sdks/profiler/README.md#update_profiler_item_by_id) - Update ProfilerItem
* [delete_profiler_item_by_id](docs/sdks/profiler/README.md#delete_profiler_item_by_id) - Delete ProfilerItem

### [projects](docs/sdks/projects/README.md)

* [get_system_projects_subscriptions_by_group_id_by_and_project_id](docs/sdks/projects/README.md#get_system_projects_subscriptions_by_group_id_by_and_project_id) - Get the Subscriptions associated with the Project
* [get_system_projects_version_count_by_group_id_and_project_id](docs/sdks/projects/README.md#get_system_projects_version_count_by_group_id_and_project_id) - Get the count of files of changed
* [get_system_projects_version_diff_by_group_id_and_project_id](docs/sdks/projects/README.md#get_system_projects_version_diff_by_group_id_and_project_id) - Get the textual diff for given commit
* [get_system_projects_version_files_by_group_id_and_project_id](docs/sdks/projects/README.md#get_system_projects_version_files_by_group_id_and_project_id) - Get the files changed
* [create_system_projects_version_commit_by_group_id_and_project_id](docs/sdks/projects/README.md#create_system_projects_version_commit_by_group_id_and_project_id) - Commit project changes
* [create_system_projects_subscriptions_capture_by_group_id_and_subscription_id](docs/sdks/projects/README.md#create_system_projects_subscriptions_capture_by_group_id_and_subscription_id) - Capture live incoming data from a particular Project and Subscription at the Subscription
* [create_system_projects_capture_by_group_id_and_project_id](docs/sdks/projects/README.md#create_system_projects_capture_by_group_id_and_project_id) - Capture live incoming data from a particular Project and Subscription at the Destination
* [create_system_projects_preview_by_group_id_and_project_id](docs/sdks/projects/README.md#create_system_projects_preview_by_group_id_and_project_id) - Sends sample events through a Pipeline  for specified Project and returns the results
* [get_system_projects_pipelines_by_group_id_and_project_id](docs/sdks/projects/README.md#get_system_projects_pipelines_by_group_id_and_project_id) - Get A list of Pipeline objects for specified Project
* [create_system_projects_pipelines_by_group_id_and_project_id](docs/sdks/projects/README.md#create_system_projects_pipelines_by_group_id_and_project_id) - Create Pipeline
* [get_system_projects_pipelines_by_group_id_and_project_id_and_pipeline_id](docs/sdks/projects/README.md#get_system_projects_pipelines_by_group_id_and_project_id_and_pipeline_id) - Get Pipeline by ID in specified Project
* [update_system_projects_pipelines_by_group_id_and_project_id_and_pipeline_id](docs/sdks/projects/README.md#update_system_projects_pipelines_by_group_id_and_project_id_and_pipeline_id) - Update Pipeline in specified Project
* [delete_system_projects_pipelines_by_group_id_and_project_id_and_pipeline_id](docs/sdks/projects/README.md#delete_system_projects_pipelines_by_group_id_and_project_id_and_pipeline_id) - Delete Pipeline in specified Project
* [create_system_projects_version_commit_by_project_id](docs/sdks/projects/README.md#create_system_projects_version_commit_by_project_id) - Commit project changes.
* [get_system_projects_version_count_by_project_id](docs/sdks/projects/README.md#get_system_projects_version_count_by_project_id) - get the count of files of changed
* [get_system_projects_version_diff_by_project_id](docs/sdks/projects/README.md#get_system_projects_version_diff_by_project_id) - get the textual diff for given commit
* [get_system_projects_version_files_by_project_id](docs/sdks/projects/README.md#get_system_projects_version_files_by_project_id) - get the files changed
* [create_system_projects_version_revert_by_project_id](docs/sdks/projects/README.md#create_system_projects_version_revert_by_project_id) - Revert project changes.
* [get_system_projects_version_show_by_project_id](docs/sdks/projects/README.md#get_system_projects_version_show_by_project_id) - Show project changes.
* [list_project](docs/sdks/projects/README.md#list_project) - Get a list of Project objects
* [create_project](docs/sdks/projects/README.md#create_project) - Create Project
* [get_project_by_id](docs/sdks/projects/README.md#get_project_by_id) - Get Project by ID
* [update_project_by_id](docs/sdks/projects/README.md#update_project_by_id) - Update Project
* [delete_project_by_id](docs/sdks/projects/README.md#delete_project_by_id) - Delete Project
* [get_project_acl_by_id](docs/sdks/projects/README.md#get_project_acl_by_id) - Get Project ACL
* [create_project_acl_apply_by_id](docs/sdks/projects/README.md#create_project_acl_apply_by_id) - Modify Project ACL
* [get_project_acl_teams_by_id](docs/sdks/projects/README.md#get_project_acl_teams_by_id) - Get Project Teams
* [create_project_acl_teams_apply_by_id](docs/sdks/projects/README.md#create_project_acl_teams_apply_by_id) - Modify Project Teams ACL
* [get_project_destinations_by_project_id](docs/sdks/projects/README.md#get_project_destinations_by_project_id) - Lists destinations associated with this project.
* [get_subscription_by_project_id](docs/sdks/projects/README.md#get_subscription_by_project_id) - Get the subscriptions associated with the project

### [protobuflibraries](docs/sdks/protobuflibraries/README.md)

* [get_protobuf_library_config](docs/sdks/protobuflibraries/README.md#get_protobuf_library_config) - Show list of Protobuf encodings for a given Library
* [get_protobuf_library_config_by_id](docs/sdks/protobuflibraries/README.md#get_protobuf_library_config_by_id) - Show Library by Id
* [get_protobuf_library_config_encodings_by_id_and_enc_id](docs/sdks/protobuflibraries/README.md#get_protobuf_library_config_encodings_by_id_and_enc_id) - Show Protobuf library encodings by encoding id
* [get_protobuf_library_config_encodings_by_id](docs/sdks/protobuflibraries/README.md#get_protobuf_library_config_encodings_by_id) - Show list of Protobuf encodings for a given Library

### [regexes](docs/sdks/regexes/README.md)

* [list_regex_lib_entry](docs/sdks/regexes/README.md#list_regex_lib_entry) - Get a list of RegexLibEntry objects
* [create_regex_lib_entry](docs/sdks/regexes/README.md#create_regex_lib_entry) - Create RegexLibEntry
* [get_regex_lib_entry_by_id](docs/sdks/regexes/README.md#get_regex_lib_entry_by_id) - Get RegexLibEntry by ID
* [update_regex_lib_entry_by_id](docs/sdks/regexes/README.md#update_regex_lib_entry_by_id) - Update RegexLibEntry
* [delete_regex_lib_entry_by_id](docs/sdks/regexes/README.md#delete_regex_lib_entry_by_id) - Delete RegexLibEntry

### [roles](docs/sdks/roles/README.md)

* [list_role](docs/sdks/roles/README.md#list_role) - Get a list of Role objects
* [create_role](docs/sdks/roles/README.md#create_role) - Create Role
* [get_role_by_id](docs/sdks/roles/README.md#get_role_by_id) - Get Role by ID
* [update_role_by_id](docs/sdks/roles/README.md#update_role_by_id) - Update Role
* [delete_role_by_id](docs/sdks/roles/README.md#delete_role_by_id) - Delete Role

### [routes](docs/sdks/routessdk/README.md)

* [list_routes](docs/sdks/routessdk/README.md#list_routes) - Get a list of Routes objects
* [get_routes_by_id](docs/sdks/routessdk/README.md#get_routes_by_id) - Get Routes by ID
* [update_routes_by_id](docs/sdks/routessdk/README.md#update_routes_by_id) - Update Routes
* [create_routes_append_by_id](docs/sdks/routessdk/README.md#create_routes_append_by_id) - Appends routes to the end of the routing table
* [get_routes_by_pack](docs/sdks/routessdk/README.md#get_routes_by_pack) - Get a list of Routes objects within a Pack
* [get_routes_by_pack_and_id](docs/sdks/routessdk/README.md#get_routes_by_pack_and_id) - Get Routes by ID within a Pack
* [update_routes_by_pack_and_id](docs/sdks/routessdk/README.md#update_routes_by_pack_and_id) - Update Routes within a Pack
* [create_routes_append_by_pack_and_id](docs/sdks/routessdk/README.md#create_routes_append_by_pack_and_id) - Appends routes to the end of the routing table within a Pack

### [samples](docs/sdks/samples/README.md)

* [create_system_projects_subscriptions_capture_by_group_id_and_subscription_id](docs/sdks/samples/README.md#create_system_projects_subscriptions_capture_by_group_id_and_subscription_id) - Capture live incoming data from a particular Project and Subscription at the Subscription
* [create_system_projects_capture_by_group_id_and_project_id](docs/sdks/samples/README.md#create_system_projects_capture_by_group_id_and_project_id) - Capture live incoming data from a particular Project and Subscription at the Destination
* [create_system_projects_preview_by_group_id_and_project_id](docs/sdks/samples/README.md#create_system_projects_preview_by_group_id_and_project_id) - Sends sample events through a Pipeline  for specified Project and returns the results
* [list_data_sample](docs/sdks/samples/README.md#list_data_sample) - Get a list of DataSample objects
* [create_data_sample](docs/sdks/samples/README.md#create_data_sample) - Create DataSample
* [get_data_sample_by_id](docs/sdks/samples/README.md#get_data_sample_by_id) - Get DataSample by ID
* [update_data_sample_by_id](docs/sdks/samples/README.md#update_data_sample_by_id) - Update DataSample
* [delete_data_sample_by_id](docs/sdks/samples/README.md#delete_data_sample_by_id) - Delete DataSample
* [get_data_sample_content_by_id](docs/sdks/samples/README.md#get_data_sample_content_by_id) - Get sample content by ID
* [create_system_capture](docs/sdks/samples/README.md#create_system_capture) - Capture live incoming data
* [create_system_projects_capture_by_project_id](docs/sdks/samples/README.md#create_system_projects_capture_by_project_id) - Capture live incoming data from a particular project and subscription at the destination
* [create_system_projects_subscriptions_capture_by_project_id_and_subscription_id](docs/sdks/samples/README.md#create_system_projects_subscriptions_capture_by_project_id_and_subscription_id) - Capture live incoming data from a particular project and subscription at the subscription
* [create_preview](docs/sdks/samples/README.md#create_preview) - Sends sample events through a pipeline and returns the results

### [sandboxes](docs/sdks/sandboxes/README.md)

* [assign_sandbox_workspace_to_user](docs/sdks/sandboxes/README.md#assign_sandbox_workspace_to_user)
* [get_assignments](docs/sdks/sandboxes/README.md#get_assignments)

### [saved_jobs](docs/sdks/savedjobs/README.md)

* [list_saved_job](docs/sdks/savedjobs/README.md#list_saved_job) - Get a list of SavedJob objects
* [create_saved_job](docs/sdks/savedjobs/README.md#create_saved_job) - Create SavedJob
* [get_saved_job_by_id](docs/sdks/savedjobs/README.md#get_saved_job_by_id) - Get SavedJob by ID
* [update_saved_job_by_id](docs/sdks/savedjobs/README.md#update_saved_job_by_id) - Update SavedJob
* [delete_saved_job_by_id](docs/sdks/savedjobs/README.md#delete_saved_job_by_id) - Delete SavedJob

### [saved_queries](docs/sdks/savedqueries/README.md)

* [list_saved_query](docs/sdks/savedqueries/README.md#list_saved_query) - Get a list of SavedQuery objects
* [create_saved_query](docs/sdks/savedqueries/README.md#create_saved_query) - Create SavedQuery
* [get_saved_query_by_id](docs/sdks/savedqueries/README.md#get_saved_query_by_id) - Get SavedQuery by ID
* [update_saved_query_by_id](docs/sdks/savedqueries/README.md#update_saved_query_by_id) - Update SavedQuery
* [delete_saved_query_by_id](docs/sdks/savedqueries/README.md#delete_saved_query_by_id) - Delete SavedQuery

### [schemas](docs/sdks/schemas/README.md)

* [list_lib_schemas](docs/sdks/schemas/README.md#list_lib_schemas) - Get a list of Schema objects
* [create_lib_schemas](docs/sdks/schemas/README.md#create_lib_schemas) - Create Schema
* [get_lib_schemas_by_id](docs/sdks/schemas/README.md#get_lib_schemas_by_id) - Get Schema by ID
* [update_lib_schemas_by_id](docs/sdks/schemas/README.md#update_lib_schemas_by_id) - Update Schema
* [delete_lib_schemas_by_id](docs/sdks/schemas/README.md#delete_lib_schemas_by_id) - Delete Schema
* [get_schema_lib_by_pack](docs/sdks/schemas/README.md#get_schema_lib_by_pack) - Get a list of Schema objects within a Pack
* [create_schema_lib_by_pack](docs/sdks/schemas/README.md#create_schema_lib_by_pack) - Create Schema within a Pack
* [get_schema_lib_by_pack_and_id](docs/sdks/schemas/README.md#get_schema_lib_by_pack_and_id) - Get Schema by ID within a Pack
* [update_schema_lib_by_pack_and_id](docs/sdks/schemas/README.md#update_schema_lib_by_pack_and_id) - Update Schema within a Pack
* [delete_schema_lib_by_pack_and_id](docs/sdks/schemas/README.md#delete_schema_lib_by_pack_and_id) - Delete Schema within a Pack

### [scripts](docs/sdks/scripts/README.md)

* [list_script](docs/sdks/scripts/README.md#list_script) - Get a list of Script objects
* [create_script](docs/sdks/scripts/README.md#create_script) - Create Script
* [get_script_by_id](docs/sdks/scripts/README.md#get_script_by_id) - Get Script by ID
* [update_script_by_id](docs/sdks/scripts/README.md#update_script_by_id) - Update Script
* [delete_script_by_id](docs/sdks/scripts/README.md#delete_script_by_id) - Delete Script

### [search](docs/sdks/search/README.md)

* [list_search_job](docs/sdks/search/README.md#list_search_job) - Get a list of SearchJob objects
* [create_search_job](docs/sdks/search/README.md#create_search_job) - Create SearchJob
* [get_search_job_by_id](docs/sdks/search/README.md#get_search_job_by_id) - Get SearchJob by ID
* [update_search_job_by_id](docs/sdks/search/README.md#update_search_job_by_id) - Update SearchJob
* [delete_search_job_by_id](docs/sdks/search/README.md#delete_search_job_by_id) - Delete SearchJob
* [create_search_job_dispatch_executors_by_id](docs/sdks/search/README.md#create_search_job_dispatch_executors_by_id) - internal endpoint, dispatch search *id* to worker nodes filtered by worker node filter using RPC
* [get_search_job_logs_by_id](docs/sdks/search/README.md#get_search_job_logs_by_id) - Get search logs
* [create_search_event_breaker_preview](docs/sdks/search/README.md#create_search_event_breaker_preview) - Runs an event breaker rule on the specified data
* [get_search_healthcheck](docs/sdks/search/README.md#get_search_healthcheck) - Get health check metric for search
* [get_search_jobs_metrics_by_id](docs/sdks/search/README.md#get_search_jobs_metrics_by_id) - Get search job metrics
* [get_search_job_metrics](docs/sdks/search/README.md#get_search_job_metrics) - List metrics for all search jobs
* [create_search_preview](docs/sdks/search/README.md#create_search_preview) - Applies a query snippet on a set of input events for preview
* [get_search_jobs_stages_results_by_id_and_stage_id](docs/sdks/search/README.md#get_search_jobs_stages_results_by_id_and_stage_id) - List search results for a given stage. Note that this cannot be the root stage!
* [get_search_jobs_results_by_id](docs/sdks/search/README.md#get_search_jobs_results_by_id) - List search results, when lower/upper bound is provided, offset is relative to the time range.
* [get_search_jobs_results_poll_by_id](docs/sdks/search/README.md#get_search_jobs_results_poll_by_id) - List search results

### [secrets](docs/sdks/secrets/README.md)

* [list_rest_secret](docs/sdks/secrets/README.md#list_rest_secret) - Get a list of RestSecret objects
* [create_rest_secret](docs/sdks/secrets/README.md#create_rest_secret) - Create RestSecret
* [get_rest_secret_by_id](docs/sdks/secrets/README.md#get_rest_secret_by_id) - Get RestSecret by ID
* [update_rest_secret_by_id](docs/sdks/secrets/README.md#update_rest_secret_by_id) - Update RestSecret
* [delete_rest_secret_by_id](docs/sdks/secrets/README.md#delete_rest_secret_by_id) - Delete RestSecret

### [security](docs/sdks/security/README.md)

* [get_security_kms_config](docs/sdks/security/README.md#get_security_kms_config) - Get Cribl KMS config
* [update_security_kms_config](docs/sdks/security/README.md#update_security_kms_config) - Update Cribl KMS config
* [get_security_kms_health](docs/sdks/security/README.md#get_security_kms_health) - Get Cribl KMS health

### [subscriptions](docs/sdks/subscriptions/README.md)

* [get_system_projects_subscriptions_by_group_id_by_and_project_id](docs/sdks/subscriptions/README.md#get_system_projects_subscriptions_by_group_id_by_and_project_id) - Get the Subscriptions associated with the Project
* [list_subscription](docs/sdks/subscriptions/README.md#list_subscription) - Get a list of Subscription objects
* [create_subscription](docs/sdks/subscriptions/README.md#create_subscription) - Create subscription
* [get_subscription_by_id](docs/sdks/subscriptions/README.md#get_subscription_by_id) - Get Subscription by ID
* [update_subscription_by_id](docs/sdks/subscriptions/README.md#update_subscription_by_id) - Update subscription
* [delete_subscription_by_id](docs/sdks/subscriptions/README.md#delete_subscription_by_id) - Delete subscription
* [get_subscription_by_project_id](docs/sdks/subscriptions/README.md#get_subscription_by_project_id) - Get the subscriptions associated with the project

### [system](docs/sdks/system/README.md)

* [update_changelog_viewed](docs/sdks/system/README.md#update_changelog_viewed) - Update changelog viewed state
* [create_system_distributed_upgrade_cancel_by_group](docs/sdks/system/README.md#create_system_distributed_upgrade_cancel_by_group) - Cancel a running group upgrade
* [create_system_distributed_upgrade_stage_by_group](docs/sdks/system/README.md#create_system_distributed_upgrade_stage_by_group) - Stage distributed group upgrade
* [create_system_distributed_upgrade_by_group](docs/sdks/system/README.md#create_system_distributed_upgrade_by_group) - Execute distributed group upgrade
* [get_system_distributed_upgrade_download_by_file](docs/sdks/system/README.md#get_system_distributed_upgrade_download_by_file) - Get the previously downloaded Cribl package
* [reload_settings](docs/sdks/system/README.md#reload_settings) - Reload Cribl settings from the filesystem
* [trigger_restart](docs/sdks/system/README.md#trigger_restart) - Restart Cribl server
* [get_system_settings_auth](docs/sdks/system/README.md#get_system_settings_auth) - Get authentication settings
* [update_system_settings_auth](docs/sdks/system/README.md#update_system_settings_auth) - Update authentication settings
* [get_system_settings_conf](docs/sdks/system/README.md#get_system_settings_conf) - Get Cribl system settings
* [update_system_settings_conf](docs/sdks/system/README.md#update_system_settings_conf) - Update Cribl system settings
* [get_system_settings_git_settings](docs/sdks/system/README.md#get_system_settings_git_settings) - Get git settings
* [update_system_settings_git_settings](docs/sdks/system/README.md#update_system_settings_git_settings) - Update git settings
* [get_system_settings_search_limits](docs/sdks/system/README.md#get_system_settings_search_limits) - Get search limits
* [~~get_system_settings~~](docs/sdks/system/README.md#get_system_settings) - Get Cribl system settings. Deprecated: use specific endpoints /system/limits, /system/job-limits, /system/redis-cache-limits, /system/services-limits, /system/settings/git-settings, and /system/settings/conf respectively :warning: **Deprecated**
* [~~update_system_settings~~](docs/sdks/system/README.md#update_system_settings) - Update Cribl system settings. Deprecated: use specific endpoints /system/limits, /system/job-limits, /system/settings/git-settings, /system/settings/auth and /system/settings/conf respectively :warning: **Deprecated**
* [get_system_settings_cribl](docs/sdks/system/README.md#get_system_settings_cribl) - Get public settings visible to any logged user
* [get_system_settings_upgrade](docs/sdks/system/README.md#get_system_settings_upgrade) - Get a list of Cribl versions available for upgrade
* [create_system_settings_upgrade_by_version](docs/sdks/system/README.md#create_system_settings_upgrade_by_version) - Upgrade Cribl to a given version
* [create_system_settings_upgrade_from_package](docs/sdks/system/README.md#create_system_settings_upgrade_from_package) - Upgrade master node with the provided package

### [teams](docs/sdks/teams/README.md)

* [create_team](docs/sdks/teams/README.md#create_team) - Create Team
* [get_team](docs/sdks/teams/README.md#get_team) - Get a list of Team objects
* [get_team_by_id](docs/sdks/teams/README.md#get_team_by_id) - Get Team by ID
* [update_team_by_id](docs/sdks/teams/README.md#update_team_by_id) - Update Team
* [delete_team_by_id](docs/sdks/teams/README.md#delete_team_by_id) - Delete Team
* [get_team_acl_by_id](docs/sdks/teams/README.md#get_team_acl_by_id) - Get Teams's Access Control List
* [get_team_roles_by_id](docs/sdks/teams/README.md#get_team_roles_by_id) - Get user's product roles
* [get_team_users_by_id](docs/sdks/teams/README.md#get_team_users_by_id) - Get users on a team
* [create_team_users_by_id](docs/sdks/teams/README.md#create_team_users_by_id) - Update existing users on a team – admin use only
* [get_products_groups_acl_teams_by_product_and_id](docs/sdks/teams/README.md#get_products_groups_acl_teams_by_product_and_id) - ACL of team with permissions for resources in this Group

### [teams_acl](docs/sdks/teamsacl/README.md)

* [get_dataset_acl_teams_by_id](docs/sdks/teamsacl/README.md#get_dataset_acl_teams_by_id) - Get Dataset Teams
* [create_dataset_acl_teams_apply_by_id](docs/sdks/teamsacl/README.md#create_dataset_acl_teams_apply_by_id) - Modify Dataset Teams ACL
* [get_search_dashboard_acl_teams_by_id](docs/sdks/teamsacl/README.md#get_search_dashboard_acl_teams_by_id) - Get SearchDashboard Teams
* [create_search_dashboard_acl_teams_apply_by_id](docs/sdks/teamsacl/README.md#create_search_dashboard_acl_teams_apply_by_id) - Modify SearchDashboard Teams ACL
* [get_project_acl_teams_by_id](docs/sdks/teamsacl/README.md#get_project_acl_teams_by_id) - Get Project Teams
* [create_project_acl_teams_apply_by_id](docs/sdks/teamsacl/README.md#create_project_acl_teams_apply_by_id) - Modify Project Teams ACL

### [trust_policies](docs/sdks/trustpolicies/README.md)

* [list_trust_policy](docs/sdks/trustpolicies/README.md#list_trust_policy) - Get a list of TrustPolicy objects

### [ui_state](docs/sdks/uistate/README.md)

* [get_ui_by_key](docs/sdks/uistate/README.md#get_ui_by_key) - Get UI state by key
* [update_ui_by_key](docs/sdks/uistate/README.md#update_ui_by_key) - Update UI state by key

### [usage_groups](docs/sdks/usagegroups/README.md)

* [list_usage_group](docs/sdks/usagegroups/README.md#list_usage_group) - Get a list of UsageGroup objects
* [create_usage_group](docs/sdks/usagegroups/README.md#create_usage_group) - Create UsageGroup
* [get_usage_group_by_id](docs/sdks/usagegroups/README.md#get_usage_group_by_id) - Get UsageGroup by ID
* [update_usage_group_by_id](docs/sdks/usagegroups/README.md#update_usage_group_by_id) - Update UsageGroup
* [delete_usage_group_by_id](docs/sdks/usagegroups/README.md#delete_usage_group_by_id) - Delete UsageGroup

### [users](docs/sdks/users/README.md)

* [list_user](docs/sdks/users/README.md#list_user) - Get a list of User objects
* [create_user](docs/sdks/users/README.md#create_user) - Create User
* [get_user_by_id](docs/sdks/users/README.md#get_user_by_id) - Get User by ID
* [update_user_by_id](docs/sdks/users/README.md#update_user_by_id) - Update User properties – admin use only
* [delete_user_by_id](docs/sdks/users/README.md#delete_user_by_id) - Delete User
* [update_user_info_by_id](docs/sdks/users/README.md#update_user_info_by_id) - Update User except for their roles
* [get_products_users_acl_by_product_and_id](docs/sdks/users/README.md#get_products_users_acl_by_product_and_id) - Get user's Access Control List
* [get_products_users_by_product](docs/sdks/users/README.md#get_products_users_by_product) - Get Users belonging to a product
* [delete_products_users_cache_by_product](docs/sdks/users/README.md#delete_products_users_cache_by_product) - Invalidate the members cache for a given product in SaaS deployment.

### [users_acl](docs/sdks/usersacl/README.md)

* [get_dataset_acl_by_id](docs/sdks/usersacl/README.md#get_dataset_acl_by_id) - Get Dataset ACL
* [create_dataset_acl_apply_by_id](docs/sdks/usersacl/README.md#create_dataset_acl_apply_by_id) - Modify Dataset ACL
* [get_search_dashboard_acl_by_id](docs/sdks/usersacl/README.md#get_search_dashboard_acl_by_id) - Get SearchDashboard ACL
* [create_search_dashboard_acl_apply_by_id](docs/sdks/usersacl/README.md#create_search_dashboard_acl_apply_by_id) - Modify SearchDashboard ACL
* [get_project_acl_by_id](docs/sdks/usersacl/README.md#get_project_acl_by_id) - Get Project ACL
* [create_project_acl_apply_by_id](docs/sdks/usersacl/README.md#create_project_acl_apply_by_id) - Modify Project ACL
* [get_groups_acl_by_id](docs/sdks/usersacl/README.md#get_groups_acl_by_id) - ACL of members with permissions for resources in this Group


#### [v5.billing](docs/sdks/criblbilling/README.md)


#### [v5.billing.consumption](docs/sdks/consumption/README.md)

* [v5_billing_consumption_get_credits_summary](docs/sdks/consumption/README.md#v5_billing_consumption_get_credits_summary)
* [v5_billing_consumption_get_cumulative_consumption](docs/sdks/consumption/README.md#v5_billing_consumption_get_cumulative_consumption)
* [v5_billing_consumption_get_products_breakdown](docs/sdks/consumption/README.md#v5_billing_consumption_get_products_breakdown)
* [v5_billing_consumption_get_products_consumption_stats](docs/sdks/consumption/README.md#v5_billing_consumption_get_products_consumption_stats)
* [v5_billing_consumption_get_single_product_usage_breakdown](docs/sdks/consumption/README.md#v5_billing_consumption_get_single_product_usage_breakdown)

#### [v5.billing.invoices](docs/sdks/invoices/README.md)

* [v5_billing_invoices_get_invoices](docs/sdks/invoices/README.md#v5_billing_invoices_get_invoices)
* [v5_billing_invoices_get_invoice](docs/sdks/invoices/README.md#v5_billing_invoices_get_invoice)

### [versioning](docs/sdks/versioning/README.md)

* [get_system_projects_version_count_by_group_id_and_project_id](docs/sdks/versioning/README.md#get_system_projects_version_count_by_group_id_and_project_id) - Get the count of files of changed
* [get_system_projects_version_diff_by_group_id_and_project_id](docs/sdks/versioning/README.md#get_system_projects_version_diff_by_group_id_and_project_id) - Get the textual diff for given commit
* [get_system_projects_version_files_by_group_id_and_project_id](docs/sdks/versioning/README.md#get_system_projects_version_files_by_group_id_and_project_id) - Get the files changed
* [create_system_projects_version_commit_by_group_id_and_project_id](docs/sdks/versioning/README.md#create_system_projects_version_commit_by_group_id_and_project_id) - Commit project changes
* [create_system_projects_version_commit_by_project_id](docs/sdks/versioning/README.md#create_system_projects_version_commit_by_project_id) - Commit project changes.
* [get_system_projects_version_count_by_project_id](docs/sdks/versioning/README.md#get_system_projects_version_count_by_project_id) - get the count of files of changed
* [get_system_projects_version_diff_by_project_id](docs/sdks/versioning/README.md#get_system_projects_version_diff_by_project_id) - get the textual diff for given commit
* [get_system_projects_version_files_by_project_id](docs/sdks/versioning/README.md#get_system_projects_version_files_by_project_id) - get the files changed
* [create_system_projects_version_revert_by_project_id](docs/sdks/versioning/README.md#create_system_projects_version_revert_by_project_id) - Revert project changes.
* [get_system_projects_version_show_by_project_id](docs/sdks/versioning/README.md#get_system_projects_version_show_by_project_id) - Show project changes.
* [undo_last_commit](docs/sdks/versioning/README.md#undo_last_commit) - undo the last commit
* [get_version_branch](docs/sdks/versioning/README.md#get_version_branch) - get the list of branches
* [create_version_commit](docs/sdks/versioning/README.md#create_version_commit) - create a new commit containing the current configs the given log message describing the changes.
* [get_version_count](docs/sdks/versioning/README.md#get_version_count) - get the count of files of changed
* [get_version_current_branch](docs/sdks/versioning/README.md#get_version_current_branch) - returns git branch that the config is checked out to, if any
* [get_version_diff](docs/sdks/versioning/README.md#get_version_diff) - get the textual diff for given commit
* [get_version_files](docs/sdks/versioning/README.md#get_version_files) - get the files changed
* [get_version_info](docs/sdks/versioning/README.md#get_version_info) - Get info about versioning availability
* [create_version_push](docs/sdks/versioning/README.md#create_version_push) - push the current configs to the remote repository.
* [create_version_revert](docs/sdks/versioning/README.md#create_version_revert) - revert a commit
* [get_version_show](docs/sdks/versioning/README.md#get_version_show) - get the log message and textual diff for given commit
* [get_version_status](docs/sdks/versioning/README.md#get_version_status) - get the the working tree status
* [create_version_sync](docs/sdks/versioning/README.md#create_version_sync) - syncs with remote repo via POST requests

### [workers](docs/sdks/workers/README.md)

* [get_summary_workers](docs/sdks/workers/README.md#get_summary_workers) - get worker and edge nodes count
* [get_workers](docs/sdks/workers/README.md#get_workers) - get worker and edge nodes
* [update_workers_restart](docs/sdks/workers/README.md#update_workers_restart) - restarts worker nodes

### [workspaces](docs/sdks/workspaces/README.md)

* [workspaces_controller_list_workspaces](docs/sdks/workspaces/README.md#workspaces_controller_list_workspaces)
* [workspaces_controller_create_workspace](docs/sdks/workspaces/README.md#workspaces_controller_create_workspace)
* [workspaces_controller_get_workspace](docs/sdks/workspaces/README.md#workspaces_controller_get_workspace)
* [workspaces_controller_delete_workspace](docs/sdks/workspaces/README.md#workspaces_controller_delete_workspace)
* [workspaces_controller_patch_workspace](docs/sdks/workspaces/README.md#workspaces_controller_patch_workspace)

</details>
<!-- End Available Resources and Operations [operations] -->

<!-- Start Retries [retries] -->
## Retries

Some of the endpoints in this SDK support retries. If you use the SDK without any configuration, it will fall back to the default retry strategy provided by the API. However, the default retry strategy can be overridden on a per-operation basis, or across the entire SDK.

To change the default retry strategy for a single API call, simply provide a `RetryConfig` object to the call:
```python
import cribl
from cribl import Cribl
from cribl.utils import BackoffStrategy, RetryConfig
import os


with Cribl(
    server_url="https://api.example.com",
    bearer_auth=os.getenv("CRIBL_BEARER_AUTH", ""),
) as c_client:

    res = c_client.billing.get_usage(organization_id="<id>", metric_type=cribl.MetricType.HYBRID_WORKER_G_BS_RECEIVED, starting_on="<value>", ending_before="<value>",
        RetryConfig("backoff", BackoffStrategy(1, 50, 1.1, 100), False))

    # Handle response
    print(res)

```

If you'd like to override the default retry strategy for all operations that support retries, you can use the `retry_config` optional parameter when initializing the SDK:
```python
import cribl
from cribl import Cribl
from cribl.utils import BackoffStrategy, RetryConfig
import os


with Cribl(
    server_url="https://api.example.com",
    retry_config=RetryConfig("backoff", BackoffStrategy(1, 50, 1.1, 100), False),
    bearer_auth=os.getenv("CRIBL_BEARER_AUTH", ""),
) as c_client:

    res = c_client.billing.get_usage(organization_id="<id>", metric_type=cribl.MetricType.HYBRID_WORKER_G_BS_RECEIVED, starting_on="<value>", ending_before="<value>")

    # Handle response
    print(res)

```
<!-- End Retries [retries] -->

<!-- Start Error Handling [errors] -->
## Error Handling

Handling errors in this SDK should largely match your expectations. All operations return a response object or raise an exception.

By default, an API error will raise a models.APIError exception, which has the following properties:

| Property        | Type             | Description           |
|-----------------|------------------|-----------------------|
| `.status_code`  | *int*            | The HTTP status code  |
| `.message`      | *str*            | The error message     |
| `.raw_response` | *httpx.Response* | The raw HTTP response |
| `.body`         | *str*            | The response content  |

When custom error responses are specified for an operation, the SDK may also raise their associated exceptions. You can refer to respective *Errors* tables in SDK docs for more details on possible exception types for each operation. For example, the `get_system_projects_subscriptions_by_group_id_by_and_project_id_async` method may raise the following exceptions:

| Error Type      | Status Code | Content Type     |
| --------------- | ----------- | ---------------- |
| models.Error    | 500         | application/json |
| models.APIError | 4XX, 5XX    | \*/\*            |

### Example

```python
from cribl import Cribl, models
import os


with Cribl(
    server_url="https://api.example.com",
    bearer_auth=os.getenv("CRIBL_BEARER_AUTH", ""),
) as c_client:
    res = None
    try:

        res = c_client.projects.get_system_projects_subscriptions_by_group_id_by_and_project_id(group_id="<id>", project_id="<id>")

        # Handle response
        print(res)

    except models.Error as e:
        # handle e.data: models.ErrorData
        raise(e)
    except models.APIError as e:
        # handle exception
        raise(e)
```
<!-- End Error Handling [errors] -->

<!-- Start Custom HTTP Client [http-client] -->
## Custom HTTP Client

The Python SDK makes API calls using the [httpx](https://www.python-httpx.org/) HTTP library.  In order to provide a convenient way to configure timeouts, cookies, proxies, custom headers, and other low-level configuration, you can initialize the SDK client with your own HTTP client instance.
Depending on whether you are using the sync or async version of the SDK, you can pass an instance of `HttpClient` or `AsyncHttpClient` respectively, which are Protocol's ensuring that the client has the necessary methods to make API calls.
This allows you to wrap the client with your own custom logic, such as adding custom headers, logging, or error handling, or you can just pass an instance of `httpx.Client` or `httpx.AsyncClient` directly.

For example, you could specify a header for every request that this sdk makes as follows:
```python
from cribl import Cribl
import httpx

http_client = httpx.Client(headers={"x-custom-header": "someValue"})
s = Cribl(client=http_client)
```

or you could wrap the client with your own custom logic:
```python
from cribl import Cribl
from cribl.httpclient import AsyncHttpClient
import httpx

class CustomClient(AsyncHttpClient):
    client: AsyncHttpClient

    def __init__(self, client: AsyncHttpClient):
        self.client = client

    async def send(
        self,
        request: httpx.Request,
        *,
        stream: bool = False,
        auth: Union[
            httpx._types.AuthTypes, httpx._client.UseClientDefault, None
        ] = httpx.USE_CLIENT_DEFAULT,
        follow_redirects: Union[
            bool, httpx._client.UseClientDefault
        ] = httpx.USE_CLIENT_DEFAULT,
    ) -> httpx.Response:
        request.headers["Client-Level-Header"] = "added by client"

        return await self.client.send(
            request, stream=stream, auth=auth, follow_redirects=follow_redirects
        )

    def build_request(
        self,
        method: str,
        url: httpx._types.URLTypes,
        *,
        content: Optional[httpx._types.RequestContent] = None,
        data: Optional[httpx._types.RequestData] = None,
        files: Optional[httpx._types.RequestFiles] = None,
        json: Optional[Any] = None,
        params: Optional[httpx._types.QueryParamTypes] = None,
        headers: Optional[httpx._types.HeaderTypes] = None,
        cookies: Optional[httpx._types.CookieTypes] = None,
        timeout: Union[
            httpx._types.TimeoutTypes, httpx._client.UseClientDefault
        ] = httpx.USE_CLIENT_DEFAULT,
        extensions: Optional[httpx._types.RequestExtensions] = None,
    ) -> httpx.Request:
        return self.client.build_request(
            method,
            url,
            content=content,
            data=data,
            files=files,
            json=json,
            params=params,
            headers=headers,
            cookies=cookies,
            timeout=timeout,
            extensions=extensions,
        )

s = Cribl(async_client=CustomClient(httpx.AsyncClient()))
```
<!-- End Custom HTTP Client [http-client] -->

<!-- Start Resource Management [resource-management] -->
## Resource Management

The `Cribl` class implements the context manager protocol and registers a finalizer function to close the underlying sync and async HTTPX clients it uses under the hood. This will close HTTP connections, release memory and free up other resources held by the SDK. In short-lived Python programs and notebooks that make a few SDK method calls, resource management may not be a concern. However, in longer-lived programs, it is beneficial to create a single SDK instance via a [context manager][context-manager] and reuse it across the application.

[context-manager]: https://docs.python.org/3/reference/datamodel.html#context-managers

```python
from cribl import Cribl
import os
def main():

    with Cribl(
        server_url="https://api.example.com",
        bearer_auth=os.getenv("CRIBL_BEARER_AUTH", ""),
    ) as c_client:
        # Rest of application here...


# Or when using async:
async def amain():

    async with Cribl(
        server_url="https://api.example.com",
        bearer_auth=os.getenv("CRIBL_BEARER_AUTH", ""),
    ) as c_client:
        # Rest of application here...
```
<!-- End Resource Management [resource-management] -->

<!-- Start Debugging [debug] -->
## Debugging

You can setup your SDK to emit debug logs for SDK requests and responses.

You can pass your own logger class directly into your SDK.
```python
from cribl import Cribl
import logging

logging.basicConfig(level=logging.DEBUG)
s = Cribl(server_url="https://example.com", debug_logger=logging.getLogger("cribl"))
```

You can also enable a default debug logger by setting an environment variable `CRIBL_DEBUG` to true.
<!-- End Debugging [debug] -->

<!-- Placeholder for Future Speakeasy SDK Sections -->
