---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.Network.dll-Help.xml
online version: .\Remove-AzureNetworkSecurityRule.md
schema: 2.0.0
---

# Set-AzureNetworkSecurityRule

## SYNOPSIS
Adds or modifies a network security rule in a network security group.

## SYNTAX

```
Set-AzureNetworkSecurityRule -Name <String> -Type <String> -Priority <Int32> -Action <String>
 -SourceAddressPrefix <String> -SourcePortRange <String> -DestinationAddressPrefix <String>
 -DestinationPortRange <String> -Protocol <String> [-NetworkSecurityGroup] <INetworkSecurityGroup>
 [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-AzureNetworkSecurityRule** cmdlet adds or modifies an Azure network security rule in a network security group.

## EXAMPLES

### 1:
```

```

## PARAMETERS

### -Name
Specifies the name for the network security rule that this cmdlet adds or modifies.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Type
Specifies the type of connection for the network security rule.
Valid values are: Inbound and Outbound.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Priority
Specifies the priority for the network security rule.
Valid values are: integers from 100 to 4096.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Action
Specifies the action for a network security rule.
Valid values are: Allow and Deny.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SourceAddressPrefix
Specifies the CIDR address of the source IP range for the network security rule.
An asterisk (*) specifies any IP address.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SourcePortRange
Specifies a source port range for the network security rule.
Valid values consist of integers from 0 to 65535.
You can specify an individual value, or specify a range in the format LowerNumber-HigherNumber.
A hyphen separates the two values.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DestinationAddressPrefix
Specifies the Classless Interdomain Routing (CIDR) address of the destination IP range for the network security rule.
An asterisk (*) specifies any IP address.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DestinationPortRange
Specifies a destination port range for the network security rule.
Valid values consist of integers from 0 to 65535.
You can specify an individual value, or specify a range in the format LowerNumber-HigherNumber.
A hyphen separates the two values.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Protocol
Specifies the protocol for the network security rule.
Valid values are: 

- TCP 
- UDP 
- *

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NetworkSecurityGroup
Specifies the network security group that this cmdlet modifies.
To obtain an **INetworkSecurityGroup** object, use the **Get-AzureNetworkSecurityGroup** cmdlet.

```yaml
Type: INetworkSecurityGroup
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
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

[Remove-AzureNetworkSecurityRule](.\Remove-AzureNetworkSecurityRule.md)

