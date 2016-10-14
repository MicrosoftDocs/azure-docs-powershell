---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.dll-Help.xml
online version: .\New-AzureReservedIP.md
schema: 2.0.0
---

# Get-AzureReservedIP

## SYNOPSIS
Gets a reserved IP address by its name or lists all the reserved IP addresses in the subscription.

## SYNTAX

```
Get-AzureReservedIP [[-ReservedIPName] <String>] [-Profile <AzureSMProfile>]
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureReservedIP** cmdlet gets a reserved IP address by its name or lists all of the reserved IP addresses in the subscription.

## EXAMPLES

### Example 1: Get all reserved IP addresses
```
PS C:\>Get-AzureReservedIP
```

This command gets all reserved IP addresses.

### Example 2: Get a reserved IP address with a specified name
```
PS C:\>Get-AzureReservedIP -ReservedIPName $IpName
```

This command gets the reserved IP address that has the name specified by the $IpName variable.

## PARAMETERS

### -ReservedIPName
Specifies the reserved IP name.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
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

[New-AzureReservedIP](.\New-AzureReservedIP.md)

[Remove-AzureReservedIP](.\Remove-AzureReservedIP.md)

