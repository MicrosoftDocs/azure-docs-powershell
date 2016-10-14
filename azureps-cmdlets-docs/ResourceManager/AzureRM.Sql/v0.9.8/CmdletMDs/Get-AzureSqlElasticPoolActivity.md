---
external help file: Microsoft.Azure.Commands.Sql.dll-Help.xml
online version: 
schema: 2.0.0
---

# Get-AzureSqlElasticPoolActivity

## SYNOPSIS
Gets the status of operations on an elastic pool.

## SYNTAX

```
Get-AzureSqlElasticPoolActivity [-ServerName] <String> [-ElasticPoolName] <String>
 [-ResourceGroupName] <String> [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The Get-AzureSqlElasticPoolActivity cmdlet gets the status of operations on an elastic pool in Azure SQL Database.
You can see status of pool creation and configuration updates.

## EXAMPLES

### Example 1: Get the status of operations for an elastic pool
```
PS C:\>Get-AzureSqlElasticPoolActivity -ResourceGroupName "ResourceGroup11" -ServerName "Server01" -ElasticPoolName "ElasticPool27"
```

This command gets the status of the operations for the elastic pool named ElasticPool27.

## PARAMETERS

### -ServerName
Specifies the name of a server that contains an elastic pool.
This cmdlet gets status for a pool on the server that this parameter specifies.

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

### -ElasticPoolName
Specifies the name of an elastic pool.
This cmdlet gets status for the pool that this parameter specifies.

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

### -ResourceGroupName
Specifies the name of a resource group that contains an elastic pool.
This cmdlet gets status for a pool in the resource group that this parameter specifies.

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

### System.String

## OUTPUTS

### System.Object

## NOTES
* This cmdlet supports the common parameters: Verbose, Debug, ErrorAction, ErrorVariable, WarningAction, WarningVariable, OutBuffer, PipelineVariable, and OutVariable. For more information, see about_CommonParameters.

## RELATED LINKS

[Azure SQL Database]()

[Get-AzureSqlElasticPool]()

[Get-AzureSqlElasticPoolDatabase]()

[New-AzureSqlElasticPool]()

[Remove-AzureSqlElasticPool]()

[Set-AzureSqlElasticPool]()

