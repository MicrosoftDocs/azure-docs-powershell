---
external help file: Microsoft.Azure.Commands.Insights.dll-Help.xml
online version: .\Add-AutoscaleSetting.md
schema: 2.0.0
---

# Get-AutoscaleSetting

## SYNOPSIS
Gets Autoscale settings.

## SYNTAX

```
Get-AutoscaleSetting -ResourceGroup <String> [-Name <String>] [-DetailedOutput] [-Profile <AzureProfile>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-AutoscaleSetting** cmdlet gets Autoscale settings.
Get all Autoscale settings that are associated to a resource group, or specify a setting by resource group name and setting name.

## EXAMPLES

### Example 1: Get all Autoscale settings for a resource group
```
PS C:\>Get-AutoscaleSetting -ResourceGroup "Default-Web-EastUS" -DetailedOutput
```

This command retrieves the Autoscale settings associated to a resource group named Default-Web-EastUS.

### Example 2: Get a specific Autoscale setting
```
PS C:\>Get-AutoscaleSetting -ResourceGroup "Default-Web-EastUS" -Name "DefaultServerFarm-Default-Web-EastUS" -DetailedOutput
```

This command retrieves the named Autoscale setting associated to the named resource group.

## PARAMETERS

### -ResourceGroup
Specifies the name of the resource group that contains the settings that this cmdlet gets.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies the name of setting that this cmdlet gets.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DetailedOutput
Indicates that this cmdlet displays detailed information about the objects that it retrieves.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Add-AutoscaleSetting](.\Add-AutoscaleSetting.md)

[Get-AutoscaleHistory](.\Get-AutoscaleHistory.md)

[Remove-AutoscaleSetting](.\Remove-AutoscaleSetting.md)

