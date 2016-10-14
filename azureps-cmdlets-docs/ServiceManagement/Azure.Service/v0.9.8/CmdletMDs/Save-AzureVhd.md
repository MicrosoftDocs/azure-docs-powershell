---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.dll-Help.xml
online version: .\Add-AzureVhd.md
schema: 2.0.0
---

# Save-AzureVhd

## SYNOPSIS
Enables download of .vhd images.

## SYNTAX

```
Save-AzureVhd [-Source] <Uri> [-LocalFilePath] <FileInfo> [[-NumberOfThreads] <Int32>] [[-StorageKey] <String>]
 [-OverWrite] [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Save-AzureVhd** cmdlet enables download of .vhd images from a blob where they are stored to a file.
It has parameters to configure the download process by specifying the number of downloader threads that are used or overwriting the file which already exists in the specified file path.

**Save-AzureVhd** does not do any VHD format conversion and the blob is downloaded as it is.

## EXAMPLES

### Example 1: Download a VHD file
```
PS C:\>Save-AzureVhd -Source "http://contosoaccount.blob.core.windows.net/vhdstore/win7baseimage.vhd" -LocalFilePath "C:\vhd\Win7Image.vhd"
```

This command downloads a .vhd file.

### Example 2: Download a VHD file and overwrite the local file
```
PS C:\>Save-AzureVhd -Source "http://contosoaccount.blob.core.windows.net/vhdstore/win7baseimage.vhd" -LocalFilePath "C:\vhd\Win7Image.vhd" -Overwrite
```

This command downloads a .vhd file and overwrites any file in the destination path.

### Example 3: Download a VHD file and specify the number of threads
```
PS C:\>Save-AzureVhd -Source "http://contosoaccount.blob.core.windows.net/vhdstore/win7baseimage.vhd" -LocalFilePath "C:\vhd\Win7Image.vhd" -NumberOfThreads 32
```

This command downloads a .vhd file and specifies the number of threads.

### Example 4: Download a VHD file and specify the storage key
```
PS C:\>Save-AzureVhd -Source "http://contosoaccount.blob.core.windows.net/vhdstore/win7baseimage.vhd" -LocalFilePath "C:\vhd\Win7Image.vhd" -StorageKey "zNvcH0r5vAGmC5AbwEtpcyWCMyBd3eMDbdaa4ua6kwxq6vTZH3Y+sw=="
```

This command downloads a .vhd file and specifies the storage key.

## PARAMETERS

### -Source
Specifies the Uniform Resource Identifier (URI) to the blob in `azure_2`.

```yaml
Type: Uri
Parameter Sets: (All)
Aliases: src

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -LocalFilePath
Specifies the local file path.

```yaml
Type: FileInfo
Parameter Sets: (All)
Aliases: lf

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NumberOfThreads
Specifies the number of download threads that this cmdlet uses during download.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: th

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StorageKey
Specifies the storage key of the blob storage account.
If it is not provided, **Save-AzureVhd** attempts to determine the storage key of the account in *SourceUri* from Azure.

```yaml
Type: String
Parameter Sets: (All)
Aliases: sk

Required: False
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OverWrite
Specifies that this cmdlet deletes the file specified by *LocalFilePath* file if it exists.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: o

Required: False
Position: 5
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Profile
Specifies the Azure profile from which this cmdlet reads.
If you do not specify a profile, this cmdlet reads from the local default profile.

```yaml
Type: AzureProfile
Parameter Sets: (All)
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

[Add-AzureVhd](.\Add-AzureVhd.md)

