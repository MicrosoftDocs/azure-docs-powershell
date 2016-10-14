---
external help file: Microsoft.Azure.Commands.Management.Storage.dll-Help.xml
online version: e33b0d60-c851-4bc5-b2b3-6d151590a796
schema: 2.0.0
---

# Get-AzureRmStorageUsage

## SYNOPSIS
Gets the Storage resource usage of the current subscription.

## SYNTAX

```
Get-AzureRmStorageUsage [-InformationAction <ActionPreference>] [-InformationVariable <String>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureRmStorageUsage** cmdlet gets the resource usage for Azure Storage for the current subscription.

## EXAMPLES

### Example 1: Get the storage resources usage
```
PS C:\>Get-AzureRmStorageUsage
```

This command gets the Storage resources usage of the current subscription.

## PARAMETERS

### -InformationAction
@{Text=}```yaml
Type: ActionPreference
Parameter Sets: (All)
Aliases: infa

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InformationVariable
@{Text=}```yaml
Type: String
Parameter Sets: (All)
Aliases: iv

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Azure Storage Manager Cmdlets](.\AzureRM.Storage.md)

