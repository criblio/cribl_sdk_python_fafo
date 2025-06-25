# SystemSDK
(*system*)

## Overview

Actions related to system settings

### Available Operations

* [update_changelog_viewed](#update_changelog_viewed) - Update changelog viewed state
* [create_system_distributed_upgrade_cancel_by_group](#create_system_distributed_upgrade_cancel_by_group) - Cancel a running group upgrade
* [create_system_distributed_upgrade_stage_by_group](#create_system_distributed_upgrade_stage_by_group) - Stage distributed group upgrade
* [create_system_distributed_upgrade_by_group](#create_system_distributed_upgrade_by_group) - Execute distributed group upgrade
* [get_system_distributed_upgrade_download_by_file](#get_system_distributed_upgrade_download_by_file) - Get the previously downloaded Cribl package
* [reload_settings](#reload_settings) - Reload Cribl settings from the filesystem
* [trigger_restart](#trigger_restart) - Restart Cribl server
* [get_system_settings_auth](#get_system_settings_auth) - Get authentication settings
* [update_system_settings_auth](#update_system_settings_auth) - Update authentication settings
* [get_system_settings_conf](#get_system_settings_conf) - Get Cribl system settings
* [update_system_settings_conf](#update_system_settings_conf) - Update Cribl system settings
* [get_system_settings_git_settings](#get_system_settings_git_settings) - Get git settings
* [update_system_settings_git_settings](#update_system_settings_git_settings) - Update git settings
* [get_system_settings_search_limits](#get_system_settings_search_limits) - Get search limits
* [~~get_system_settings~~](#get_system_settings) - Get Cribl system settings. Deprecated: use specific endpoints /system/limits, /system/job-limits, /system/redis-cache-limits, /system/services-limits, /system/settings/git-settings, and /system/settings/conf respectively :warning: **Deprecated**
* [~~update_system_settings~~](#update_system_settings) - Update Cribl system settings. Deprecated: use specific endpoints /system/limits, /system/job-limits, /system/settings/git-settings, /system/settings/auth and /system/settings/conf respectively :warning: **Deprecated**
* [get_system_settings_cribl](#get_system_settings_cribl) - Get public settings visible to any logged user
* [get_system_settings_upgrade](#get_system_settings_upgrade) - Get a list of Cribl versions available for upgrade
* [create_system_settings_upgrade_by_version](#create_system_settings_upgrade_by_version) - Upgrade Cribl to a given version
* [create_system_settings_upgrade_from_package](#create_system_settings_upgrade_from_package) - Upgrade master node with the provided package

## update_changelog_viewed

Update changelog viewed state

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

    res = cspf_client.system.update_changelog_viewed()

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.UpdateChangelogViewedResponse](../../models/updatechangelogviewedresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| errors.Error     | 500              | application/json |
| errors.APIError  | 4XX, 5XX         | \*/\*            |

## create_system_distributed_upgrade_cancel_by_group

Cancel a running group upgrade

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

    res = cspf_client.system.create_system_distributed_upgrade_cancel_by_group(group="<value>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `group`                                                             | *str*                                                               | :heavy_check_mark:                                                  | id of the group                                                     |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.CreateSystemDistributedUpgradeCancelByGroupResponse](../../models/createsystemdistributedupgradecancelbygroupresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| errors.Error     | 500              | application/json |
| errors.APIError  | 4XX, 5XX         | \*/\*            |

## create_system_distributed_upgrade_stage_by_group

Stage distributed group upgrade

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

    res = cspf_client.system.create_system_distributed_upgrade_stage_by_group(group="<value>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `group`                                                             | *str*                                                               | :heavy_check_mark:                                                  | Group to upgrade                                                    |
| `upgrade_percentage`                                                | *Optional[str]*                                                     | :heavy_minus_sign:                                                  | body number percentage of nodes on the worker group to upgrade      |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.CreateSystemDistributedUpgradeStageByGroupResponse](../../models/createsystemdistributedupgradestagebygroupresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| errors.Error     | 500              | application/json |
| errors.APIError  | 4XX, 5XX         | \*/\*            |

## create_system_distributed_upgrade_by_group

Execute distributed group upgrade

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

    res = cspf_client.system.create_system_distributed_upgrade_by_group(group="<value>", upgrade_percentage=1, worker_retries=5, worker_retry_delay=1000)

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                                                   | Type                                                                                        | Required                                                                                    | Description                                                                                 |
| ------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------- |
| `group`                                                                                     | *str*                                                                                       | :heavy_check_mark:                                                                          | Group to upgrade                                                                            |
| `package_urls`                                                                              | List[[models.PackageURL](../../models/packageurl.md)]                                       | :heavy_minus_sign:                                                                          | Provide your own URLs or local paths for platform-specific Cribl packages                   |
| `upgrade_percentage`                                                                        | *Optional[float]*                                                                           | :heavy_minus_sign:                                                                          | Percentage of the total worker nodes on the group to run the upgrade on                     |
| `worker_retries`                                                                            | *Optional[float]*                                                                           | :heavy_minus_sign:                                                                          | Number of times to retry conncecting to a worker node before marking the upgrade as failed. |
| `worker_retry_delay`                                                                        | *Optional[float]*                                                                           | :heavy_minus_sign:                                                                          | Delay between retries                                                                       |
| `upgrade_mode`                                                                              | [Optional[models.UpgradeMode]](../../models/upgrademode.md)                                 | :heavy_minus_sign:                                                                          | N/A                                                                                         |
| `version_to`                                                                                | *Optional[str]*                                                                             | :heavy_minus_sign:                                                                          | N/A                                                                                         |
| `retries`                                                                                   | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)                            | :heavy_minus_sign:                                                                          | Configuration to override the default retry behavior of the client.                         |

### Response

**[models.CreateSystemDistributedUpgradeByGroupResponse](../../models/createsystemdistributedupgradebygroupresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| errors.Error     | 500              | application/json |
| errors.APIError  | 4XX, 5XX         | \*/\*            |

## get_system_distributed_upgrade_download_by_file

Get the previously downloaded Cribl package

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

    res = cspf_client.system.get_system_distributed_upgrade_download_by_file(file="<value>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `file`                                                              | *str*                                                               | :heavy_check_mark:                                                  | Name of the file to be downloaded                                   |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.GetSystemDistributedUpgradeDownloadByFileResponse](../../models/getsystemdistributedupgradedownloadbyfileresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| errors.Error     | 500              | application/json |
| errors.APIError  | 4XX, 5XX         | \*/\*            |

## reload_settings

Reload Cribl settings from the filesystem

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

    cspf_client.system.reload_settings()

    # Use the SDK ...

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Errors

| Error Type      | Status Code     | Content Type    |
| --------------- | --------------- | --------------- |
| errors.APIError | 4XX, 5XX        | \*/\*           |

## trigger_restart

Restart Cribl server

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

    cspf_client.system.trigger_restart()

    # Use the SDK ...

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Errors

| Error Type      | Status Code     | Content Type    |
| --------------- | --------------- | --------------- |
| errors.APIError | 4XX, 5XX        | \*/\*           |

## get_system_settings_auth

Get authentication settings

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

    res = cspf_client.system.get_system_settings_auth()

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.GetSystemSettingsAuthResponse](../../models/getsystemsettingsauthresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| errors.Error     | 500              | application/json |
| errors.APIError  | 4XX, 5XX         | \*/\*            |

## update_system_settings_auth

Update authentication settings

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

    res = cspf_client.system.update_system_settings_auth()

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.UpdateSystemSettingsAuthResponse](../../models/updatesystemsettingsauthresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| errors.Error     | 500              | application/json |
| errors.APIError  | 4XX, 5XX         | \*/\*            |

## get_system_settings_conf

Get Cribl system settings

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

    res = cspf_client.system.get_system_settings_conf()

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.GetSystemSettingsConfResponse](../../models/getsystemsettingsconfresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| errors.Error     | 500              | application/json |
| errors.APIError  | 4XX, 5XX         | \*/\*            |

## update_system_settings_conf

Update Cribl system settings

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

    res = cspf_client.system.update_system_settings_conf(api={
        "disabled": True,
        "host": "both-draw.com",
        "port": 3795.06,
        "protocol": "<value>",
        "ssl": {
            "cert_path": "<value>",
            "disabled": False,
            "passphrase": "<value>",
            "priv_key_path": "<value>",
        },
        "worker_remote_access": False,
    }, backups={
        "backup_persistence": "<value>",
        "backups_directory": "<value>",
    }, custom_logo={
        "enabled": False,
        "logo_description": "<value>",
        "logo_image": "<value>",
    }, pii={
        "enable_pii_detection": True,
    }, proxy={
        "use_env_vars": True,
    }, rollback={
        "rollback_enabled": True,
    }, shutdown={
        "drain_timeout": 2424.38,
    }, sni={
        "disable_sni_routing": True,
    }, system={
        "intercom": False,
        "upgrade": models.SystemSettingsConfUpgrade.FALSE,
    }, tls={
        "default_cipher_list": "<value>",
        "default_ecdh_curve": "<value>",
        "max_version": "<value>",
        "min_version": "<value>",
        "reject_unauthorized": True,
    }, upgrade_group_settings={}, upgrade_settings={
        "disable_automatic_upgrade": False,
        "enable_legacy_edge_upgrade": False,
        "upgrade_source": "<value>",
    }, workers={
        "count": 1297.29,
        "memory": 5944.19,
        "minimum": 3174.73,
    })

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                                               | Type                                                                                    | Required                                                                                | Description                                                                             |
| --------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------- |
| `api`                                                                                   | [models.SystemSettingsConfAPI](../../models/systemsettingsconfapi.md)                   | :heavy_check_mark:                                                                      | N/A                                                                                     |
| `backups`                                                                               | [models.SystemSettingsConfBackups](../../models/systemsettingsconfbackups.md)           | :heavy_check_mark:                                                                      | N/A                                                                                     |
| `custom_logo`                                                                           | [models.SystemSettingsConfCustomLogo](../../models/systemsettingsconfcustomlogo.md)     | :heavy_check_mark:                                                                      | N/A                                                                                     |
| `pii`                                                                                   | [models.SystemSettingsConfPii](../../models/systemsettingsconfpii.md)                   | :heavy_check_mark:                                                                      | N/A                                                                                     |
| `proxy`                                                                                 | [models.SystemSettingsConfProxy](../../models/systemsettingsconfproxy.md)               | :heavy_check_mark:                                                                      | N/A                                                                                     |
| `rollback`                                                                              | [models.SystemSettingsConfRollback](../../models/systemsettingsconfrollback.md)         | :heavy_check_mark:                                                                      | N/A                                                                                     |
| `shutdown`                                                                              | [models.SystemSettingsConfShutdown](../../models/systemsettingsconfshutdown.md)         | :heavy_check_mark:                                                                      | N/A                                                                                     |
| `sni`                                                                                   | [models.SystemSettingsConfSni](../../models/systemsettingsconfsni.md)                   | :heavy_check_mark:                                                                      | N/A                                                                                     |
| `system`                                                                                | [models.SystemSettingsConfSystem](../../models/systemsettingsconfsystem.md)             | :heavy_check_mark:                                                                      | N/A                                                                                     |
| `tls`                                                                                   | [models.SystemSettingsConfTLS](../../models/systemsettingsconftls.md)                   | :heavy_check_mark:                                                                      | N/A                                                                                     |
| `upgrade_group_settings`                                                                | [models.UpgradeGroupSettings](../../models/upgradegroupsettings.md)                     | :heavy_check_mark:                                                                      | N/A                                                                                     |
| `upgrade_settings`                                                                      | [models.UpgradeSettings](../../models/upgradesettings.md)                               | :heavy_check_mark:                                                                      | N/A                                                                                     |
| `workers`                                                                               | [models.SystemSettingsConfWorkers](../../models/systemsettingsconfworkers.md)           | :heavy_check_mark:                                                                      | N/A                                                                                     |
| `sockets`                                                                               | [Optional[models.SystemSettingsConfSockets]](../../models/systemsettingsconfsockets.md) | :heavy_minus_sign:                                                                      | N/A                                                                                     |
| `retries`                                                                               | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)                        | :heavy_minus_sign:                                                                      | Configuration to override the default retry behavior of the client.                     |

### Response

**[models.UpdateSystemSettingsConfResponse](../../models/updatesystemsettingsconfresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| errors.Error     | 500              | application/json |
| errors.APIError  | 4XX, 5XX         | \*/\*            |

## get_system_settings_git_settings

Get git settings

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

    res = cspf_client.system.get_system_settings_git_settings()

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.GetSystemSettingsGitSettingsResponse](../../models/getsystemsettingsgitsettingsresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| errors.Error     | 500              | application/json |
| errors.APIError  | 4XX, 5XX         | \*/\*            |

## update_system_settings_git_settings

Update git settings

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

    res = cspf_client.system.update_system_settings_git_settings()

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.UpdateSystemSettingsGitSettingsResponse](../../models/updatesystemsettingsgitsettingsresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| errors.Error     | 500              | application/json |
| errors.APIError  | 4XX, 5XX         | \*/\*            |

## get_system_settings_search_limits

Get search limits

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

    res = cspf_client.system.get_system_settings_search_limits()

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.GetSystemSettingsSearchLimitsResponse](../../models/getsystemsettingssearchlimitsresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| errors.Error     | 500              | application/json |
| errors.APIError  | 4XX, 5XX         | \*/\*            |

## ~~get_system_settings~~

Get Cribl system settings. Deprecated: use specific endpoints /system/limits, /system/job-limits, /system/redis-cache-limits, /system/services-limits, /system/settings/git-settings, and /system/settings/conf respectively

> :warning: **DEPRECATED**: This will be removed in a future release, please migrate away from it as soon as possible.

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

    res = cspf_client.system.get_system_settings()

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.GetSystemSettingsResponse](../../models/getsystemsettingsresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| errors.Error     | 500              | application/json |
| errors.APIError  | 4XX, 5XX         | \*/\*            |

## ~~update_system_settings~~

Update Cribl system settings. Deprecated: use specific endpoints /system/limits, /system/job-limits, /system/settings/git-settings, /system/settings/auth and /system/settings/conf respectively

> :warning: **DEPRECATED**: This will be removed in a future release, please migrate away from it as soon as possible.

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

    res = cspf_client.system.update_system_settings()

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.UpdateSystemSettingsResponse](../../models/updatesystemsettingsresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| errors.Error     | 500              | application/json |
| errors.APIError  | 4XX, 5XX         | \*/\*            |

## get_system_settings_cribl

Get public settings visible to any logged user

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

    res = cspf_client.system.get_system_settings_cribl()

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.GetSystemSettingsCriblResponse](../../models/getsystemsettingscriblresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| errors.Error     | 500              | application/json |
| errors.APIError  | 4XX, 5XX         | \*/\*            |

## get_system_settings_upgrade

Get a list of Cribl versions available for upgrade

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

    res = cspf_client.system.get_system_settings_upgrade()

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.GetSystemSettingsUpgradeResponse](../../models/getsystemsettingsupgraderesponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| errors.Error     | 500              | application/json |
| errors.APIError  | 4XX, 5XX         | \*/\*            |

## create_system_settings_upgrade_by_version

Upgrade Cribl to a given version

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

    res = cspf_client.system.create_system_settings_upgrade_by_version(version="<value>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `version`                                                           | *str*                                                               | :heavy_check_mark:                                                  | Version number                                                      |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.CreateSystemSettingsUpgradeByVersionResponse](../../models/createsystemsettingsupgradebyversionresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| errors.Error     | 500              | application/json |
| errors.APIError  | 4XX, 5XX         | \*/\*            |

## create_system_settings_upgrade_from_package

Upgrade master node with the provided package

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

    res = cspf_client.system.create_system_settings_upgrade_from_package()

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                                 | Type                                                                      | Required                                                                  | Description                                                               |
| ------------------------------------------------------------------------- | ------------------------------------------------------------------------- | ------------------------------------------------------------------------- | ------------------------------------------------------------------------- |
| `packages`                                                                | List[[models.Package](../../models/package.md)]                           | :heavy_minus_sign:                                                        | Provide your own URLs or local paths for platform-specific Cribl packages |
| `retries`                                                                 | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)          | :heavy_minus_sign:                                                        | Configuration to override the default retry behavior of the client.       |

### Response

**[models.CreateSystemSettingsUpgradeFromPackageResponse](../../models/createsystemsettingsupgradefrompackageresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| errors.Error     | 500              | application/json |
| errors.APIError  | 4XX, 5XX         | \*/\*            |