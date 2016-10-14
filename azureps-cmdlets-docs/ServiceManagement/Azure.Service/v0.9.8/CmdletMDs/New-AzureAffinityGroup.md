---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.dll-Help.xml
online version: .\Get-AzureAffinityGroup.md
schema: 2.0.0
---

# New-AzureAffinityGroup

## SYNOPSIS
Creates an affinity group in the current subscription.

## SYNTAX

```
New-AzureAffinityGroup [-Name] <String> [-Label <String>] [-Description <String>] -Location <String>
 [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **New-AzureAffinityGroup** cmdlet creates an Azure affinity group in the current Azure subscription.

An affinity group puts your services and their resources together in an Azure datacenter.
The affinity group groups members together for optimal performance.
Define affinity groups at the subscription level.
Your affinity groups are available to any subsequent cloud services or storage accounts that you create.
You can add services to an affinity group only when you create it.

## EXAMPLES

### Example 1: Create an affinity group
```
PS C:\>New-AzureAffinityGroup -Name "South01" -Location "South Central US" -Label "South Region" -Description "Affinity group for production applications in southern region."
```

This command creates an affinity group named South01 in the South Central US region.
The command specifies a label and a description.

## PARAMETERS

### -Name
Specifies a name for the affinity group.
The name must be unique to the subscription.

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
Specifies a label for the affinity group.
The label may be up to 100 characters long.

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

### -Description
Specifies a description for the affinity group.
The description may be up to 1024 characters long.

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

### -Location
Specifies the geographical location of the Azure datacenter where this cmdlet creates the affinity group.

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

[Get-AzureAffinityGroup](.\Get-AzureAffinityGroup.md)

[Remove-AzureAffinityGroup](.\Remove-AzureAffinityGroup.md)

[Set-AzureAffinityGroup](.\Set-AzureAffinityGroup.md)

