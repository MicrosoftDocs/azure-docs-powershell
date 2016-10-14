---
external help file: Microsoft.WindowsAzure.Commands.TrafficManager.dll-Help.xml
online version: http://go.microsoft.com/fwlink/?LinkID=398281
schema: 2.0.0
---

# Add-AzureTrafficManagerEndpoint

## SYNOPSIS
Adds an endpoint to a Traffic Manager profile.

## SYNTAX

```
Add-AzureTrafficManagerEndpoint -DomainName <String> [-Location <String>] -Type <String> -Status <String>
 [-Weight <Int32>] [-MinChildEndpoints <Int32>] [-TrafficManagerProfile] <IProfileWithDefinition>
 [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Add-AzureTrafficManagerEndpoint** cmdlet adds an endpoint to a Microsoft Azure Traffic Manager profile.
After you add an endpoint, pass the result to the **Set-AzureTrafficManagerProfile** cmdlet by using the pipeline operator.
That cmdlet connects to Azure to save your changes.

## EXAMPLES

### Example 1: Add an endpoint to a profile
```
PS C:\>$TrafficManagerProfile = Get-AzureTrafficManagerProfile -Name "ContosoProfile"
PS C:\> Add-AzureTrafficManagerEndpoint -TrafficManagerProfile $TrafficManagerProfile -DomainName "Contoso02App.cloudapp.net" -Status "Enabled" -Type "CloudService" | Set-AzureTrafficManagerProfile
```

The first command uses the **Get-AzureTrafficManagerProfile** cmdlet to get the profile named ContosoProfile, and then stores it in the $TrafficManagerProfile variable.

The second command adds an endpoint to Traffic Manager profile that is stored in $TrafficManagerProfile.
The endpoint has the domain name Contoso02App.couldapp.net.
The command also specifies whether it is enabled and its type.
The command passes the profile object to the **Set-AzureTrafficManagerProfile** cmdlet to connect to Azure to save your changes.

### Example 2: Add an endpoint that has a specified location and weight
```
PS C:\>Add-AzureTrafficManagerEndpoint -TrafficManagerProfile ContosoTrafficManagerProfile -DomainName " Contoso02App.cloudapp.net" -Status Enabled -Type CloudService -Weight 2 -Location myLocation | Set-AzureTrafficManagerProfile
```

This command adds an endpoint to a Traffic Manager profile.
The endpoint has the domain name Contoso02App.couldapp.net.
The command also specifies whether it is enabled and its type.
The command also specifies the weight and location for the endpoint.
The command passes the profile object to **Set-AzureTrafficManagerProfile** to connect to Azure to save your changes.

## PARAMETERS

### -DomainName
Specifies the domain name of the endpoint to add.

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

### -Location
Specifies the location of the endpoint the cmdlet adds.
This must be an Azure location.

This parameter must contain a value for endpoints of the type "Any" or of type "TrafficManager" in a profile that has the load balancing method set to "Performance".
The possible values are the Azure region names, as listed at  http://azure.microsoft.com/regions/http://azure.microsoft.com/regions/.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Type
Specifies the type of endpoint.
Valid values are: 

- CloudService
- AzureWebsite
- TrafficManager

- Any 

If there is more than one AzureWebsite endpoint, the endpoints must be in different datacenters.

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

### -Status
Specifies the status of the monitoring endpoint.
Valid values are: 

- Enabled
- Disabled

If you specify a value of Enabled, Traffic Manager monitors the endpoint and the load-balancing method considers it when managing traffic.

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

### -Weight
Specifies the weight of the endpoint the cmdlet adds.
The valid value range for this parameter is \[1,1000\].

This parameter is only used for RoundRobin load balancing policies.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MinChildEndpoints
Specifies the minimum number of endpoints the nested profile must have online for this endpoint to be considered online.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TrafficManagerProfile
Specifies the Traffic Manager profile object to which to add the endpoint.

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
In-memory profile.```yaml
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

[Remove-AzureTrafficManagerEndpoint](.\Remove-AzureTrafficManagerEndpoint.md)

[Set-AzureTrafficManagerEndpoint](.\Set-AzureTrafficManagerEndpoint.md)

[Get-AzureTrafficManagerProfile](.\Get-AzureTrafficManagerProfile.md)

[Set-AzureTrafficManagerProfile](.\Set-AzureTrafficManagerProfile.md)

