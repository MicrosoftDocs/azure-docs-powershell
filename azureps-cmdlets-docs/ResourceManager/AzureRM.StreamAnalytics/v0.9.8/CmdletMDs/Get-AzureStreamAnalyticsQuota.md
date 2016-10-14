---
external help file: Microsoft.Azure.Commands.StreamAnalytics.dll-Help.xml
online version: 851398c2-2daf-4f3d-acad-e440c8ae736e
schema: 2.0.0
---

# Get-AzureStreamAnalyticsQuota

## SYNOPSIS
Gets information about the Streaming Unit quota of a specified region.

## SYNTAX

```
Get-AzureStreamAnalyticsQuota [-Location] <String> [-Profile <AzureProfile>] [-PipelineVariable <String>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureStreamAnalyticsQuota** cmdlet gets the streaming unit quota for a specified Azure region.

## EXAMPLES

### Example 1: Get the streaming unit quota for a region
```
PS C:\>Get-AzureStreamAnalyticsQuota -Location "West US"
```

This command gets the streaming unit quota and usage for the West US region.

## PARAMETERS

### -Location
Specifies the name of an Azure region/Azure data center location to get Streaming Unit quota information for.
See Azure Regionshttp://azure.microsoft.com/en-us/regions/#services at http://azure.microsoft.com/en-us/regions/#services for a list of supported Azure regions.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### System.Collections.Generic.List`1[[Microsoft.Azure.Commands.StreamAnalytics.Models.PSQuota, Microsoft.Azure.Commands.StreamAnalytics, Version=0.8.11.0, Culture=neutral, PublicKeyToken=null]]Microsoft.Azure.Commands.StreamAnalytics.Models.PSQuota

## NOTES

## RELATED LINKS

