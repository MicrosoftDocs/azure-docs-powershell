---
external help file: Microsoft.AzureStack.AzureConsistentStorage.Commands.dll-Help.xml
Module Name: AzureRM.AzureStackStorage
online version: 
schema: 2.0.0
---

# Undo-AzsDeletedStorageAccount

## SYNOPSIS
Tries to recover a deleted storage account.

## SYNTAX

```
Undo-AzsDeletedStorageAccount -AccountId <String> [-NewAccountName <String>]
 [-StorageAccountApiVersion <String>] [-ResourceAdminApiVersion <String>] [-SkipCertificateValidation]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Undo-AzsDeletedStorageAccount** cmdlet tries to recover a deleted storage account. The cloud administrator can use this cmdlet to recover a storage account deleted by a user.

## EXAMPLES

### Example 1
```
$DeletedStorageAccounts = Get-AzsStorageAccount -StorageAccountStatus Deleted 

$AccountIdToRecover = foreach ($StorageAccount in $DeletedStorageAccounts) { if($StorageAccount.StorageAccountName.Equals("teststo")) {$StorageAccount.AccountId} }

Undo-AzsDeletedStorageAccount -AccountId $AccountIdToRecover
```

## PARAMETERS

### -AccountId
Specifies the account ID in which this cmdlet recovers the storage account.

```yaml
Type: String
Parameter Sets: (All)
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

### -NewAccountName
Specifies the new account name of the storage account.
```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceAdminApiVersion
API version of the Resource.Admin namespace.

```yaml
Type: String
Parameter Sets: (All)
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

### -StorageAccountApiVersion
Specifies the API version of the storage account for which this cmdlet recovers.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
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
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

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

[Get-AzsStorageAccount](./Get-AzsStorageAccount.md)

[Get-AzsStorageFarm](./Get-AzsStorageFarm.md)


