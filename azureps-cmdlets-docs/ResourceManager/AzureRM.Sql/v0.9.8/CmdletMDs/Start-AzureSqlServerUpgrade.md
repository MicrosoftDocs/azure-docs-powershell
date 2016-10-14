---
external help file: Microsoft.Azure.Commands.Sql.dll-Help.xml
online version: 
schema: 2.0.0
---

# Start-AzureSqlServerUpgrade

## SYNOPSIS
Starts the upgrade of an Azure SQL Database server.

## SYNTAX

```
Start-AzureSqlServerUpgrade -ServerVersion <String> [-ScheduleUpgradeAfterUtcDateTime <DateTime>]
 [-DatabaseCollection <RecommendedDatabaseProperties[]>]
 [-ElasticPoolCollection <UpgradeRecommendedElasticPoolProperties[]>] -ServerName <String>
 [-ResourceGroupName] <String> [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The Start-AzureSqlServerUpgrade cmdlet starts the upgrade of an Azure SQL Database server version 11 to version 12.
Monitor the progress of an upgrade by using the Get-AzureSqlServerUpgrade cmdlet.

## EXAMPLES

### Example 1: Upgrade a Simple server upgradeUpgrade a
```
PS C:\>Start-AzureSqlServerUpgrade -ResourceGroupName "ResourceGroup11" -ServerName "Server01" -ServerVersion 12.0
ResourceGroupName               : ResourceGroup11
ServerName                      : Server01
ServerVersion                   : 12.0
ScheduleUpgradeAfterUtcDateTime : 
DatabaseCollection              :
```

This command upgrades the server named Server01 in resource group named ResourceGroup11 to version 12.0.
Server01 must currently be version 2.0.

### Example 2: Upgrade server by using schedule time and database recommendation
```
PS C:\>$ScheduleTime = (Get-Date).AddMinutes(5).ToUniversalTime()
PS C:\>$DatabaseMap = New-Object -TypeName Microsoft.Azure.Management.Sql.Models.RecommendedDatabaseProperties
PS C:\> $DatabaseMap.Name = "contosodb"
PS C:\> $DatabaseMap.TargetEdition = "Standard"
PS C:\> $DatabaseMap.TargetServiceLevelObjective = "S0"
PS C:\> Start-AzureSqlServerUpgrade -ResourceGroupName "ResourceGroup11" -ServerName "Server02" -ServerVersion 12.0 -ScheduleUpgradeAfterUtcDateTime $ScheduleTime -DatabaseCollection ($DatabaseMap)
```

The first command creates a time five minutes in the future by using the Get-Date core cmdlet.
The command stores the date in the $ScheduleTime variable.
For more information, type Get-Help Get-Date.The second command creates a RecommendedDatabaseProperties object, and then stores that object in the $DatabaseMap variable.
The next three commands assign values to properties of the object stored in $DatabaseMap.The final command upgrades the existing server named Server02 in the  resource group named ResourceGroup11 to version 12.0.
The earliest time to upgrade is five minutes after you run the command, as specified by the $ScheduleTime variable.
After the upgrade, the database contosodb has the edition Standard and the Service Level Objective value of S0.

## PARAMETERS

### -ServerVersion
Specifies the version to which this cmdlet upgrades the server.
Currently, the only valid value is 12.0.

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

### -ScheduleUpgradeAfterUtcDateTime
Specifies the earliest time, as a DateTime object, to upgrade the server.
Specify a value in the ISO8601 format, in Coordinated Universal Time (UTC).
For more information, type Get-Help Get-Date.

```yaml
Type: DateTime
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DatabaseCollection
Specifies an array of RecommendedDatabaseProperties objects that this cmdlet uses for the server upgrade.

```yaml
Type: RecommendedDatabaseProperties[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ElasticPoolCollection
@{Text=}

```yaml
Type: UpgradeRecommendedElasticPoolProperties[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ServerName
Specifies the name of the server that this cmdlet upgrades.

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

### -ResourceGroupName
Specifies the name of the resource group in which this cmdlet upgrades a server.

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

## OUTPUTS

## NOTES
* This cmdlet supports the common parameters: Verbose, Debug, ErrorAction, ErrorVariable, WarningAction, WarningVariable, OutBuffer, PipelineVariable, and OutVariable. For more information, see about_CommonParameters.

## RELATED LINKS

[Get-AzureSqlServerUpgrade]()

[Stop-AzureSqlServerUpgrade]()

