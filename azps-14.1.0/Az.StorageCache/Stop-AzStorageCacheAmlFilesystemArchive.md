---
external help file: Az.StorageCache-help.xml
Module Name: Az.StorageCache
online version: https://learn.microsoft.com/powershell/module/az.storagecache/stop-azstoragecacheamlfilesystemarchive
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/StorageCache/StorageCache/help/Stop-AzStorageCacheAmlFilesystemArchive.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/StorageCache/StorageCache/help/Stop-AzStorageCacheAmlFilesystemArchive.md
---

# Stop-AzStorageCacheAmlFilesystemArchive

## SYNOPSIS
Cancel archiving data from the AML file system.

## SYNTAX

### Cancel (Default)
```
Stop-AzStorageCacheAmlFilesystemArchive -AmlFilesystemName <String> -ResourceGroupName <String>
 [-SubscriptionId <String>] [-DefaultProfile <PSObject>] [-PassThru]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### CancelViaIdentity
```
Stop-AzStorageCacheAmlFilesystemArchive -InputObject <IStorageCacheIdentity> [-DefaultProfile <PSObject>]
 [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cancel archiving data from the AML file system.

## EXAMPLES

### Example 1: Cancel archiving data from the AML file system.
```powershell
Stop-AzStorageCacheAmlFilesystemArchive -AmlFilesystemName azps-cache-fs -ResourceGroupName azps_test_gp_storagecache -PassThru
```

```output
True
```

Cancel archiving data from the AML file system.

## PARAMETERS

### -AmlFilesystemName
Name for the AML file system.
Allows alphanumerics, underscores, and hyphens.
Start and end with alphanumeric.

```yaml
Type: System.String
Parameter Sets: Cancel
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DefaultProfile
The DefaultProfile parameter is not functional.
Use the SubscriptionId parameter when available if executing the cmdlet against a different subscription.

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

### -InputObject
Identity Parameter

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.StorageCache.Models.IStorageCacheIdentity
Parameter Sets: CancelViaIdentity
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -PassThru
Returns true when the command succeeds

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
The name of the resource group.
The name is case insensitive.

```yaml
Type: System.String
Parameter Sets: Cancel
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubscriptionId
The ID of the target subscription.

```yaml
Type: System.String
Parameter Sets: Cancel
Aliases:

Required: False
Position: Named
Default value: (Get-AzContext).Subscription.Id
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

### Microsoft.Azure.PowerShell.Cmdlets.StorageCache.Models.IStorageCacheIdentity

## OUTPUTS

### System.Boolean

## NOTES

## RELATED LINKS
