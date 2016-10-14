---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.Network.dll-Help.xml
online version: .\Get-AzureVNetGatewayDiagnostics.md
schema: 2.0.0
---

# Stop-AzureVNetGatewayDiagnostics

## SYNOPSIS
Stops a running VPN gateway diagnostics session.

## SYNTAX

```
Stop-AzureVNetGatewayDiagnostics [-VNetName] <String> [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Stop-AzureVNetGatewayDiagnostics** cmdlet stops a running virtual private network (VPN) gateway diagnostics session.
This command saves the results of the diagnostics session to the storage account that the **Start-AzureVNetGatewayDiagnostics** cmdlet specifies.

## EXAMPLES

### 1:
```

```

## PARAMETERS

### -VNetName
Specifies the virtual network that contains a virtual network gateway for which this cmdlet stops diagnostics.

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

[Get-AzureVNetGatewayDiagnostics](.\Get-AzureVNetGatewayDiagnostics.md)

[Start-AzureVNetGatewayDiagnostics](.\Start-AzureVNetGatewayDiagnostics.md)

