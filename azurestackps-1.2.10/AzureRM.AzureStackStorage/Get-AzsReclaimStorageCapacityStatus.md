---
external help file: Microsoft.AzureStack.AzureConsistentStorage.Commands.dll-Help.xml
online version: 
schema: 2.0.0
---

# Get-AzsReclaimStorageCapacityStatus

## SYNOPSIS
Gets the status of the reclaimed storage capacity. 

## SYNTAX

```
Get-AzsReclaimStorageCapacityStatus -JobId <String> [-SkipCertificateValidation]
```

## DESCRIPTION
The **Get-AzsReclaimStorageCapacityStatus** cmdlet gets the status of the reclaimed storage capacity. 

## EXAMPLES
### Example 1

```
$jobId = Start-AzsReclaimStorageCapacity

Get-AzsReclaimStorageCapacityStatus -JobId $jobId 

```

## PARAMETERS

### -JobId
This jobId is returned by the Start-AzsReclaimStorageCapacity cmdlet.

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

[Start-AzsReclaimStorageCapacity](./Start-AzsReclaimStorageCapacity.md)


