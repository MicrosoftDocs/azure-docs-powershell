---
external help file: Microsoft.Azure.Commands.Compute.dll-Help.xml
online version: .\New-AzureAvailabilitySet.md
schema: 2.0.0
---

# Get-AzureAvailabilitySet

## SYNOPSIS
Gets Azure availability sets in a resource group.

## SYNTAX

```
Get-AzureAvailabilitySet [-ResourceGroupName] <String> [[-Name] <String>] [-Profile <AzureProfile>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureAvailabilitySet** cmdlet gets Azure availability sets in a resource group.
Specify the name of a specific availability set to get.

## EXAMPLES

### Example 1: Get a specific availability set
```
PS C:\>Get-AzureAvailabilitySet -ResourceGroupName "ResourceGroup11" -Name "AvailabilitySet03"
```

This command gets the availability set named AvailablitySet03 in the resource group named ResourceGroup11.

### Example 2: Get all availability sets
```
PS C:\>Get-AzureAvailabilitySet -ResourceGroupName "ResourceGroup11"
```

This command gets all the availability sets in the resource group named ResourceGroup11.

## PARAMETERS

### -Name
Specifies the name of an availability set to get.

```yaml
Type: String
Parameter Sets: (All)
Aliases: ResourceName, AvailabilitySetName

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### -ResourceGroupName
Specifies the name of a resource group.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[New-AzureAvailabilitySet](.\New-AzureAvailabilitySet.md)

[Remove-AzureAvailabilitySet](.\Remove-AzureAvailabilitySet.md)

