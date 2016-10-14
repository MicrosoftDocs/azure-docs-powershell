---
external help file: Microsoft.WindowsAzure.Commands.RemoteApp.dll-Help.xml
online version: .\Set-AzureRemoteAppVNet.md
schema: 2.0.0
---

# Get-AzureRemoteAppVNet

## SYNOPSIS
Retrieves information about azure_2 RemoteApp virtual networks in azure_2.

## SYNTAX

```
Get-AzureRemoteAppVNet [[-VNetName] <String>] [-IncludeSharedKey] [-Profile <AzureSMProfile>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureRemoteAppVNet** cmdlet retrieves information about azure_2 RemoteApp virtual networks in Microsoft Azure.
This cmdlet returns an object that contains information about a specified virtual network.
If no virtual network is specified, this cmdlet returns information about all the virtual networks in the current subscription.

## EXAMPLES

### Example 1: Retrieve information about a virtual network
```
PS C:\>Get-AzureRemoteAppVNet -VNetName "ContosoVNet"
```

This command gets information about the virtual network named ContosoVNet.

## PARAMETERS

### -IncludeSharedKey
Indicates that this cmdlet includes the shared key value in the information it retrieves about the virtual network.

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

### -VNetName
Specifies the name of the azure_2 RemoteApp virtual network.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: True
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

[Set-AzureRemoteAppVNet](.\Set-AzureRemoteAppVNet.md)

