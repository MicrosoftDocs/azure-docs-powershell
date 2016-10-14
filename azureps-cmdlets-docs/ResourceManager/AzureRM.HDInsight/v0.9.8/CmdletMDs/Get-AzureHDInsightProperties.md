---
external help file: Microsoft.Azure.Commands.HDInsight.dll-Help.xml
online version: 773fd402-3dc5-41e9-b488-f41d46446618
schema: 2.0.0
---

# Get-AzureHDInsightProperties

## SYNOPSIS
Gets properties about the HDInsight service, such as available locations and capacity.

## SYNTAX

```
Get-AzureHDInsightProperties [-Location] <String> [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureHDInsightProperties** cmdlet gets properties specific to HDInsight, such as the list of available locations, HDInsight cluster versions, and available compute capacity.

## EXAMPLES

### Example 1: Get the properties of an Azure HDInsight cluster
```
PS C:\>Get-AzureHDInsightProperties -Location "East US 2"
```

This command gets properties from an HDInsight service from location East US 2.

## PARAMETERS

### -Location
Gets or sets the datacenter location for the cluster.```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
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

[Azure HDInsight Cmdlets](.\AzureRM.HDInsight.md)

