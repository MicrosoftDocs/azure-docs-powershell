---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.dll-Help.xml
online version: .\Add-AzureEndpoint.md
schema: 2.0.0
---

# Add-AzureVirtualIP

## SYNOPSIS
Adds a virtual IP to a cloud service.

## SYNTAX

```
Add-AzureVirtualIP -ServiceName <String> -VirtualIPName <String> [-Profile <AzureProfile>]
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [-PipelineVariable <String>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Add-AzureVirtualIP** cmdlet adds a new virtual IP (VIP) to your Azure service.
The new virtual IP has a name but is not allocated an IP address.

The IP address is allocated only when you associate an endpoint to the VIP.
See Add-AzureEndpoint for more details.

Your subscription is charged for extra VIPs only once they are associated with an endpoint.

## EXAMPLES

### Example 1: Add a virtual IP to a service
```
PS C:\>Add-AzureVirtualIP -VirtualIPName "Vip01" -ServiceName "ContosoService03"
OperationDescription OperationId                          OperationStatus
-------------------- -----------                          ---------------
Add-AzureVirtualIP   4bd7b638-d2e7-216f-ba38-5221233d70ce Succeeded
```

This command adds a virtual IP address to a service.

## PARAMETERS

### -InformationAction
Not Specified

The following values are permitted for this object type.```yaml
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
Not Specified```yaml
Type: String
Parameter Sets: (All)
Aliases: iv

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PipelineVariable
Not Specified```yaml
Type: String
Parameter Sets: (All)
Aliases: pv

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
Type: AzureProfile
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ServiceName
Specifies the name of the service.

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

### -VirtualIPName
Specifies the name of the virtual IP address.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.WindowsAzure.Commands.Utilities.Common.ManagementOperationContext

## NOTES

## RELATED LINKS

[Add-AzureEndpoint](.\Add-AzureEndpoint.md)

[Remove-AzureVirtualIP](.\Remove-AzureVirtualIP.md)

