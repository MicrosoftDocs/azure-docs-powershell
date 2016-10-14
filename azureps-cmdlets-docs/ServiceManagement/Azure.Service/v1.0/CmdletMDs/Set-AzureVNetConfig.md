---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.dll-Help.xml
online version: .\Get-AzureVNetConfig.md
schema: 2.0.0
---

# Set-AzureVNetConfig

## SYNOPSIS
Updates the virtual network settings for an azure_2 cloud service.

## SYNTAX

```
Set-AzureVNetConfig [-ConfigurationPath] <String> [-Profile <AzureSMProfile>]
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-AzureVNetConfig** cmdlet updates the network configuration for the current azure_2 subscription by specifying a path to anetwork configuration file (.netcfg).
The network configuration file defines DNS servers and subnets for cloud services within a subscription.

## EXAMPLES

### Example 1: Update the network configuration of the Azure subscription to a local file
```
PS C:\>Set-AzureVNetConfig  -ConfigurationPath "c:\temp\MyAzNets.netcfg"
```

This command updates the network configuration of the current Microsoft azure_2 subscription to that in the local file "c:\temp\MyAzNets.netcfg".

### Example 2: Set the Azure subscription and then update the network configuration
```
PS C:\>$SubsId = "5bea2bc2-88a5-44b8-abe1-3e76733b6783"
C:\PS> $Cert = Get-Item cert:\LocalMachine\MY\82F105B2DA81149204A6257A9A91EC452B8C52C3
C:\PS> Set-AzureVNetConfig  -ConfigurationPath "c:\temp\MyAzNets.netcfg"
```

This example sets the Microsoft Azure subscription, and then updates the network configuration of that subscription using the configuration defined in the local file "c:\temp\MyAzNets.netcfg".

## PARAMETERS

### -ConfigurationPath
Specifies the path and file name of a network configuration file (.netcfg).

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
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

### -InformationAction
@{Text=}```yaml
Type: ActionPreference
Parameter Sets: (All)
Aliases: infa

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InformationVariable
@{Text=}```yaml
Type: String
Parameter Sets: (All)
Aliases: iv

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

[Get-AzureVNetConfig](.\Get-AzureVNetConfig.md)

[Get-AzureVNetSite](.\Get-AzureVNetSite.md)

[Remove-AzureVNetConfig](.\Remove-AzureVNetConfig.md)

