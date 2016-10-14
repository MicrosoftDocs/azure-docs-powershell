---
external help file: Microsoft.Azure.Commands.DataLakeStore.dll-Help.xml
online version: .\Get-AzureRmDataLakeStoreAccount.md
schema: 2.0.0
---

# Set-AzureRmDataLakeStoreAccount

## SYNOPSIS
Modifies a Data Lake Store account.

## SYNTAX

```
Set-AzureRmDataLakeStoreAccount [-Name] <String> [[-DefaultGroup] <String>] [[-Tags] <Hashtable>]
 [[-ResourceGroupName] <String>] [-InformationAction <ActionPreference>] [-InformationVariable <String>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Set-AzureRmDataLakeStoreAccount** cmdlet modifies a Data Lake Store account.

## EXAMPLES

### Example 1: Add a tag to an account
```
PS C:\>Set-AzureRmDataLakeStoreAccount -Name "ContosoADL" -Tags @{"stage"="production"}
```

This command adds the specified tag to the Data Lake Store account named ContosoADL.

## PARAMETERS

### -Name
Specifies the name of a Data Lake Store account.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DefaultGroup
Specifies the ID of an AzureActive Directory group.
This group is the default group for files and folders that you create.

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

### -Tags
Specifies tags as key-value pairs.
You can use tags to identify a Data Lake Store account from other Azure resources.

```yaml
Type: Hashtable
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Specifies the name of the resource group that contains the Data Lake Store account to modify.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

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

[Get-AzureRmDataLakeStoreAccount](.\Get-AzureRmDataLakeStoreAccount.md)

[New-AzureRmDataLakeStoreAccount](.\New-AzureRmDataLakeStoreAccount.md)

[Remove-AzureRmDataLakeStoreAccount](.\Remove-AzureRmDataLakeStoreAccount.md)

[Test-AzureRmDataLakeStoreAccount](.\Test-AzureRmDataLakeStoreAccount.md)

