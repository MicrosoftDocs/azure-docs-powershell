---
external help file: Microsoft.Azure.Commands.Sql.dll-Help.xml
online version: 
schema: 2.0.0
---

# Get-AzureSqlElasticPool

## SYNOPSIS
Gets elastic pools and their property values in an Azure SQL Database.

## SYNTAX

```
Get-AzureSqlElasticPool [[-ElasticPoolName] <String>] [-ServerName] <String> [-ResourceGroupName] <String>
 [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The Get-AzureSqlElasticPool cmdlet gets elastic pools and their property values in an Azure SQL Database.
Specify the name of an existing elastic pool to see the property values for only that pool.

## EXAMPLES

### Example 1: Get all elastic pools
```
PS C:\>Get-AzureSqlElasticPool -ResourceGroupName "ResourceGroup11" -ServerName "Server01"
```

This command gets all elastic pools on the server named Server01.

### Example 2: Get a specific elastic pool
```
PS C:\>Get-AzureSqlElasticPool -ResourceGroupName "ResourceGroup11" -ServerName "Server01" -ElasticPoolName "ElasticPool27"
```

This command gets the elastic pool named ElasticPool27 on the server named Server01.

## PARAMETERS

### -ElasticPoolName
Specifies the name of the elastic pool that this cmdlet gets.

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

### -ServerName
Specifies the name of the server that contains the elastic pool that this cmdlet gets.

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

### -ResourceGroupName
Specifies the name of the resource group that contains the elastic pool that this cmdlet gets.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### InputType
System.String

## OUTPUTS

### OutputType
System.Object

## NOTES
* This cmdlet supports the common parameters: Verbose, Debug, ErrorAction, ErrorVariable, WarningAction, WarningVariable, OutBuffer, PipelineVariable, and OutVariable. For more information, see about_CommonParameters.

## RELATED LINKS

[Azure SQL Database]()

[New-AzureSqlElasticPool]()

[Remove-AzureSqlElasticPool]()

[Set-AzureSqlElasticPool]()

