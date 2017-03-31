---
external help file: Microsoft.WindowsAzure.Commands.TrafficManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 45D3D3A3-F0AC-4102-A6C9-D72E45151CEA
---

# Remove-AzureTrafficManagerEndpoint

## SYNOPSIS
Removes an endpoint from a Traffic Manager profile.

## SYNTAX

```
Remove-AzureTrafficManagerEndpoint -DomainName <String> [-Force]
 [-TrafficManagerProfile] <IProfileWithDefinition> [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-AzureTrafficManagerEndpoint** cmdlet removes an endpoint from a Microsoft Azure Traffic Manager profile.
After you remove an endpoint, pass the result to the **Set-AzureTrafficManagerProfile** cmdlet by using the pipeline operator.
That cmdlet connects to Azure to save your changes.

## EXAMPLES

### Example 1: Remove an endpoint from a profile
```
PS C:\> $TrafficManagerProfile = Get-AzureTrafficManagerProfile -Name "ContosoProfile"
PS C:\> Remove-AzureTrafficManagerEndpoint -TrafficManagerProfile $TrafficManagerProfile -DomainName "Contoso02App.cloudapp.net" | Set-AzureTrafficManagerProfile
```

The first command uses the **Get-AzureTrafficManagerProfile** cmdlet to get the profile named ContosoProfile, and then stores it in the $TrafficManagerProfile variable.

The second command removes an endpoint that has the domain name Contoso02App.cloudapp.net from the Traffic Manager profile that is stored in $TrafficManagerProfile.
The command passes the profile object to the **Set-AzureTrafficManagerProfile** cmdlet to connect to Azure to save your changes.

## PARAMETERS

### -DomainName
Specifies the domain name of the endpoint to remove.

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

### -Force
Forces the command to run without asking for user confirmation.

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

### -TrafficManagerProfile
Specifies the Traffic Manager profile object from which to remove the endpoint.

```yaml
Type: IProfileWithDefinition
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

### Microsoft.WindowsAzure.Commands.Utilities.TrafficManager.Models.IProfileWithDefinition
This cmdlet generates a Traffic Manager profile object, which contains information about the updated profile.

## NOTES

## RELATED LINKS

[Add-AzureTrafficManagerEndpoint](./Add-AzureTrafficManagerEndpoint.md)

[Set-AzureTrafficManagerEndpoint](./Set-AzureTrafficManagerEndpoint.md)

[Get-AzureTrafficManagerProfile](./Get-AzureTrafficManagerProfile.md)

[Set-AzureTrafficManagerProfile](./Set-AzureTrafficManagerProfile.md)


