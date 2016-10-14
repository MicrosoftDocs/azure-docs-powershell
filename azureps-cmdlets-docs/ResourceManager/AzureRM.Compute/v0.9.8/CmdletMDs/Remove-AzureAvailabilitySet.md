---
external help file: Microsoft.Azure.Commands.Compute.dll-Help.xml
online version: .\Get-AzureAvailabilitySet.md
schema: 2.0.0
---

# Remove-AzureAvailabilitySet

## SYNOPSIS
Removes an availability set from Azure.

## SYNTAX

```
Remove-AzureAvailabilitySet [-ResourceGroupName] <String> [[-Name] <String>] [-Force] [-Profile <AzureProfile>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Remove-AzureAvailabilitySet** cmdlet removes an availability set from Azure.

## EXAMPLES

### Example 1: Remove an availability set
```
PS C:\>Remove-AzureAvailabilitySet -Name "AvailabilitySet03" -ResourceGroupName "ResourceGroup11"
```

This command removes an availability set named AvailablitySet03 in the resource group named ResourceGroup11.

## PARAMETERS

### -Force
Forces the command to run without asking for user confirmation.```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of the availability set to remove.```yaml
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
Specifies the name of a resource group.```yaml
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

[Get-AzureAvailabilitySet](.\Get-AzureAvailabilitySet.md)

[New-AzureAvailabilitySet](.\New-AzureAvailabilitySet.md)

