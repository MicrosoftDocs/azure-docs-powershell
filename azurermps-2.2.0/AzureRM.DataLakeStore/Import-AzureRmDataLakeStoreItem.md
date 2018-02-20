---
external help file: Microsoft.Azure.Commands.DataLakeStore.dll-Help.xml
ms.assetid: D66CCFDC-9E49-4302-88AC-D27D1B8E0CB2
online version:
schema: 2.0.0
---

# Import-AzureRmDataLakeStoreItem

## SYNOPSIS
Uploads a local file or directory to a Data Lake Store.

## SYNTAX

```
Import-AzureRmDataLakeStoreItem -Account <String> [-Path] <String> [-Destination] <DataLakeStorePathInstance>
 [-Recurse] [-Resume] [-ForceBinary] [[-NumThreads] <Int32>] [-Force] [<CommonParameters>]
```

## DESCRIPTION
The **Import-AzureRmDataLakeStoreItem** cmdlet uploads a local file or directory to a Data Lake Store.

## EXAMPLES

### Example 1: Upload a file
```
PS C:\>Import-AzureRmDataLakeStoreItem -AccountName "ContosoADL" -Path "C:\SrcFile.csv" -Destination "/MyFiles/File.csv"
```

This command uploads the file SrcFile.csv and adds it to the MyFiles folder in the Data Lake Store as File.csv.

## PARAMETERS

### -Destination
Specifies the Data Lake Store path to which to upload a file or folder, starting with the root directory (/).

```yaml
Type: DataLakeStorePathInstance
Parameter Sets: (All)
Aliases:

Required: True
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Force
Indicates that this operation can overwrite the destination file if it already exists.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: 8
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ForceBinary
Indicates that this operation uploads the file as a binary file.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: 6
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NumThreads
Specifies the number of threads to use to upload the file or folder.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: 7
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Path
Specifies the local path of the file or folder to upload.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Recurse
Indicates that this operation should upload all items in all subfolders.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: 4
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Resume
Indicates that this operation should resume a previously canceled or failed upload.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: 5
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Account
Specifies the name of the Data Lake Store account.

```yaml
Type: String
Parameter Sets: (All)
Aliases: AccountName

Required: True
Position: Named
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

[Get-AzureRmDataLakeStoreItem](./Get-AzureRmDataLakeStoreItem.md)

[Export-AzureRmDataLakeStoreItem](./Export-AzureRmDataLakeStoreItem.md)

[Join-AzureRmDataLakeStoreItem](./Join-AzureRmDataLakeStoreItem.md)

[Move-AzureRmDataLakeStoreItem](./Move-AzureRmDataLakeStoreItem.md)

[New-AzureRmDataLakeStoreItem](./New-AzureRmDataLakeStoreItem.md)

[Remove-AzureRmDataLakeStoreItem](./Remove-AzureRmDataLakeStoreItem.md)

[Test-AzureRmDataLakeStoreItem](./Test-AzureRmDataLakeStoreItem.md)
