---
external help file: Microsoft.Azure.Commands.Batch.dll-Help.xml
online version: .\Get-AzureBatchAccountKeys.md
schema: 2.0.0
---

# Get-AzureBatchRemoteDesktopProtocolFile

## SYNOPSIS
Gets an RDP file from a compute node.

## SYNTAX

### Id_Path (Default)
```
Get-AzureBatchRemoteDesktopProtocolFile [-PoolId] <String> [-ComputeNodeId] <String> -DestinationPath <String>
 -BatchContext <BatchAccountContext> [-Profile <AzureProfile>] [<CommonParameters>]
```

### Id_Stream
```
Get-AzureBatchRemoteDesktopProtocolFile [-PoolId] <String> [-ComputeNodeId] <String>
 -DestinationStream <Stream> -BatchContext <BatchAccountContext> [-Profile <AzureProfile>] [<CommonParameters>]
```

### InputObject_Stream
```
Get-AzureBatchRemoteDesktopProtocolFile [[-ComputeNode] <PSComputeNode>] -DestinationStream <Stream>
 -BatchContext <BatchAccountContext> [-Profile <AzureProfile>] [<CommonParameters>]
```

### InputObject_Path
```
Get-AzureBatchRemoteDesktopProtocolFile [[-ComputeNode] <PSComputeNode>] -DestinationPath <String>
 -BatchContext <BatchAccountContext> [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureBatchRemoteDesktopProtocolFile** cmdlet gets a Remote Desktop Protocol (RDP) file from a compute node and saves it as a file or to a user supplied stream.

## EXAMPLES

### Example 1: Get an RDP file from a specified compute node and save the file
```
PS C:\>Get-AzureBatchRemoteDesktopProtocolFile -PoolId "Pool06" -ComputeNodeId "ComputeNode01" -DestinationPath "C:\PowerShell\ComputeNode01.rdp" -BatchContext $Context
```

This command gets an RDP file from the compute node that has the ID ComputeNode01 in the pool that has the ID Pool06.
The command saves the .rdp file as C:\PowerShell\MyComputeNode.rdp.
Use the **Get-AzureBatchAccountKeys** cmdlet to assign a context to the $Context variable.

### Example 2: Get an RDP file from a compute node and save the file by using the pipeline
```
PS C:\>Get-AzureBatchComputeNode -PoolId "Pool06" -Id "ComputeNode02" -BatchContext $Context | Get-AzureBatchRemoteDesktopProtocolFile -DestinationPath "C:\PowerShell\MyComputeNode02.rdp" -BatchContext $Context
```

This command gets the compute node that has the ID ComputeNode02 in the pool that has the ID Pool06.
The command passes that compute node to the current cmdlet by using the pipeline operator.
The current cmdlet gets an .rpd file from the compute node, and then saves the contents as a file that is named C:\PowerShell\MyComputeNode02.rdp.

### Example 3: Get a RDP file from a specified compute node and direct it to a stream
```
PS C:\>$Stream = New-Object -TypeName "System.IO.MemoryStream"
 PS C:\> Get-AzureBatchRemoteDesktopProtocolFile "Pool06" -ComputeNodeId "ComputeNode03" -DestinationStream $Stream -BatchContext $Context
```

The first command creates a stream by using the New-Object cmdlet, and then stores it in the $Stream variable.

The second command gets an .rdp file from the compute node that has the ID ComputeNode03 in the pool that has the ID Pool06.
The command directs file contents to the stream in $Stream.

## PARAMETERS

### -BatchContext
Specifies the **BatchAccountContext** instance that this cmdlet uses to interact with the Batch service.
To obtain a **BatchAccountContext** object that contains access keys for your subscription, use the Get-AzureBatchAccountKeys cmdlet.

```yaml
Type: BatchAccountContext
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ComputeNode
Specifies a compute node, as a **PSComputeNode** object, to which the .rdp file points.
To obtain a compute node object, use the Get-AzureBatchComputeNode cmdlet.

```yaml
Type: PSComputeNode
Parameter Sets: InputObject_Stream, InputObject_Path
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ComputeNodeId
Specifies the ID of the compute node to which the .rdp file points.

```yaml
Type: String
Parameter Sets: Id_Path, Id_Stream
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DestinationPath
Specifies the file path where this cmdlet saves the .rdp file.

```yaml
Type: String
Parameter Sets: Id_Path, InputObject_Path
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DestinationStream
Specifies the stream into which this cmdlet directs the RDP data.
This cmdlet does not close or rewind this stream.

```yaml
Type: Stream
Parameter Sets: Id_Stream, InputObject_Stream
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PoolId
Specifies the ID of the pool that contains the compute node from which this cmdlet gets an .rdp file.

```yaml
Type: String
Parameter Sets: Id_Path, Id_Stream
Aliases: 

Required: True
Position: 1
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

[Get-AzureBatchAccountKeys](.\Get-AzureBatchAccountKeys.md)

[Get-AzureBatchComputeNode](.\Get-AzureBatchComputeNode.md)

[Azure Batch Cmdlets](.\AzureRM.Batch.md)

