---
document type: cmdlet
external help file: Microsoft.Azure.Azclips.Cmdlets.Storage.dll-Help.xml
HelpUri: ''
Locale: en-US
Module Name: Az.Storage
ms.date: 10/13/2026
PlatyPS schema version: 2024-05-01
title: Get-AzStorageAccount
---

# Get-AzStorageAccount

## SYNOPSIS

Get one or more Azure Storage accounts.

## SYNTAX

### ResourceGroup (Default)

```
Get-AzStorageAccount [[-ResourceGroupName] <string>] [-SubscriptionId <string>] [-Profile <string>]
 [<CommonParameters>]
```

### AccountName

```
Get-AzStorageAccount [-ResourceGroupName] <string> [-Name] <string> [-IncludeGeoReplicationStats]
 [-SubscriptionId <string>] [-Profile <string>] [<CommonParameters>]
```

## ALIASES

## DESCRIPTION

Gets Azure Storage accounts.
Supply -Name together with -ResourceGroupName to get a single account, supply only -ResourceGroupName to list the accounts in that resource group, or supply neither to list every storage account in the subscription.
Paged responses from the service are followed automatically, so listing returns the complete set.

## EXAMPLES

### Example 1: Get a single storage account

```powershell
Get-AzStorageAccount -ResourceGroupName myResourceGroup -Name mystorageaccount
```

### Example 2: List the storage accounts in a resource group

```powershell
Get-AzStorageAccount -ResourceGroupName myResourceGroup
```

### Example 3: List every storage account in the subscription

```powershell
Get-AzStorageAccount
```

### Example 4: Include geo-replication statistics

```powershell
Get-AzStorageAccount -ResourceGroupName myResourceGroup -Name mystorageaccount -IncludeGeoReplicationStats
```

## PARAMETERS

### -IncludeGeoReplicationStats

Include geo-replication statistics in the returned account, reporting the replication state and whether the account can fail over.

```yaml
Type: System.Management.Automation.SwitchParameter
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: AccountName
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -Name

The name of the storage account to get.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases:
- StorageAccountName
- AccountName
ParameterSets:
- Name: AccountName
  Position: 1
  IsRequired: true
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: true
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -Profile

Use the named profile for this command, overriding the active profile.

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

### -ResourceGroupName

The resource group name. Omit to list every storage account in the subscription.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: AccountName
  Position: 0
  IsRequired: true
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: true
  ValueFromRemainingArguments: false
- Name: ResourceGroup
  Position: 0
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: true
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -SubscriptionId

Azure Subscription Id. Defaults to the subscription of the active profile.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: AccountName
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
- Name: ResourceGroup
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

### System.String

You can pipe a resource group name and storage account name to this cmdlet by property name.

## OUTPUTS

### Microsoft.Azure.Azclips.Extensions.Storage.Models.StorageAccount

Gets Azure Storage accounts, either a single account by name or all accounts in a resource group or subscription.

## NOTES

## RELATED LINKS

- [Online Version]()

