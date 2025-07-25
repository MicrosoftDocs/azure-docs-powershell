---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Storage.dll-Help.xml
Module Name: Az.Storage
ms.assetid: A96A1A67-6C9C-499F-9935-B90F7ACEB50E
online version: https://learn.microsoft.com/powershell/module/az.storage/start-azstoragefilecopy
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Storage/Storage.Management/help/Start-AzStorageFileCopy.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Storage/Storage.Management/help/Start-AzStorageFileCopy.md
---

# Start-AzStorageFileCopy

## SYNOPSIS
Starts to copy a source file.

## SYNTAX

### ContainerName
```
Start-AzStorageFileCopy -SrcBlobName <String> -SrcContainerName <String> -DestShareName <String>
 -DestFilePath <String> [-Context <IStorageContext>] [-DestContext <IStorageContext>]
 [-DisAllowDestTrailingDot] [-Force] [-ServerTimeoutPerRequest <Int32>] [-ClientTimeoutPerRequest <Int32>]
 [-DefaultProfile <IAzureContextContainer>] [-ConcurrentTaskCount <Int32>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ContainerInstance
```
Start-AzStorageFileCopy -SrcBlobName <String> -SrcContainer <CloudBlobContainer> -DestShareName <String>
 -DestFilePath <String> [-DestContext <IStorageContext>] [-Force] [-ServerTimeoutPerRequest <Int32>]
 [-ClientTimeoutPerRequest <Int32>] [-DefaultProfile <IAzureContextContainer>] [-ConcurrentTaskCount <Int32>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### BlobInstanceFilePath
```
Start-AzStorageFileCopy -SrcBlob <CloudBlob> -DestShareName <String> -DestFilePath <String>
 [-DestContext <IStorageContext>] [-Force] [-ServerTimeoutPerRequest <Int32>]
 [-ClientTimeoutPerRequest <Int32>] [-DefaultProfile <IAzureContextContainer>] [-ConcurrentTaskCount <Int32>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### BlobInstanceFileInstance
```
Start-AzStorageFileCopy -SrcBlob <CloudBlob> [-DestShareFileClient <ShareFileClient>]
 [-DestContext <IStorageContext>] [-Force] [-ServerTimeoutPerRequest <Int32>]
 [-ClientTimeoutPerRequest <Int32>] [-DefaultProfile <IAzureContextContainer>] [-ConcurrentTaskCount <Int32>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ShareName
```
Start-AzStorageFileCopy -SrcFilePath <String> -SrcShareName <String> -DestShareName <String>
 -DestFilePath <String> [-Context <IStorageContext>] [-DestContext <IStorageContext>]
 [-DisAllowSourceTrailingDot] [-DisAllowDestTrailingDot] [-FileMode <String>] [-Owner <String>]
 [-Group <String>] [-OwnerCopyMode <String>] [-FileModeCopyMode <String>] [-Force]
 [-ServerTimeoutPerRequest <Int32>] [-ClientTimeoutPerRequest <Int32>]
 [-DefaultProfile <IAzureContextContainer>] [-ConcurrentTaskCount <Int32>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ShareInstance
```
Start-AzStorageFileCopy -SrcFilePath <String> -SrcShare <ShareClient> -DestShareName <String>
 -DestFilePath <String> [-DestContext <IStorageContext>] [-FileMode <String>] [-Owner <String>]
 [-Group <String>] [-OwnerCopyMode <String>] [-FileModeCopyMode <String>] [-Force]
 [-ServerTimeoutPerRequest <Int32>] [-ClientTimeoutPerRequest <Int32>]
 [-DefaultProfile <IAzureContextContainer>] [-ConcurrentTaskCount <Int32>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### FileInstanceToFilePath
```
Start-AzStorageFileCopy -SrcFile <ShareFileClient> -DestShareName <String> -DestFilePath <String>
 [-DestContext <IStorageContext>] [-FileMode <String>] [-Owner <String>] [-Group <String>]
 [-OwnerCopyMode <String>] [-FileModeCopyMode <String>] [-Force] [-ServerTimeoutPerRequest <Int32>]
 [-ClientTimeoutPerRequest <Int32>] [-DefaultProfile <IAzureContextContainer>] [-ConcurrentTaskCount <Int32>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### FileInstanceToFileInstance
```
Start-AzStorageFileCopy -SrcFile <ShareFileClient> [-DestShareFileClient <ShareFileClient>]
 [-DestContext <IStorageContext>] [-FileMode <String>] [-Owner <String>] [-Group <String>]
 [-OwnerCopyMode <String>] [-FileModeCopyMode <String>] [-Force] [-ServerTimeoutPerRequest <Int32>]
 [-ClientTimeoutPerRequest <Int32>] [-DefaultProfile <IAzureContextContainer>] [-ConcurrentTaskCount <Int32>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### UriToFilePath
```
Start-AzStorageFileCopy -AbsoluteUri <String> -DestShareName <String> -DestFilePath <String>
 [-DestContext <IStorageContext>] [-Force] [-ServerTimeoutPerRequest <Int32>]
 [-ClientTimeoutPerRequest <Int32>] [-DefaultProfile <IAzureContextContainer>] [-ConcurrentTaskCount <Int32>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### UriToFileInstance
```
Start-AzStorageFileCopy -AbsoluteUri <String> [-DestShareFileClient <ShareFileClient>]
 [-DestContext <IStorageContext>] [-Force] [-ServerTimeoutPerRequest <Int32>]
 [-ClientTimeoutPerRequest <Int32>] [-DefaultProfile <IAzureContextContainer>] [-ConcurrentTaskCount <Int32>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Start-AzStorageFileCopy** cmdlet starts to copy a source file to a destination file.
This cmdlet will trigger asynchronous blob copy, the copy process is handled by server. If this is a cross account blob copy, there is no SLA for the blob copy.

## EXAMPLES

### Example 1: Start copy operation from file to file by using share name and file name
```powershell
Start-AzStorageFileCopy -SrcShareName "ContosoShare01" -SrcFilePath "FilePath01" -DestShareName "ContosoShare02" -DestFilePath "FilePath02"
```

This command starts a copy operation from file to file.
The command specifies share name and file name

### Example 2: Start copy operation from blob to file by using container name and blob name
```powershell
Start-AzStorageFileCopy -SrcContainerName "ContosoContainer01" -SrcBlobName "ContosoBlob01" -DestShareName "ContosoShare" -DestFilePath "FilePath02"
```

This command starts a copy operation from blob to file.
The command specifies container name and blob name

### Example 3: Start copy operation from file to file with specific FileMode, Owner, Group on destination file
```powershell
Start-AzStorageFileCopy -SrcShareName "contososhare01" -SrcFilePath "FilePath01" -DestShareName "contososhare02" -DestFilePath "FilePath02" -FileMode rw-rwx-wT -Owner 1 -Group 1 -FileModeCopyMode Override -OwnerCopyMode Override
```

This command starts a copy operation from file to file, with specific FileMode, Owner, Group on destination file.
If the destination file should have same FileMode, Owner, Group as source file, specify "-FileModeCopyMode Source" and "-OwnerCopyMode Source", the parameters FileMode, Owner, Group should not be specified.
If all the parameters FileModeCopyMode, OwnerCopyMode, FileMode, Owner, Group are not specified, the destination file will have the default FileMode, Owner, Group.
FileMode, Owner, Group only works on NFS file share. 

## PARAMETERS

### -AbsoluteUri
Specifies the URI of the source file.
If the source location requires a credential, you must provide one.

```yaml
Type: System.String
Parameter Sets: UriToFilePath, UriToFileInstance
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ClientTimeoutPerRequest
Specifies the client-side time-out interval, in seconds, for one service request.
If the previous call fails in the specified interval, this cmdlet retries the request.
If this cmdlet does not receive a successful response before the interval elapses, this cmdlet returns an error.

```yaml
Type: System.Nullable`1[System.Int32]
Parameter Sets: (All)
Aliases: ClientTimeoutPerRequestInSeconds

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ConcurrentTaskCount
Specifies the maximum concurrent network calls.
You can use this parameter to limit the concurrency to throttle local CPU and bandwidth usage by specifying the maximum number of concurrent network calls.
The specified value is an absolute count and is not multiplied by the core count.
This parameter can help reduce network connection problems in low bandwidth environments, such as 100 kilobits per second.
The default value is 10.

```yaml
Type: System.Nullable`1[System.Int32]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Context
Specifies an Azure Storage context.
To obtain a context, use the New-AzStorageContext cmdlet.

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.IStorageContext
Parameter Sets: ContainerName, ShareName
Aliases: SrcContext

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DefaultProfile
The credentials, account, tenant, and subscription used for communication with Azure.

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DestContext
Specifies the Azure Storage context of the destination.
To obtain a context, use **New-AzStorageContext**.

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.IStorageContext
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DestFilePath
Specifies the path of the destination file relative to the destination share.

```yaml
Type: System.String
Parameter Sets: ContainerName, ContainerInstance, BlobInstanceFilePath, ShareName, ShareInstance, FileInstanceToFilePath, UriToFilePath
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DestShareFileClient
ShareFileClient object indicated the Dest file.

```yaml
Type: Azure.Storage.Files.Shares.ShareFileClient
Parameter Sets: BlobInstanceFileInstance, FileInstanceToFileInstance, UriToFileInstance
Aliases: DestFile

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DestShareName
Specifies the name of the destination share.

```yaml
Type: System.String
Parameter Sets: ContainerName, ContainerInstance, BlobInstanceFilePath, ShareName, ShareInstance, FileInstanceToFilePath, UriToFilePath
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisAllowDestTrailingDot
Disallow trailing dot (.) to suffix destination directory and destination file names.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ContainerName, ShareName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisAllowSourceTrailingDot
Disallow trailing dot (.) to suffix source directory and source file names.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ShareName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FileMode
The mode permissions to be set on the destination file. Only applicable to NFS Files. Only work together with parameter `-FileModeCopyMode Override`. Symbolic (rwxrw-rw-) is supported.

```yaml
Type: System.String
Parameter Sets: ShareName, ShareInstance, FileInstanceToFilePath, FileInstanceToFileInstance
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FileModeCopyMode
Only applicable to NFS Files. The value "Override" need to be specified together with parameter `-FileMode`. If not specified, the destination file will have the default File Mode.

```yaml
Type: System.String
Parameter Sets: ShareName, ShareInstance, FileInstanceToFilePath, FileInstanceToFileInstance
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force
Forces the command to run without asking for user confirmation.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Group
The owner group identifier (GID) to be set on the destination file. Only applicable to NFS Files. Need specify together with parameter `-OwnerCopyMode Override`.

```yaml
Type: System.String
Parameter Sets: ShareName, ShareInstance, FileInstanceToFilePath, FileInstanceToFileInstance
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Owner
The owner user identifier (UID) to be set on the destination file. Only applicable to NFS Files. Need specify together with parameter `-OwnerCopyMode Override`.

```yaml
Type: System.String
Parameter Sets: ShareName, ShareInstance, FileInstanceToFilePath, FileInstanceToFileInstance
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OwnerCopyMode
Only applicable to NFS Files. The value "Override" need to be specified together with parameter `-Owner` and `-Group`. If not specified, the destination file will have the default Owner and Group.

```yaml
Type: System.String
Parameter Sets: ShareName, ShareInstance, FileInstanceToFilePath, FileInstanceToFileInstance
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ServerTimeoutPerRequest
Specifies the length of the time-out period for the server part of a request.

```yaml
Type: System.Nullable`1[System.Int32]
Parameter Sets: (All)
Aliases: ServerTimeoutPerRequestInSeconds

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SrcBlob
Specifies a **CloudBlob** object.
You can create a cloud blob or obtain one by using the Get-AzStorageBlob cmdlet.

```yaml
Type: Microsoft.Azure.Storage.Blob.CloudBlob
Parameter Sets: BlobInstanceFilePath, BlobInstanceFileInstance
Aliases: ICloudBlob

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -SrcBlobName
Specifies the name of the source blob.

```yaml
Type: System.String
Parameter Sets: ContainerName, ContainerInstance
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SrcContainer
Specifies a cloud blob container object.
You can create cloud blob container object or use the Get-AzStorageContainer cmdlet.

```yaml
Type: Microsoft.Azure.Storage.Blob.CloudBlobContainer
Parameter Sets: ContainerInstance
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SrcContainerName
Specifies the name of the source container.

```yaml
Type: System.String
Parameter Sets: ContainerName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SrcFile
Specifies a **ShareFileClient** object.
You can create a ShareFileClient or obtain one by using **Get-AzStorageFile**.

```yaml
Type: Azure.Storage.Files.Shares.ShareFileClient
Parameter Sets: FileInstanceToFilePath, FileInstanceToFileInstance
Aliases: ShareFileClient

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -SrcFilePath
Specifies the path of the source file relative to the source directory or source share.

```yaml
Type: System.String
Parameter Sets: ShareName, ShareInstance
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SrcShare
Specifies a cloud file share object.
You can create a cloud file share or obtain one by using the Get-AzStorageShare cmdlet.

```yaml
Type: Azure.Storage.Files.Shares.ShareClient
Parameter Sets: ShareInstance
Aliases: ShareClient

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SrcShareName
Specifies the name of the source share.

```yaml
Type: System.String
Parameter Sets: ShareName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Storage.Blob.CloudBlob

### Azure.Storage.Files.Shares.ShareFileClient

### Microsoft.Azure.Commands.Common.Authentication.Abstractions.IStorageContext

## OUTPUTS

### Microsoft.WindowsAzure.Commands.Common.Storage.ResourceModel.AzureStorageFile

## NOTES

## RELATED LINKS

[Get-AzStorageBlob](./Get-AzStorageBlob.md)

[Get-AzStorageContainer](./Get-AzStorageContainer.md)

[Get-AzStorageFile](./Get-AzStorageFile.md)

[Get-AzStorageShare](./Get-AzStorageShare.md)

[Get-AzStorageFileCopyState](./Get-AzStorageFileCopyState.md)

[Stop-AzStorageFileCopy](./Stop-AzStorageFileCopy.md)
