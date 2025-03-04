---
description: Configure Azure PowerShell global settings using centralized and granular AzConfig cmdlets
ms.custom: devx-track-azurepowershell
ms.devlang: powershell
ms.service: azure-powershell
ms.topic: conceptual
title: Configure Azure PowerShell global settings
---

# Configure Azure PowerShell global settings

Azure PowerShell offers various global settings, such as the option to disable breaking change
warning messages. Before version 9 of the **Az** PowerShell module, there was no centralized or
detailed method for configuring these global settings.

## Centralized configuration

The **Az** PowerShell module version 9 and higher includes cmdlets for managing the configuration of
global settings for Azure PowerShell. These `*-AzConfig` cmdlets are part of the **Az.Accounts**
PowerShell module:

- [Get-AzConfig][get-azconfig]
- [Update-AzConfig][update-azconfig]
- [Export-AzConfig][export-azconfig]
- [Import-AzConfig][import-azconfig]
- [Clear-AzConfig][clear-azconfig]

## Granular settings

You can apply settings that are effective within a particular scope. The valid values for the
**Scope** parameter are:

- `Current User`: The default scope when applying a setting.
- `Process`: The setting is applied only to the current PowerShell session.
- `Default`: A read-only scope where the default value hasn't changed.
- `Environment`: A read-only scope where the value is configured via an environment variable.

Besides scopes, you can apply settings to all **Az** PowerShell modules or only a single module.
Using the **AppliesTo** parameter, you can specify how broad you want the setting to be applied. The
value `Az` indicates that the setting is applied to all modules that are part of Azure PowerShell.

## Configuration options

There are numerous configuration options that you can set with the `*-AzConfig` cmdlets. Many of
these configuration options are shown in this section. Run the following command to see a complete
list of the Azure PowerShell configuration options you can set with the `*-AzConfig` cmdlets.

```azurepowershell
Get-AzConfig | Format-List
```

### Upgrade notifications

In-tool notifications for Azure PowerShell version upgrades is a feature released in **Az**
PowerShell module version 10.3.0. When a new version of Azure PowerShell is available, an upgrade
notification is displayed in your interactive PowerShell session.

To determine if upgrade notifications are enabled, use the `Get-AzConfig` cmdlet with
the **CheckForUpgrade** parameter, as shown in the following example.

```azurepowershell
Get-AzConfig -CheckForUpgrade
```

To enable upgrade notifications for Azure PowerShell, use the `Update-AzConfig` cmdlet with the
**CheckForUpgrade** parameter and `$true` for its value, as shown in the following example.

```azurepowershell
Update-AzConfig -CheckForUpgrade $true
```

To turn off upgrade notifications, use the `Update-AzConfig` cmdlet with the **CheckForUpgrade**
parameter and `$false` for its value, as shown in the following example.

```azurepowershell
Update-AzConfig -CheckForUpgrade $false
```

### Default subscription

By default, beginning with **Az** PowerShell module version 12.0.0, if you have access to multiple
subscriptions, you're prompted to select an Azure subscription to sign in with.

To prevent being prompted to select a subscription each time you sign in interactively, use the
`Update-AzConfig` cmdlet with the **DefaultSubscriptionForLogin** parameter to set your default
subscription, as shown in the following example.

```azurepowershell
Update-AzConfig -DefaultSubscriptionForLogin <Subscription ID or Name>
```

> [!NOTE]
> Not to be confused with **the subscription of the default context**, the
> **DefaultSubscriptionForLogin** configuration takes effect only when authenticating to Azure.

### Instance discovery

The disable instance discovery setting is designed for situations where the metadata endpoint is
inaccessible, such as in private clouds or Azure Stack environments. Instance discovery involves
retrieving authority metadata from `https://login.microsoft.com/` to validate the authority. By
enabling this setting (setting it to `true`), you disable both instance discovery and authority
validation. Therefore, it's essential to ensure that the configured authority host is valid and
trustworthy.

To disable both instance discovery and authority validation, enable this setting (set it to `true`).

```azurepowershell
Update-AzConfig -DisableInstanceDiscovery $true
```

### Breaking change warning messages

To disable breaking change warning messages for cmdlets in all **Az** modules, use the
`Update-AzConfig` cmdlet with the `DisplayBreakingChangeWarning` parameter, as shown in the
following example:

```azurepowershell
Update-AzConfig -DisplayBreakingChangeWarning $false
```

To disable the breaking change warning message specifically for cmdlets in the **Az.Compute**
module, use the `Update-AzConfig` cmdlet with both the **DisplayBreakingChangeWarning** and
**AppliesTo** parameters as shown in the following example:

```azurepowershell
Update-AzConfig -DisplayBreakingChangeWarning $false -AppliesTo Az.Compute
```

In this scenario, the breaking change warning message remains active for cmdlets in all **Az**
PowerShell modules except **Az.Compute**.

### Azure region identification

Azure customers can choose to deploy resources in several different regions. Sometimes, customers
can reduce costs by selecting nearby regions offering the same services. If a nearby region is
identified, a message displays the region to choose for future deployments.

To disable the region recommendation messages, use the `Update-AzConfig` cmdlet with the
**DisplayRegionIdentified** parameter, as shown in the following example.

```azurepowershell
Update-AzConfig -DisplayRegionIdentified $false
```

For more information about Azure regions, see
[Choose the right Azure region for you][choose-azure-region].

### Display secrets warning

Azure PowerShell displays a warning message by default beginning with version 12.0.0 to help you
protect sensitive information when it identifies a potential secret in the output of a command.

In the following example, the `Update-AzConfig` cmdlet is used to disable the warning message.

```azurepowershell
Update-AzConfig -DisplaySecretsWarning $false
```

### Surveys

When using Azure PowerShell, you might be invited to participate in a survey to tell us about your
experience. While we appreciate the insights this data provides, we understand not everyone wants to
be prompted to complete a survey.

You can disable being prompted to participate in surveys with the `Update-AzConfig` cmdlet, as shown
in the following example.

```azurepowershell
Update-AzConfig -DisplaySurveyMessage $false
```

### Data collection

By default, Azure PowerShell cmdlets send telemetry data to Microsoft to improve the customer
experience. For more information, see our privacy statement: [aka.ms/privacy][privacy].

```azurepowershell
Update-AzConfig -EnableDataCollection $false
```

### Error records

By default, Azure PowerShell error records are written to `$HOME/.Azure/ErrorRecords`.

To disable persistent error records, use the `Update-AzConfig` cmdlet with the
**EnableErrorRecordsPersistence** parameter, as shown in the following example.

```azurepowershell
Update-AzConfig -EnableErrorRecordsPersistence $false
```

### Web Account Manager (WAM)

Beginning with **Az** PowerShell module version 12.0.0, Windows systems use Web Account Manager
(WAM), and Linux and macOS systems use browser-based sign-in by default.

To use browser-based sign-in on Windows 10 and later or on Windows Server 2019 and later with **Az**
12.0.0 and higher, you must disable WAM for use with Azure PowerShell. Use the following command to
disable WAM and return to browser-based sign-in, the default before Az 12.0.0.

```azurepowershell
Update-AzConfig -EnableLoginByWam $false
```

### The new login experience

Beginning with **Az** PowerShell module version 12.0.0, if you have access to multiple
subscriptions, you're prompted to select an Azure subscription to sign in with.

When the new login experience is disabled, and you have access to multiple subscriptions, you're
signed in to the first subscription Azure returns unless you specify a subscription with
`Connect-AzAccount`. Commands run against this subscription by default. This behavior can be
dangerous, for example if the first subscription returned is a production environment.

To disable the new login experience, use the `Update-AzConfig` cmdlet, as shown in the following
example.

```azurepowershell
Update-AzConfig -LoginExperienceV2 Off
```

## Replicating settings

To replicate your settings from one environment to another, you use the `Export-AzConfig` cmdlet to
export the settings to a JSON file.

```azurepowershell
Export-AzConfig -Path $HOME\AzConfig.json
```

To import your settings, use the `Import-AzConfig` cmdlet and reference the previously exported
JSON file.

```azurepowershell
Import-AzConfig -Path $HOME\AzConfig.json
```

## Clearing configuration

To reset the configuration setting of one or more Azure PowerShell global settings to the default,
use the `Clear-AzConfig` cmdlet. In the following example, the **DefaultSubscriptionForLogin**
setting is cleared.

```azurepowershell
Clear-AzConfig -DefaultSubscriptionForLogin
```

<!-- link references -->

[get-azconfig]: /powershell/module/az.accounts/get-azconfig
[update-azconfig]:/powershell/module/az.accounts/update-azconfig
[export-azconfig]: /powershell/module/az.accounts/export-azconfig
[import-azconfig]: /powershell/module/az.accounts/import-azconfig
[clear-azconfig]: /powershell/module/az.accounts/clear-azconfig
[choose-azure-region]: https://azure.microsoft.com/explore/global-infrastructure/geographies/#overview
[privacy]: https://aka.ms/privacy
