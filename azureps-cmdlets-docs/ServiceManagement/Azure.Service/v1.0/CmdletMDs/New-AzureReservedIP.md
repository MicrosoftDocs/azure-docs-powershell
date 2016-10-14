---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.dll-Help.xml
online version: .\Get-AzureReservedIP.md
schema: 2.0.0
---

# New-AzureReservedIP

## SYNOPSIS
Creates a reserved IP address.

## SYNTAX

### CreateNewReservedIP (Default)
```
New-AzureReservedIP [-ReservedIPName] <String> [[-Label] <String>] [-Location] <String>
 [-Profile <AzureSMProfile>] [-InformationAction <ActionPreference>] [-InformationVariable <String>]
 [<CommonParameters>]
```

### CreateInUseReservedIPUsingSlot
```
New-AzureReservedIP [-ReservedIPName] <String> [[-Label] <String>] [-Location] <String>
 [-Profile <AzureSMProfile>] [-InformationAction <ActionPreference>] [-InformationVariable <String>]
 [<CommonParameters>]
```

### CreateInUseReservedIP
```
New-AzureReservedIP [-ReservedIPName] <String> [[-Label] <String>] [-Location] <String> [-ServiceName] <String>
 [[-VirtualIPName] <String>] [[-Slot] <String>] [-Profile <AzureSMProfile>]
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **New-AzureReservedIP** cmdlet creates a reserved IP address.

## EXAMPLES

### Example 1: Create a new reserved IP
```
PS C:\>New-AzureReservedIP -ReservedIPName $Name -Label $Label -Location $Location
```

This command creates a new reserved IP address in the subscription, which can be used for creating cloud services that include Web, Worker, and Virtual Machines.

### Example 2: Create a reserved IP based on an existing IP
```
PS C:\>New-AzureReservedIP -ReservedIPName resip14 -Location "West Europe" -ServiceName piptestwesteurope
```

This command creates an existing VIP (Virtual IP) on the specified service.

## PARAMETERS

### -ReservedIPName
Specifies the reserved IP address name.

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

### -Label
Specifies a label for the reserved IP address.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Location
Specifies a location at which to create the reserved IP address.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
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

### -ServiceName
Specifies a service name.

```yaml
Type: String
Parameter Sets: CreateInUseReservedIP
Aliases: 

Required: True
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VirtualIPName
Specifies that this cmdlet uses the **VirtualIPName** parameter to reserve an existing virtual IP address (VIP) in your deployment.
If this parameter is not specified, this cmdlet reserves a new VIP.

```yaml
Type: String
Parameter Sets: CreateInUseReservedIP
Aliases: 

Required: False
Position: 4
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Slot
Specifies the deployment slot.
psdx_paramvalues Staging, Production.

```yaml
Type: String
Parameter Sets: CreateInUseReservedIP
Aliases: 

Required: False
Position: 5
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-AzureReservedIP](.\Get-AzureReservedIP.md)

[Remove-AzureReservedIP](.\Remove-AzureReservedIP.md)

