---
external help file: Microsoft.Azure.Commands.Sql.dll-Help.xml
online version: 999c2f73-f7f3-438f-ba9d-8f6451ebbc31
schema: 2.0.0
---

# Get-AzureSqlCapability

## SYNOPSIS
Gets SQL Database capabilities for the current subscription.

## SYNTAX

### FilterResults (Default)
```
Get-AzureSqlCapability [-LocationName] <String> [-ServerVersionName <String>] [-EditionName <String>]
 [-ServiceObjectiveName <String>] [-Profile <AzureProfile>] [<CommonParameters>]
```

### DefaultResults
```
Get-AzureSqlCapability [-LocationName] <String> [-Defaults] [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureSqlCapability** cmdlet gets the Azure SQL Database capabilities available on the current subscription for a region.
If you specify the *ServerVersionName*, *EditionName*, or *ServiceObjectiveName* parameters, this cmdlet returns the specified values and their predecessors.

## EXAMPLES

### Example 1: Get capabilities for the current subscription for a region
```
PS C:\>Get-AzureSqlCapability -LocationName "Central US" 
Location : Central US 
Status : Available 
SupportedServerVersions : {12.0, 2.0}
```

This command returns the capabilities for SQL Database on the current subscription for the Central US region.

### Example 2: Get default capabilities for the current subscription for a region
```
PS C:\>Get-AzureSqlCapability -LocationName "Central US" -Defaults 
Location : Central US 
Status : Available 
ExpandedDetails : Version: 2.0 (Default) -> Edition: Standard (Default) -> Service Objective: S0 (Default)
```

This command returns the default capabilities for SQL Database on the current subscription in the Central US region.

### Example 3: Get details for a service objective
```
PS C:\>Get-AzureSqlCapability -LocationName "Central US" -ServiceObjectiveName "Service11" 
Location : Central US 
Status : Available 
ExpandedDetails : Version: 12.0 (Available) -> Edition: Standard (Default) -> Service Objective: S1 (Available) 
 Version: 2.0 (Default) -> Edition: Standard (Default) -> Service Objective: S1 (Available)
```

This command gets default capabilities for SQL Database for the specified service objective on the current subscription.

## PARAMETERS

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[RMAzure_SqlDatabase](.\AzureRM.Sql.md)

