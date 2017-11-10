---
external help file: Microsoft.Azure.Commands.Management.Storage.dll-Help.xml
online version:
schema: 2.0.0
---

# Get-AzureRmStorageUsage

## SYNOPSIS
Gets the storage resource usage for the current subscription.

## SYNTAX

```
Get-AzureRmStorageUsage [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureRmStorageUsage** cmdlet gets the storage resource usage for the current subscription.

## EXAMPLES

### Example 1: Get the storage resource usage
```
PS C:\> Get-AzureRmStorageUsage -InformationAction Ignore
```

This command gets the storage resource usage of the current subscription, ignoring an information event.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### Microsoft.Azure.Commands.Management.Storage.Models.PSUsage

## NOTES

## RELATED LINKS

[Azure Storage Manager Cmdlets](./AzureRM.Storage.md)
