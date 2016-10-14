---
external help file: Microsoft.Azure.Commands.Sql.dll-Help.xml
online version: .\Remove-AzureRmSqlDatabaseThreatDetectionPolicy.md
schema: 2.0.0
---

# Get-AzureRmSqlDatabaseThreatDetectionPolicy

## SYNOPSIS
Gets the threat detection policy for a database.

## SYNTAX

```
Get-AzureRmSqlDatabaseThreatDetectionPolicy [-ServerName] <String> [-DatabaseName] <String>
 [-ResourceGroupName] <String> [-InformationAction <ActionPreference>] [-InformationVariable <String>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureRmSqlDatabaseThreatDetectionPolicy** cmdlet gets the threat detection policy of an azure_2 SQL database.
To use this cmdlet, specify the *ResourceGroupName*, *ServerName*, and *DatabaseName* parameters to identify the database for which this cmdlet gets the policy.

This cmdlet is also supported by the SQL Server Stretch Database service on azure_2.

## EXAMPLES

### Example 1: Get the threat detection policy for a database
```
PS C:\>Get-AzureRmSqlDatabaseThreatDetectionPolicy -ResourceGroupName "ResourceGroup11" -ServerName "Server01" -DatabaseName "Database01"
DatabaseName                 : Database01
ResourceGroupName            : ResourceGroup11
ServerName                   : Server01
ThreatDetectionState         : Disabled
NotificationRecipientsEmails : 
EmailAdmins                  : False
ExcludedDetectionTypes       : {}
```

This command gets the threat detection policy for a database named Database01.
The database is located on the server named Server01, which is assigned to the resource group ResourceGroup11.

## PARAMETERS

### -ServerName
Specifies the name of a server.

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

### -DatabaseName
Specifies the name of a database.

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
Specifies the name of the resource group to which the server is assigned.

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

###  
You cannot pipe input to this cmdlet.

## OUTPUTS

### Microsoft.Azure.Commands.Sql.ThreatDetection.Model.DatabaseThreatDetectionPolicyModel
This cmdlet returns a **Model.DatabaseThreatDetectionPolicyModel** object.

## NOTES

## RELATED LINKS

[Remove-AzureRmSqlDatabaseThreatDetectionPolicy](.\Remove-AzureRmSqlDatabaseThreatDetectionPolicy.md)

[Set-AzureRmSqlDatabaseThreatDetectionPolicy]()

[Azure SQL Database Cmdlets](.\AzureRM.Sql.md)

