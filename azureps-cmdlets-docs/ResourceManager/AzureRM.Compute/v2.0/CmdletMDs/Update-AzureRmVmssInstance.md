---
external help file: Microsoft.Azure.Commands.Compute.dll-Help.xml
online version: .\Update-AzureRmVmss.md
schema: 2.0.0
---

# Update-AzureRmVmssInstance

## SYNOPSIS
Starts a manual upgrade of the VMSS instance.

## SYNTAX

```
Update-AzureRmVmssInstance [-ResourceGroupName] <String> [-VMScaleSetName] <String> [-InstanceId] <String[]>
 [<CommonParameters>]
```

## DESCRIPTION
The Update-AzureRmVmssInstance cmdlet starts a manual upgrade of the specified Virtual Machine Scale Set (VMSS) instance.
This is used when the upgrade policy on the VMSS Scale Set is set to manual.

## EXAMPLES

### Example 1: Start an upgrade of the VMSS instance
```
PS C:\>Update-AzureRmVmssInstance -ResourceGroupName "Group011" -VMScaleSetName "VMScaleSet001" -InstanceId "0"
```

This command starts an upgrade of the VMSS named VMScaleSet001 that has the instance ID of 0.

## PARAMETERS

### -InstanceId
Specifies, as a string array, the ID or IDs of the instance to upgrade.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Specifies the name of the resource group of the VMSS.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMScaleSetName
Specifies the name of the VMSS instance that this cmdlet upgrades.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

###  
This cmdlet does not generate any output.

## NOTES

## RELATED LINKS

[Update-AzureRmVmss](.\Update-AzureRmVmss.md)

