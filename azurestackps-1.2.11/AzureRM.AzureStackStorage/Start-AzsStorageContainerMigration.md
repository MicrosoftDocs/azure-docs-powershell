---
external help file: Microsoft.AzureStack.AzureConsistentStorage.Commands.dll-Help.xml
Module Name: AzureRM.AzureStackStorage
online version: 
schema: 2.0.0
---

# Start-AzsStorageContainerMigration

## SYNOPSIS
Starts the operation to migrate containers to the specified destination share and returns the job ID.

## SYNTAX

```
Start-AzsStorageContainerMigration -ContainerToMigrate <Container> -DestinationShareUncPath <String>
 [-SkipCertificateValidation] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
The **Start-AzsStorageContainerMigration** cmdlet starts the operation to migrate containers to the specified destination share and returns the job ID. This cmdlet is available for Azure Stack multi-node instances only.

## EXAMPLES

### Example 1
```
$Shares = Get-AzsStorageShare

$containers = Get-AzsStorageContainer -ShareName $shares[0].ShareName -Count 4 -Intent Migration 

$DestinationShare = Get-AzsStorageShare -SourceShareName $Shares[0].ShareName 

$jobId = Start-AzsStorageContainerMigration -ContainerToMigrate $containers[1] -DestinationShareUncPath $DestinationShare.UncPath 
 }}
```

## PARAMETERS

### -ContainerToMigrate
Specifies the Azs container that this cmdlet migrates.

```yaml
Type: Container
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -DefaultProfile
The credentials, account, tenant, and subscription used for communication with azure.

```yaml
Type: IAzureContextContainer
Parameter Sets: (All)
Aliases: AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DestinationShareUncPath
Specifies the share to which the container gets migrated.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Stop-AzsStorageContainerMigration](./Stop-AzsStorageContainerMigration.md)


