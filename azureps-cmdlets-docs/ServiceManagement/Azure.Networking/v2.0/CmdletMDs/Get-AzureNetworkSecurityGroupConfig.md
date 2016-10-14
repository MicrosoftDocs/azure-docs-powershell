---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.Network.dll-Help.xml
online version: .\New-AzureNetworkSecurityGroup.md
schema: 2.0.0
---

# Get-AzureNetworkSecurityGroupConfig

## SYNOPSIS
Gets details for a network security group.

## SYNTAX

```
Get-AzureNetworkSecurityGroupConfig [-Detailed] -VM <IPersistentVM> [-Profile <AzureSMProfile>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureNetworkSecurityGroupConfig** cmdlet returns details for a network security group.
Specify the *Detailed* parameter to display the network security rules.

## EXAMPLES

### 1:
```

```

## PARAMETERS

### -Detailed
Indicates that this cmdlet displays the network security rules.

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

### -Profile
Specifies the Azure profile from which this cmdlet reads.
If you do not specify a profile, this cmdlet reads from the local default profile.

```yaml
Type: AzureSMProfile
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VM
Specifies the virtual machine for which this cmdlet gets the details of a network security group.

```yaml
Type: IPersistentVM
Parameter Sets: (All)
Aliases: InputObject

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[New-AzureNetworkSecurityGroup](.\New-AzureNetworkSecurityGroup.md)

[Remove-AzureNetworkSecurityGroup](.\Remove-AzureNetworkSecurityGroup.md)

