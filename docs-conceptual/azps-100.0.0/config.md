---
title: Configuration management
description: Learn how to manage Azure PowerShell preview configuration settings, including keys, environment variables, and file locations.
---

# Configuration management

Azure PowerShell preview stores user-scope configuration in a global JSON file.

Configuration follows strict precedence: **command args > environment variables > global config > defaults**.

## Valid Configuration Keys

| Key                                           | Type   | Default            | Notes                                                                                                                                                                                                                                                                   |
| --------------------------------------------- | ------ | ------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `core.logging.level`                          | string | `warn`             | Log level: `debug`, `info`, `warn`, `error`. Diagnostics (`warn`/`info`/`verbose`/`debug`) are written to **stderr**; command results stay on stdout.                                                                                                                   |
| `core.http.maxRetries`                        | int    | `3`                | Max HTTP request retries                                                                                                                                                                                                                                                |
| `core.http.maxRetriesFor429`                  | int    | `5`                | Max retries for 429 (rate limit) responses                                                                                                                                                                                                                              |
| `core.engine.extensionIndexCacheSize`         | int    | `512`              | LFU cache capacity for extension index (entry count)                                                                                                                                                                                                                    |
| `assemblyLoading.versionedInstallationDir`    | string | (system)           | Versioned assembly installation directory                                                                                                                                                                                                                               |
| `assemblyLoading.builtinInstallationDir`      | string | (system)           | Built-in assembly directory                                                                                                                                                                                                                                             |
| `assemblyLoading.extensionFolderPrefix`       | string | (see notes)        | Extension assembly folder prefix; `Microsoft.Azure.Azclips.Extensions.` (DEBUG), empty (Release)                                                                                                                                                                        |
| `telemetry.enabled`                           | bool   | `true`             | Enable telemetry                                                                                                                                                                                                                                                        |
| `extensions.resources.arm.apiVersionOverride` | string | (empty)            | Override ARM API version                                                                                                                                                                                                                                                |
| `clients.powershell.output.format`            | string | `object`           | PowerShell output format: `object`, `json`, `table`                                                                                                                                                                                                                     |
| `defaults.group`                              | string | (empty)            | Default resource group                                                                                                                                                                                                                                                  |
| `defaults.location`                           | string | (empty)            | Default location                                                                                                                                                                                                                                                        |
| `defaults.web`                                | string | (empty)            | Default web app name                                                                                                                                                                                                                                                    |
| `defaults.vm`                                 | string | (empty)            | Default VM name                                                                                                                                                                                                                                                         |
| `defaults.vmss`                               | string | (empty)            | Default VMSS name                                                                                                                                                                                                                                                       |
| `defaults.acr`                                | string | (empty)            | Default ACR name                                                                                                                                                                                                                                                        |

## PowerShell Usage

### Import the Config module

```powershell
Import-Module ./src/PS/Config/Config.psd1
```

### Get configuration values or sections

```powershell
Get-AzConfig -Key core.logging.level
# Output: core.logging.level = warn [default]

Get-AzConfig -Key core.logging.level -AsJson
# Output: {"Key":"core.logging.level","Value":"warn","Source":"default"}

# Retrieve a section (text output)
Get-AzConfig -Key core

# Retrieve a subsection as JSON
Get-AzConfig -Key core.logging -AsJson
# Output: {"level":"warn"}

# Retrieve a section as nested JSON
Get-AzConfig -Key core -AsJson
```

### Set a configuration value

```powershell
# Set a key (will prompt for confirmation)
Set-AzConfig -Key core.logging.level -Value debug

# Set with force (allows unknown keys)
Set-AzConfig -Key core.logging.level -Value debug -Force
```

### List all configuration

```powershell
# List user config only
Get-AzConfigList

# List with defaults
Get-AzConfigList -IncludeDefaults

# Output as JSON
Get-AzConfigList -IncludeDefaults -AsJson
```

### Delete a configuration value

```powershell
# Delete a key (will prompt for confirmation)
Remove-AzConfig -Key core.logging.level

# Delete with force (allows unknown keys)
Remove-AzConfig -Key core.logging.level -Force
```

### View schema information

```powershell
# List all valid configuration keys
Get-AzConfigInfo

# Output only key names
Get-AzConfigInfo -KeysOnly
```

## Environment Variable Mappings

You can override configuration using environment variables:

| Environment Variable                                                | Maps to                      |
| ------------------------------------------------------------------- | ---------------------------- |
| `PS_HTTP_MAX_RETRIES` / `AZURE_PS_HTTP_MAX_RETRIES`                 | `core.http.maxRetries`       |
| `PS_HTTP_MAX_RETRIES_FOR_429` / `AZURE_PS_HTTP_MAX_RETRIES_FOR_429` | `core.http.maxRetriesFor429` |

## Configuration File Location

Configuration is stored at:

- **Windows**: `%USERPROFILE%\.azclips\config.json`
- **Linux/macOS**: `$HOME/.azclips/config.json`

## Examples

### Workflow: Enable debug logging

```powershell
Set-AzConfig -Key core.logging.level -Value debug -Force
Get-AzConfig -Key core.logging.level
```

### Workflow: Check all settings with defaults

```powershell
Get-AzConfigList -IncludeDefaults
```

### Workflow: Reset to defaults

```powershell
Get-AzConfigList | Where-Object { $_ -notmatch '\[default\]' } | ForEach-Object {
  $key = ($_ -split ' = ')[0]
  Remove-AzConfig -Key $key -Force
}
```
