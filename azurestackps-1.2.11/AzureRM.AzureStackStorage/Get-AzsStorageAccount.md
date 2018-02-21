---
external help file: Microsoft.AzureStack.AzureConsistentStorage.Commands.dll-Help.xml
Module Name: AzureRM.AzureStackStorage
online version: 
schema: 2.0.0
---

# Get-AzsStorageAccount

## SYNOPSIS
Gets a list of all storage accounts and their properties in a region.

## SYNTAX

### ListMultipleAccounts (Default)
```
Get-AzsStorageAccount [-TenantSubscriptionId <String>] [-PartialAccountName <String>]
 [-StorageAccountStatus <StorageAccountStatus>] [-Detail] [-SkipCertificateValidation]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### GetSingleAccount
```
Get-AzsStorageAccount -AccountId <String> [-Detail] [-SkipCertificateValidation]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzsStorageAccount** cmdlet gets a list of all storage accounts and their properties in a region.

## EXAMPLES

### Example 1
```
Get-AzsStorageAccount -TenantSubscriptionId 0a2d6a84-d4d3-4b48-9c93-5ce0113cf115
```

This command gets storage accounts and their properties for the specified tenant Id.

## PARAMETERS

### -AccountId
Specifies the Account ID that the cmdlet uses to get the storage account.

```yaml
Type: String
Parameter Sets: GetSingleAccount
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DefaultProfile
The credentials, account, tenant, and subscription used for communication with azure.

```yaml
Type: IAzureContextContainer
Parameter Sets: (All)
Aliases: AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Detail
Specifies the Account ID that the cmdlet uses to get the storage account.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PartialAccountName
Specifies a partial account name that the cmdlet uses to search for storage accounts.

```yaml
Type: String
Parameter Sets: ListMultipleAccounts
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SkipCertificateValidation
Indicates that the cmdlet does not validate the certificate.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StorageAccountStatus
Specifies the status of the storage account that this cmdlet gets.

```yaml
Type: StorageAccountStatus
Parameter Sets: ListMultipleAccounts
Aliases: 
Accepted values: Active, Deleted, OutOfRetentionPeriod, Recycled

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TenantSubscriptionId
Specifies the tenant subscription ID that this cmdlet uses to get the storage account.

```yaml
Type: String
Parameter Sets: ListMultipleAccounts
Aliases: 

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

[Undo-AzsDeletedStorageAccount](./Undo-AzsDeletedStorageAccount.md)

[Get-AzsStorageFarm](./Get-AzsStorageFarm.md)

