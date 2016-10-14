---
external help file: Microsoft.Azure.Commands.Sql.dll-Help.xml
online version: .\Remove-AzureSqlServerActiveDirectoryAdministrator.md
schema: 2.0.0
---

# Get-AzureSqlServerActiveDirectoryAdministrator

## SYNOPSIS
Gets information about an Azure AD administrator for SQL Server.

## SYNTAX

```
Get-AzureSqlServerActiveDirectoryAdministrator [-ServerName] <String> [-ResourceGroupName] <String>
 [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureSqlServerActiveDirectoryAdministrator** cmdlet gets information about an Azure Active Directory (Azure AD) administrator for an Azure SQL Server in the current subscription.

## EXAMPLES

### Example 1: Gets information about an administrator for a server
```
PS C:\>Get-AzureSqlServerActiveDirectoryAdministrator -ResourceGroupName "ResourceGroup01" -ServerName "Server06"
ResourceGroupName ServerName DisplayName ObjectId 
----------------- ---------- ----------- -------- 
ResourceGroup01   Server06   DBAs        40b79501-b343-44ed-9ce7-da4c8cc7353b
```

This command gets information about an Azure AD administrator for a server named Server06 that is associated with resource group named ResourceGroup01.

## PARAMETERS

### -ServerName
Specifies the name of the SQL Server for which this cmdlet gets information.

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
Specifies the name of the resource group that contains the SQL Server for which this cmdlet gets information.

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
Microsoft.Azure.Commands.Sql.ServerActiveDirectoryAdministrator.Model.AzureSqlServerActiveDirectoryAdministratorModel

## NOTES

## RELATED LINKS

[Remove-AzureSqlServerActiveDirectoryAdministrator](.\Remove-AzureSqlServerActiveDirectoryAdministrator.md)

[Set-AzureSqlServerActiveDirectoryAdministrator](.\Set-AzureSqlServerActiveDirectoryAdministrator.md)

