---
external help file: Microsoft.Azure.Commands.DataLakeStore.dll-Help.xml
online version: .\New-AzureRmDataLakeStoreAccount.md
schema: 2.0.0
---

# Get-AzureRmDataLakeStoreAccount

## SYNOPSIS
Gets details of a Data Lake Store account.

## SYNTAX

### All In Subscription (Default)
```
Get-AzureRmDataLakeStoreAccount [-InformationAction <ActionPreference>] [-InformationVariable <String>]
 [<CommonParameters>]
```

### All In Resource Group
```
Get-AzureRmDataLakeStoreAccount [-ResourceGroupName] <String> [-InformationAction <ActionPreference>]
 [-InformationVariable <String>] [<CommonParameters>]
```

### Specific Account
```
Get-AzureRmDataLakeStoreAccount [[-ResourceGroupName] <String>] [-Name] <String>
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureRmDataLakeStoreAccount** cmdlet gets details of a Data Lake Store account.

## EXAMPLES

### Example 1: Get a Data Lake Store account
```
PS C:\>Get-AzureRmDataLakeStoreAccount -Name "ContosoADL"
```

This command gets the account named ContosoADL.

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

### -ResourceGroupName
Specifies the name of the resource group that contains the Data Lake Store account to get.

```yaml
Type: String
Parameter Sets: All In Resource Group
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

```yaml
Type: String
Parameter Sets: Specific Account
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies the name of the account to get.

```yaml
Type: String
Parameter Sets: Specific Account
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[New-AzureRmDataLakeStoreAccount](.\New-AzureRmDataLakeStoreAccount.md)

[Remove-AzureRmDataLakeStoreAccount](.\Remove-AzureRmDataLakeStoreAccount.md)

[Set-AzureRmDataLakeStoreAccount](.\Set-AzureRmDataLakeStoreAccount.md)

[Test-AzureRmDataLakeStoreAccount](.\Test-AzureRmDataLakeStoreAccount.md)

