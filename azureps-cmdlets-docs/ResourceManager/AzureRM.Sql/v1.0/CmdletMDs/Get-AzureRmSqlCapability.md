---
external help file: Microsoft.Azure.Commands.Sql.dll-Help.xml
online version: 999c2f73-f7f3-438f-ba9d-8f6451ebbc31
schema: 2.0.0
---

# Get-AzureRmSqlCapability

## SYNOPSIS
Gets nextref_database capabilities for the current subscription.

## SYNTAX

### FilterResults (Default)
```
Get-AzureRmSqlCapability [-LocationName] <String> [-ServerVersionName <String>] [-EditionName <String>]
 [-ServiceObjectiveName <String>] [-InformationAction <ActionPreference>] [-InformationVariable <String>]
 [<CommonParameters>]
```

### DefaultResults
```
Get-AzureRmSqlCapability [-LocationName] <String> [-Defaults] [-InformationAction <ActionPreference>]
 [-InformationVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureRmSqlCapability** cmdlet gets the ssSDS capabilities available on the current subscription for a region.
If you specify the *ServerVersionName*, *EditionName*, or *ServiceObjectiveName* parameters, this cmdlet returns the specified values and their predecessors.

## EXAMPLES

### Example 1: Get capabilities for the current subscription for a region
```
PS C:\>Get-AzureRmSqlCapability -LocationName "Central US"
Location                : Central US
Status                  : Available
SupportedServerVersions : {12.0, 2.0}
```

This command returns the capabilities for nextref_database instances on the current subscription for the Central US region.

### Example 2: Get default capabilities for the current subscription for a region
```
PS C:\>Get-AzureRmSqlCapability -LocationName "Central US" -Defaults
Location        : Central US
Status          : Available
ExpandedDetails : Version: 2.0 (Default) -> Edition: Standard (Default) -> Service Objective: S0 (Default)
```

This command returns the default capabilities for SQL Databases on the current subscription in the Central US region.

### Example 3: Get details for a service objective
```
PS C:\>Get-AzureRmSqlCapability -LocationName "Central US" -ServiceObjectiveName "S1"
Location        : Central US
Status          : Available
ExpandedDetails : Version: 12.0 (Available) -> Edition: Standard (Default) -> Service Objective: S1 (Available) 
                  Version: 2.0 (Default) -> Edition: Standard (Default) -> Service Objective: S1 (Available)
```

This command gets default capabilities for SQL Databases for the specified service objective on the current subscription.

## PARAMETERS

### -LocationName
Specifies the name of the Location for which this cmdlet gets capabilities.
For more information, see Azure Regionshttp://azure.microsoft.com/en-us/regions/ (http://azure.microsoft.com/en-us/regions/).

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

### -ServerVersionName
Specifies the name of the server version for which this cmdlet gets capabilities.

```yaml
Type: String
Parameter Sets: FilterResults
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -EditionName
Specifies the name of the database edition for which this cmdlet gets capabilities.

```yaml
Type: String
Parameter Sets: FilterResults
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ServiceObjectiveName
Specifies the name of the service objective for which this cmdlet gets capabilities.

```yaml
Type: String
Parameter Sets: FilterResults
Aliases: 

Required: False
Position: Named
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

### -Defaults
Indicates that this cmdlet gets only defaults.

```yaml
Type: SwitchParameter
Parameter Sets: DefaultResults
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

### Microsoft.Azure.Commands.Sql.Location_Capabilities.Model.LocationCapabilityModel

## NOTES

## RELATED LINKS

[Azure SQL Database Cmdlets](.\AzureRM.Sql.md)

