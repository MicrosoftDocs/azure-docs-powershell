---
external help file: Microsoft.AzureStack.AzureConsistentStorage.Commands.dll-Help.xml
online version: 
schema: 2.0.0
---

# Stop-AzsStorageContainerMigration

## SYNOPSIS
Tries to stop the container migration operation specified by the given job ID.

## SYNTAX

```
Stop-AzsStorageContainerMigration -JobId <String> [-SkipCertificateValidation]
```

## DESCRIPTION
The **Stop-AzsStorageContainerMigration** cmdlet tries to stop the container migration operation specified by the given job ID. This cmdlet is available for Azure Stack multi-node instances only.

## EXAMPLES
### Example 1

```
$jobId = Start-AzsStorageContainerMigration -ContainerToMigrate $containers[1] -DestinationShareUncPath $DestinationShare.UncPath 

Stop-AzsStorageContainerMigration -JobId $jobId 

```

## PARAMETERS

### -JobId
Specifies the Job ID of the Azs container migration that this cmdlet stops.


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

## RELATED LINKS

[Start-AzsStorageContainerMigration](./Start-AzsStorageContainerMigration.md)

