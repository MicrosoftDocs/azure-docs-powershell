---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.dll-Help.xml
online version: .\Remove-AzureReservedIPAssociation.md
schema: 2.0.0
---

# Set-AzureReservedIPAssociation

## SYNOPSIS
Associates a reserved IP address with an existing virtual machine or cloud service.

## SYNTAX

```
Set-AzureReservedIPAssociation [-ReservedIPName] <String> [-ServiceName] <String> [[-VirtualIPName] <String>]
 [[-Slot] <String>] [-Profile <AzureSMProfile>] [-InformationAction <ActionPreference>]
 [-InformationVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-AzureReservedIPAssociation** cmdlet associates a reserved IP address with the Virtual IP address (VIP) of a running virtual machine or cloud service.
The reserved IP address must not be in use at the time of invocation of this cmdlet, and must be in the same region as the virtual machine or cloud service.

The operation takes about 30 seconds to complete, after which the virtual machine or service is accessible using the reserved IP address.

## EXAMPLES

### Example 1: Set a reserved IP association
```
PS C:\>Set-AzureReservedIPAssociation -ReservedIPName "ResIp14" -ServiceName "PipTestWestEurope"
```

This command assigns the reserved IP address named ResIp14 to the service PipTestWestEurope.
ResIp14 is a reserved IP in the West Europe region.

## PARAMETERS

### -ReservedIPName
Specifies the name of the reserved IP address to associate with a virtual machine or service.

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

### -ServiceName
Specifies the name of the service that has the deployment with which to associate the reserved IP address.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VirtualIPName
Specifies the name of an existing VIP to associate with a reserved IP.
See Add-AzureVirtualIP to add VIPs to your cloud service.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Slot
Specifies the deployment slot.
psdx_paramvalues

- Staging
- Production

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### Microsoft.WindowsAzure.Commands.Utilities.Common.ManagementOperationContext

## NOTES

## RELATED LINKS

[Remove-AzureReservedIPAssociation](.\Remove-AzureReservedIPAssociation.md)

