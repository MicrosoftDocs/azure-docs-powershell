---
document type: cmdlet
external help file: Microsoft.Azure.Azclips.Cmdlets.Login.dll-Help.xml
HelpUri: ""
Locale: en-US
Module Name: Login
ms.date: 08/06/2026
PlatyPS schema version: 2024-05-01
title: Connect-AzAccount
---

# Connect-AzAccount

## SYNOPSIS

Authenticate to Azure.

## SYNTAX

### \_\_AllParameterSets

```
Connect-AzAccount [-SubscriptionId <string>] [-TenantId <string>] [-UseDeviceCode]
 [-OutProfile <string>] [-Profile <string>] [-Identity] [-ClientId <string>] [-ObjectId <string>]
 [-ResourceId <string>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## ALIASES

## DESCRIPTION

Authenticate to Azure and persist account context for subsequent commands.

## EXAMPLES

### Sign in with the default browser flow

Launches the interactive browser sign-in experience and persists the resulting account context for the specified subscription. Use this on a workstation with a default browser available.

```powershell
Connect-AzAccount -SubscriptionId '00000000-0000-0000-0000-000000000000' -TenantId '11111111-1111-1111-1111-111111111111'
```

### Sign in with device code on a host without a browser

Uses the device-code authentication flow — prints a code and verification URL to the console so you can complete the sign-in from another device. Useful for SSH sessions, containers, and headless build agents.

```powershell
Connect-AzAccount -SubscriptionId '00000000-0000-0000-0000-000000000000' -TenantId '11111111-1111-1111-1111-111111111111' -UseDeviceCode
```

## PARAMETERS

### -ClientId

Client ID of the user-assigned managed identity to authenticate as. Use with `-Identity`. Mutually exclusive with `-ObjectId` and `-ResourceId`.

```yaml
Type: System.String
DefaultValue: ""
SupportsWildcards: false
Aliases: []
ParameterSets:
    - Name: (All)
      Position: Named
      IsRequired: false
      ValueFromPipeline: false
      ValueFromPipelineByPropertyName: false
      ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ""
```

### -Confirm

Prompts you for confirmation before running the cmdlet.

```yaml
Type: System.Management.Automation.SwitchParameter
DefaultValue: ""
SupportsWildcards: false
Aliases:
    - cf
ParameterSets:
    - Name: (All)
      Position: Named
      IsRequired: false
      ValueFromPipeline: false
      ValueFromPipelineByPropertyName: false
      ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ""
```

### -Identity

Sign in using a managed identity. System-assigned by default; combine with `-ClientId`, `-ObjectId`, or `-ResourceId` to select a specific user-assigned identity.

```yaml
Type: System.Management.Automation.SwitchParameter
DefaultValue: ""
SupportsWildcards: false
Aliases:
    - MSI
    - ManagedIdentity
ParameterSets:
    - Name: (All)
      Position: Named
      IsRequired: false
      ValueFromPipeline: false
      ValueFromPipelineByPropertyName: false
      ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ""
```

### -ObjectId

Object (principal) ID of the user-assigned managed identity. Use with `-Identity`. Mutually exclusive with `-ClientId` and `-ResourceId`.

```yaml
Type: System.String
DefaultValue: ""
SupportsWildcards: false
Aliases: []
ParameterSets:
    - Name: (All)
      Position: Named
      IsRequired: false
      ValueFromPipeline: false
      ValueFromPipelineByPropertyName: false
      ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ""
```

### -OutProfile

Name of a new named profile in which to persist the sign-in context. Use `-Profile <name>` on subsequent invocations to switch back to it. Mutually exclusive with `-Profile`.

```yaml
Type: System.String
DefaultValue: ""
SupportsWildcards: false
Aliases: []
ParameterSets:
    - Name: (All)
      Position: Named
      IsRequired: false
      ValueFromPipeline: false
      ValueFromPipelineByPropertyName: false
      ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ""
```

### -Profile

Name of an existing named profile to sign into. Mutually exclusive with `-OutProfile`.

```yaml
Type: System.String
DefaultValue: ""
SupportsWildcards: false
Aliases: []
ParameterSets:
    - Name: (All)
      Position: Named
      IsRequired: false
      ValueFromPipeline: false
      ValueFromPipelineByPropertyName: false
      ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ""
```

### -ResourceId

Full ARM resource ID of the user-assigned managed identity (`/subscriptions/.../resourceGroups/.../providers/Microsoft.ManagedIdentity/userAssignedIdentities/<name>`). Use with `-Identity`. Mutually exclusive with `-ClientId` and `-ObjectId`.

```yaml
Type: System.String
DefaultValue: ""
SupportsWildcards: false
Aliases: []
ParameterSets:
    - Name: (All)
      Position: Named
      IsRequired: false
      ValueFromPipeline: false
      ValueFromPipelineByPropertyName: false
      ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ""
```

### -SubscriptionId

Azure Subscription Id.

```yaml
Type: System.String
DefaultValue: ""
SupportsWildcards: false
Aliases: []
ParameterSets:
    - Name: (All)
      Position: Named
      IsRequired: false
      ValueFromPipeline: false
      ValueFromPipelineByPropertyName: false
      ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ""
```

### -TenantId

Tenant ID to login to.

```yaml
Type: System.String
DefaultValue: ""
SupportsWildcards: false
Aliases: []
ParameterSets:
    - Name: (All)
      Position: Named
      IsRequired: false
      ValueFromPipeline: false
      ValueFromPipelineByPropertyName: false
      ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ""
```

### -UseDeviceCode

Use device code flow for authentication.

```yaml
Type: System.Management.Automation.SwitchParameter
DefaultValue: ""
SupportsWildcards: false
Aliases: []
ParameterSets:
    - Name: (All)
      Position: Named
      IsRequired: false
      ValueFromPipeline: false
      ValueFromPipelineByPropertyName: false
      ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ""
```

### -WhatIf

Shows what would happen if the cmdlet runs.
The cmdlet is not run.
Runs the command in a mode that only reports what would happen without performing the actions.
Runs the command in a mode that only reports what would happen without performing the actions.

```yaml
Type: System.Management.Automation.SwitchParameter
DefaultValue: ""
SupportsWildcards: false
Aliases:
    - wi
ParameterSets:
    - Name: (All)
      Position: Named
      IsRequired: false
      ValueFromPipeline: false
      ValueFromPipelineByPropertyName: false
      ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ""
```

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutBuffer, -OutVariable, -PipelineVariable,
-ProgressAction, -Verbose, -WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Core.Abstractions.Profile

The activated profile object (name, tenant ID, subscription ID, cloud, authentication method) after successful sign-in. Also persisted to the on-disk profile store; use `Get-AzProfile` later to enumerate saved profiles.

## NOTES

Generated help for login.

## RELATED LINKS

- [Online Version]()
