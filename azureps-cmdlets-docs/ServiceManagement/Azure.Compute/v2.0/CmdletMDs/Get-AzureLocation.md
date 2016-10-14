---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.dll-Help.xml
online version: 007cc1d1-12ff-4ef0-a480-39b958aff004
schema: 2.0.0
---

# Get-AzureLocation

## SYNOPSIS
Gets the available data center locations for the current Azure subscription.

## SYNTAX

```
Get-AzureLocation [-Profile <AzureSMProfile>] [-InformationAction <ActionPreference>]
 [-InformationVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
This topic describes the cmdlet in the 0.8.10 version of the Microsoft Azure PowerShell module.
To get the version of the module you're using, in the Azure PowerShell console, type (Get-Module -Name Azure).Version.

The **Get-AzureLocation** cmdlet returns a list object with the available Azure data centers and their properties for the current Azure subscription.
Before you run this cmdlet, you need to set your current subscription with **Select-AzureSubscription** and **Set-AzureSubscription**.

## EXAMPLES

### Example 1
```
C:\PS> Get-AzureLocation
```

This command gets a list of available data centers, and their properties, for the current subscription.

## PARAMETERS

### -Profile
Specifies the Azure profile from which this cmdlet reads. If you do not specify a profile, this cmdlet reads from the local default profile.```yaml
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

