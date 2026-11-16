---
document type: cmdlet
external help file: Microsoft.Azure.Azclips.Cmdlets.Resources.dll-Help.xml
HelpUri: ''
Locale: en-US
Module Name: Az.Resources
ms.date: 11/04/2026
PlatyPS schema version: 2024-05-01
title: Stop-AzTenantDeployment
---

# Stop-AzTenantDeployment

## SYNOPSIS

Cancel a running deployment at tenant scope.

## SYNTAX

### Default (Default)

```
Stop-AzTenantDeployment [-Name] <string> [-Profile <string>] [<CommonParameters>]
```

## ALIASES

This cmdlet has no aliases.

## DESCRIPTION

Cancels a tenant deployment whose provisioning state is `Accepted` or `Running`. Resources the
deployment already created are left in place. Azure Resource Manager rejects the request, and
the cmdlet raises an error, when the deployment is no longer running.

## EXAMPLES

### Cancel a running deployment

```powershell
Stop-AzTenantDeployment -Name tenant-infra
```

## PARAMETERS

### -Name

The name of the deployment.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases:
- DeploymentName
ParameterSets:
- Name: (All)
  Position: 0
  IsRequired: true
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -Profile

Name of a saved profile to use for this call instead of the currently-active one. Manage profiles with `Set-AzProfile` / `Get-AzProfile`.

```yaml
Type: System.String
DefaultValue: ''
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
HelpMessage: ''
```

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutBuffer, -OutVariable, -PipelineVariable,
-ProgressAction, -Verbose, -WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

This cmdlet does not accept pipeline input.

## OUTPUTS

### System.Void

This cmdlet produces no output.

## NOTES

Differences from Az.Resources: the cmdlet sends the cancel request directly and reports the service error when the deployment is not running, instead of checking its state first. `-Id`, `-InputObject`, `-PassThru`, `-WhatIf`, `-Confirm`, and `-Pre` are not supported.

## RELATED LINKS

- [Get-AzTenantDeployment](Get-AzTenantDeployment.md)
- [Remove-AzTenantDeployment](Remove-AzTenantDeployment.md)
