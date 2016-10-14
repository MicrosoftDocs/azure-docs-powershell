---
external help file: Microsoft.Azure.Commands.DataLakeStore.dll-Help.xml
online version: .\Export-AzureRmDataLakeStoreItem.md
schema: 2.0.0
---

# Get-AzureRmDataLakeStoreItem

## SYNOPSIS
Gets the details of a file or folder in Data Lake Store.

## SYNTAX

```
Get-AzureRmDataLakeStoreItem [-Account] <String> [-Path] <DataLakeStorePathInstance>
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureRmDataLakeStoreItem** cmdlet gets the details of a file or folder in Data Lake Store.

## EXAMPLES

### Example 1: Get details of a file from the Data Lake Store
```
PS C:\>Get-AzureRmDataLakeStoreItem -AccountName "ContosoADL" -Path "/MyFiles/Test.csv"
```

This command gets the details of the file Test.csv from the Data Lake Store.

## PARAMETERS

### -Account
Specifies the name of the Data Lake Store account.

```yaml
Type: String
Parameter Sets: (All)
Aliases: AccountName

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Path
Specifies the Data Lake Store path from which to get details of an item, starting with the root directory (/).

```yaml
Type: DataLakeStorePathInstance
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
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

[Export-AzureRmDataLakeStoreItem](.\Export-AzureRmDataLakeStoreItem.md)

[Get-AzureRmDataLakeStoreChildItem](.\Get-AzureRmDataLakeStoreChildItem.md)

[Import-AzureRmDataLakeStoreItem](.\Import-AzureRmDataLakeStoreItem.md)

[Join-AzureRmDataLakeStoreItem](.\Join-AzureRmDataLakeStoreItem.md)

[Move-AzureRmDataLakeStoreItem](.\Move-AzureRmDataLakeStoreItem.md)

[New-AzureRmDataLakeStoreItem](.\New-AzureRmDataLakeStoreItem.md)

[Remove-AzureRmDataLakeStoreItem](.\Remove-AzureRmDataLakeStoreItem.md)

[Test-AzureRmDataLakeStoreItem](.\Test-AzureRmDataLakeStoreItem.md)

