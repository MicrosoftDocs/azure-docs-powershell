---
external help file: Microsoft.AzureStack.AzureConsistentStorage.Commands.dll-Help.xml
online version: 
schema: 2.0.0
---

# Undo-ACSStorageAccountDeletion

## SYNOPSIS
Undeletes a tenant storage account.

## SYNTAX

```
Undo-ACSStorageAccountDeletion [-ResourceGroupName] <String> [-FarmName] <String> [-AccountId] <String>
 [[-NewAccountName] <String>] [[-StorageAccountApiVersion] <String>] [-ResourceAdminApiVersion <String>]
 [[-SubscriptionId] <String>] [[-Token] <String>] [[-AdminUri] <Uri>] [-SkipCertificateValidation]
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Undo-ACSStorageAccountDeletion** cmdlet undeletes a tenant storage account. 
The service administrator can use this cmdlet to recover a storage account deleted by a tenant administrator.

## EXAMPLES

### Example 1: Recover a storage account

```
PS C:\> $ResourceGroup = "System" 

PS C:\> $Farm = Get-ACSFarm -ResourceGroupName $ResourceGroup

PS C:\> Undo-ACSStorageAccountDeletion -ResourceGroupName $ResourceGroup -FarmName $Farm.Name -AccountId <AccountId>
```

The first command stores the value named System in the variable named $ResourceGroup.

The second command uses the [Get-ACSFarm](./Get-ACSFarm.md) cmdlet to get the farm that is contained in the resource group specified in the $ResourceGroup variable. 
The command stores the result in the variable named $Farm.

The third command uses the **Undo-ACSStorageAccountDeletion** cmdlet to restore the storage account for the specified in the *AccountID* parameter.

## PARAMETERS

### -AccountId
Specifies the account ID in which this cmdlet recovers the storage account.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 5
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -AdminUri
Specifies the link, as a URI, to the service administrator.

```yaml
Type: Uri
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -FarmName
Specifies the name of the Azure Consistent Storage (ACS) farm.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 4
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InformationAction
Specifies how this cmdlet responds to an information event.

The acceptable values for this parameter are:

- Continue
- Ignore
- Inquire
- SilentlyContinue
- Stop
- Suspend

```yaml
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
Specifies an information variable.

```yaml
Type: String
Parameter Sets: (All)
Aliases: iv

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
Position: 6
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceAdminApiVersion
API version of Resource.Admin.

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

### -ResourceGroupName
Specifies the name of the resource group that contains the ACS farm.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
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
Position: 7
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubscriptionId
Specifies the subscription ID.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Token


```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### Microsoft.AzureStack.AzureConsistentStorage.Commands.FarmResponse

### Microsoft.AzureStack.AzureConsistentStorage.Commands.StorageAccountResponse

## OUTPUTS

## NOTES

## RELATED LINKS

[Clear-ACSStorageAccount](./Clear-ACSStorageAccount.md)

[Get-ACSStorageAccount](./Get-ACSStorageAccount.md)

[Set-ACSStorageAccount](./Set-ACSStorageAccount.md)

[Get-ACSFarm](./Get-ACSFarm.md)
