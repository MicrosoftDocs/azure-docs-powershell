---
external help file: Microsoft.Azure.Commands.SiteRecovery.dll-Help.xml
online version: 
schema: 2.0.0
---

# Start-AzureRmSiteRecoveryTestFailoverJob

## SYNOPSIS
{{Fill in the Synopsis}}

## SYNTAX

### ByPEObject (Default)
```
Start-AzureRmSiteRecoveryTestFailoverJob -Direction <String> -ProtectionEntity <ASRProtectionEntity>
 [<CommonParameters>]
```

### ByPEObjectWithVMNetwork
```
Start-AzureRmSiteRecoveryTestFailoverJob -Direction <String> -ProtectionEntity <ASRProtectionEntity>
 -VMNetwork <ASRNetwork> [<CommonParameters>]
```

### ByPEObjectWithAzureVMNetworkId
```
Start-AzureRmSiteRecoveryTestFailoverJob -Direction <String> -ProtectionEntity <ASRProtectionEntity>
 -AzureVMNetworkId <String> [<CommonParameters>]
```

## DESCRIPTION
{{Fill in the Description}}

## EXAMPLES

### Example 1
```
PS C:\> {{ Add example code here }}
```

{{ Add example description here }}

## PARAMETERS

### -AzureVMNetworkId
{{Fill AzureVMNetworkId Description}}

```yaml
Type: String
Parameter Sets: ByPEObjectWithAzureVMNetworkId
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Direction
{{Fill Direction Description}}

```yaml
Type: String
Parameter Sets: (All)
Aliases: 
Accepted values: PrimaryToRecovery, RecoveryToPrimary

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProtectionEntity
{{Fill ProtectionEntity Description}}

```yaml
Type: ASRProtectionEntity
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMNetwork
{{Fill VMNetwork Description}}

```yaml
Type: ASRNetwork
Parameter Sets: ByPEObjectWithVMNetwork
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.SiteRecovery.ASRProtectionEntity

## OUTPUTS

### Microsoft.Azure.Commands.SiteRecovery.ASRJob

## NOTES

## RELATED LINKS

