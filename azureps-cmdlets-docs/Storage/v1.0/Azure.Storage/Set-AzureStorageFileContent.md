---
external help file: RMAzure_Storage.xml
online version: 2cbd0756-0224-43b0-8e22-a7316b7e24c2
schema: 2.0.0
---

# Set-AzureStorageFileContent
## SYNOPSIS
Uploads the contents of a file.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Set-AzureStorageFileContent [-ShareName] <String> [-Source] <String> [[-Path] <String>]
 [-ClientTimeoutPerRequest <Nullable [System.Int32]>] [-ConcurrentTaskCount <Nullable [System.Int32]>]
 [-Context <AzureStorageContext>] [-Force] [-PassThru] [-ServerTimeoutPerRequest <Nullable [System.Int32]>]
 [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Set-AzureStorageFileContent [-Share] <CloudFileShare> [-Source] <String> [[-Path] <String>]
 [-ClientTimeoutPerRequest <Nullable [System.Int32]>] [-ConcurrentTaskCount <Nullable [System.Int32]>] [-Force]
 [-PassThru] [-ServerTimeoutPerRequest <Nullable [System.Int32]>] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_3
```
Set-AzureStorageFileContent [-Directory] <CloudFileDirectory> [-Source] <String> [[-Path] <String>]
 [-ClientTimeoutPerRequest <Nullable [System.Int32]>] [-ConcurrentTaskCount <Nullable [System.Int32]>] [-Force]
 [-PassThru] [-ServerTimeoutPerRequest <Nullable [System.Int32]>] [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Set-AzureStorageFileContent** cmdlet uploads the contents of a file to a file on a specified share.

## EXAMPLES

### Example 1: Upload a file in the current folder
```
PS C:\>Set-AzureStorageFileContent â€"ShareName "ContosoShare06" â€"Source "DataFile37" â€"Path "ContosoWorkingFolder/CurrentDataFile"
```

This command uploads a file that is named DataFile37 in the current folder as a file that is named CurrentDataFile in the folder named ContosoWorkingFolder.

### Example 2: Upload all the files in the current folder
```
PS C:\>$CurrentFolder = (Get-Item .).FullName
PS C:\> $Container = Get-AzureStorageShare -Name "ContosoShare06"
PS C:\> Get-ChildItem -Recurse | Where-Object { $_.GetType().Name -eq "FileInfo"} | ForEach-Object {
    $path=$_.FullName.Substring($Currentfolder.Length+1).Replace("\","/")
    Set-AzureStorageFileContent -Share $Container -Source $_.FullName -Path $path -Force 
}
```

This example uses several common powershell cmdlets and the current cmdlet to upload all files from the current folder to the root folder of container ContosoShare06.

The first command gets the name of the current folder and stores it in the $CurrentFolder variable.

The second command uses the **Get-AzureStorageShare** cmdlet to get the file share named ContosoShare06, and then stores it in the $Container variable.

The final command gets the contents of the current folder and passes each one to the Where-Object cmdlet by using the pipeline operator.
That cmdlet filters out objects that are not files, and then passes the files to the ForEach-Object cmdlet.
That cmdlet runs a script block for each file that creates the appropriate path for it and then uses the current cmdlet to upload the file.
The result has the same name and same relative position with regard to the other files that this example uploads.
For more information about script blocks, type \[CODE_Snippit\]Get-Help about_Script_Blocks\[CODE_Snippit\].

## PARAMETERS

### -ClientTimeoutPerRequest
@{Text=}

```yaml
Type: Nullable [System.Int32]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ConcurrentTaskCount
@{Text=}

```yaml
Type: Nullable [System.Int32]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Context
@{Text=}

```yaml
Type: AzureStorageContext
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True(ByValue,ByPropertyName)
Accept wildcard characters: False
```

### -Directory
Specifies a folder as a **CloudFileDirectory** object.
This cmdlet uploads the file to the folder that this parameter specifies.
To obtain a directory, use the New-AzureStorageDirectory cmdlet.
You can also use the Get-AzureStorageFile cmdlet to obtain a directory.

```yaml
Type: CloudFileDirectory
Parameter Sets: UNNAMED_PARAMETER_SET_3
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True(ByValue)
Accept wildcard characters: False
```

### -Force
@{Text=}

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

### -PassThru
@{Text=}

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

### -Path
@{Text=}

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ServerTimeoutPerRequest
@{Text=}

```yaml
Type: Nullable [System.Int32]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Share
Specifies a **CloudFileShare** object.
This cmdlet uploads to a file in the file share this parameter specifies.
To obtain a **CloudFileShare** object, use the Get-AzureStorageShare cmdlet.
This object contains the storage context.
If you specify this parameter, do not specify the *Context* parameter.

```yaml
Type: CloudFileShare
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True(ByValue)
Accept wildcard characters: False
```

### -ShareName
Specifies the name of the file share.
This cmdlet uploads to a file in the file share this parameter specifies.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Source
@{Text=}

```yaml
Type: String
Parameter Sets: (All)
Aliases: FullName

Required: True
Position: 2
Default value: None
Accept pipeline input: True(ByPropertyName)
Accept wildcard characters: False
```

### -Confirm
psdx_confirmdesc

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
psdx_whatifdesc

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Remove-AzureStorageDirectory](2cbd0756-0224-43b0-8e22-a7316b7e24c2)

[New-AzureStorageDirectory](2eea330c-759d-4dee-81e9-2e72de9f707e)

[Get-AzureStorageFileContent](7e23b9f6-5f66-49a3-beb8-e2639c5234d7)

