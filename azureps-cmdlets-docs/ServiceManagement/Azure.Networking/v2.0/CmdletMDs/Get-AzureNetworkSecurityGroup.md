---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.Network.dll-Help.xml
online version: .\New-AzureNetworkSecurityGroup.md
schema: 2.0.0
---

# Get-AzureNetworkSecurityGroup

## SYNOPSIS
Gets details for a network security group.

## SYNTAX

```
Get-AzureNetworkSecurityGroup [[-Name] <String>] [-Detailed] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureNetworkSecurityGroup** cmdlet returns details for an Azure network security group.
Specify the *Detailed* parameter to display the network security rules.

## EXAMPLES

### 1:
```

```

## PARAMETERS

### -Name
Specifies the name of the network security group that this cmdlet gets.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Detailed
Indicates that this cmdlet returns the network security rules for the network security group.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[New-AzureNetworkSecurityGroup](.\New-AzureNetworkSecurityGroup.md)

[Remove-AzureNetworkSecurityGroup](.\Remove-AzureNetworkSecurityGroup.md)

