---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.Network.dll-Help.xml
online version: .\Get-AzureNetworkSecurityGroupForSubnet.md
schema: 2.0.0
---

# Remove-AzureNetworkSecurityGroupFromSubnet

## SYNOPSIS
Dissociates a network security group from a subnet.

## SYNTAX

```
Remove-AzureNetworkSecurityGroupFromSubnet [-Name] <String> [-VirtualNetworkName] <String>
 [-SubnetName] <String> [-Force] [-PassThru] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-AzureNetworkSecurityGroupFromSubnet** cmdlet dissociates an azure_2 network security group from a subnet.

## EXAMPLES

### 1:
```

```

## PARAMETERS

### -Name
Specifies the name of the network security group that this cmdlet dissociates from a subnet.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VirtualNetworkName
Specifies the name of a virtual network.
This cmdlet disassociates a network security group from a subnet in the virtual network that this parameter specifies.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubnetName
Specifies the name of a subnet from which this cmdlet dissociates a network security group.

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

### -Force
ps_force

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
passthru

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
ps_azureprofile_description

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-AzureNetworkSecurityGroupForSubnet](.\Get-AzureNetworkSecurityGroupForSubnet.md)

[Set-AzureNetworkSecurityGroupToSubnet](.\Set-AzureNetworkSecurityGroupToSubnet.md)

