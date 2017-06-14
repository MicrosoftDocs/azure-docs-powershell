---
external help file: Microsoft.AzureStack.AzureConsistentStorage.Commands.dll-Help.xml
online version: 
schema: 2.0.0
---

# Get-ACSStorageAccount

## SYNOPSIS
Gets a list of the tenant storage accounts based on the tenant subscription ID, account name, account status, or an account ID.

## SYNTAX

### ListMultipleAccounts (Default)
```
Get-ACSStorageAccount [-ResourceGroupName] <String> [-FarmName] <String> [[-TenantSubscriptionId] <String>]
 [[-PartialAccountName] <String>] [[-StorageAccountStatus] <Int32>] [-Detail] [[-SubscriptionId] <String>]
 [[-Token] <String>] [[-AdminUri] <Uri>] [-SkipCertificateValidation] [-InformationAction <ActionPreference>]
 [-InformationVariable <String>] [<CommonParameters>]
```

### GetSingleAccount
```
Get-ACSStorageAccount [-ResourceGroupName] <String> [-FarmName] <String> [-AccountId] <String> [-Detail]
 [[-SubscriptionId] <String>] [[-Token] <String>] [[-AdminUri] <Uri>] [-SkipCertificateValidation]
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-ACSStorageAccount** cmdlet gets a list of the tenant storage accounts based on the tenant subscription ID, account name (or part of the account name) ,account status, account ID.

## EXAMPLES

### Example 1: Get a list of tenant storage account
```
$ResourceGroup = "System" 

$Farm = Get-ACSFarm -ResourceGroupName $ResourceGroup

Get-ACSStorageAccount -ResourceGroupName $ResourceGroup -FarmName $Farm.Name -PartialAccountName "Account002"
```

The first command stores the value named System in the variable named $ResourceGroup.

The second command uses the [Get-ACSFarm](./Get-ACSFarm.md) cmdlet to get the farm that is contained in the resource group specified in the $ResourceGroup variable. 
The command stores the result in the variable named $Farm.

The third command uses the **Get-ACSStorageAccount** cmdlet to get the storage account named Account002.

## PARAMETERS

### -AccountId
Specifies the Account ID that the cmdlet uses to get the storage account.

```yaml
Type: String
Parameter Sets: GetSingleAccount
Aliases: 

Required: True
Position: 8
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

### -Detail


```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: 9
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FarmName
Specifies the name of the ACS farm that this cmdlet gets the storage account from.

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

### -PartialAccountName
Specifies a partial account name that the cmdlet uses to search for storage accounts.

```yaml
Type: String
Parameter Sets: ListMultipleAccounts
Aliases: 

Required: False
Position: 6
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Specifies the resource group 

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

### -StorageAccountStatus
Specifies the status of the storage account that this cmdlet gets.

```yaml
Type: Int32
Parameter Sets: ListMultipleAccounts
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

### -TenantSubscriptionId
Specifies the tenant subscription ID that this cmdlet uses to get the storage account.

```yaml
Type: String
Parameter Sets: ListMultipleAccounts
Aliases: 

Required: False
Position: 5
Default value: None
Accept pipeline input: False
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.AzureStack.AzureConsistentStorage.Commands.FarmResponse

## OUTPUTS

### Microsoft.AzureStack.AzureConsistentStorage.Commands.StorageAccountResponse

## NOTES

## RELATED LINKS

[Clear-ACSStorageAccount](./Clear-ACSStorageAccount.md)

[Sync-ACSStorageAccount](./Sync-ACSStorageAccount.md)
