---
external help file: Az.ServiceLinker-help.xml
Module Name: Az.ServiceLinker
online version: https://learn.microsoft.com/powershell/module/az.servicelinker/get-azservicelinkerconfigurationforwebapp
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ServiceLinker/ServiceLinker/help/Get-AzServiceLinkerConfigurationForWebApp.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ServiceLinker/ServiceLinker/help/Get-AzServiceLinkerConfigurationForWebApp.md
---

# Get-AzServiceLinkerConfigurationForWebApp

## SYNOPSIS
list source configurations for a linker in webapp.

## SYNTAX

```
Get-AzServiceLinkerConfigurationForWebApp -LinkerName <String> [-ResourceUri <String>]
 [-DefaultProfile <PSObject>] -WebApp <String> -ResourceGroupName <String> [-SubscriptionId <String>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
list source configurations for a linker in webapp.

## EXAMPLES

### Example 1: Get webapp's linker configuration list
```powershell
Get-AzServiceLinkerConfigurationForWebApp -WebApp servicelinker-webapp -ResourceGroupName servicelinker-test-group -LinkerName postgresql_linker | Format-List
```

```output
Name  : AZURE_POSTGRESQL_POSTGRESQL_NOVNET_CONNECTIONSTRING
Value : Server=test.postgres.database.azure.com;Database=testdb;Port=543 
        2;Ssl Mode=Require;User Id=testuser@test;Password=password;
```

Get Linker's configuration list

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

### -LinkerName
The name Linker resource.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
The resource group of the resource to be connected.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceUri
The fully qualified Azure Resource manager identifier of the resource to be connected.

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

### -SubscriptionId
Gets subscription ID which uniquely identify the Microsoft Azure subscription.
The subscription ID forms part of the URI for every service call.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: (Get-AzContext).Subscription.Id
Accept pipeline input: False
Accept wildcard characters: False
```

### -WebApp
The Name of webapp of the resource to be connected.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

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

### Microsoft.Azure.PowerShell.Cmdlets.ServiceLinker.Models.ISourceConfiguration

## NOTES

## RELATED LINKS
