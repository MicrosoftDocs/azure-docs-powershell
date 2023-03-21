---
external help file: 
Module Name: Az.ServiceLinker
online version: https://learn.microsoft.com/powershell/module/az.servicelinker/get-azservicelinkerconfigurationname
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ServiceLinker/help/Get-AzServiceLinkerConfigurationName.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ServiceLinker/help/Get-AzServiceLinkerConfigurationName.md
---

# Get-AzServiceLinkerConfigurationName

## SYNOPSIS
Lists the configuration names generated by Service Connector for all target, client types, auth types.

## SYNTAX

```
Get-AzServiceLinkerConfigurationName [-Filter <String>] [-SkipToken <String>] [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

## DESCRIPTION
Lists the configuration names generated by Service Connector for all target, client types, auth types.

## EXAMPLES

### Example 1: Get expected configuration names of difference connection
```powershell
Get-AzServiceLinkerConfigurationName
```

```output
systemAssignedIdentity none                    {Microsoft.Azure.PowerShell.Cmdlets.ServiceLinker.Models.Api20221101Preview.Config…
userAssignedIdentity   none                    {Microsoft.Azure.PowerShell.Cmdlets.ServiceLinker.Models.Api20221101Preview.Config…
servicePrincipalSecret none                    {Microsoft.Azure.PowerShell.Cmdlets.ServiceLinker.Models.Api20221101Preview.Config…
secret                 none                    {Microsoft.Azure.PowerShell.Cmdlets.ServiceLinker.Models.Api20221101Preview.Config…
accessKey              none                    {Microsoft.Azure.PowerShell.Cmdlets.ServiceLinker.Models.Api20221101Preview.Config…
```

Get the expected configuration names of connection with each auth type and client type.

## PARAMETERS

### -DefaultProfile
The credentials, account, tenant, and subscription used for communication with Azure.

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases: AzureRMContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Filter
OData filter options.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SkipToken
OData skipToken option for pagination.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.ServiceLinker.Models.Api20221101Preview.IConfigurationNameItem

## NOTES

ALIASES

## RELATED LINKS
