---
external help file: Microsoft.Azure.Commands.Sql.dll-Help.xml
online version: 
schema: 2.0.0
---

# Get-AzureSqlServerUpgrade

## SYNOPSIS
Gets the status of an Azure SQL Database server upgrade.

## SYNTAX

```
Get-AzureSqlServerUpgrade -ServerName <String> [-ResourceGroupName] <String> [-Profile <AzureProfile>]
 [<CommonParameters>]
```

## DESCRIPTION
The Get-AzureSqlServerUpgrade cmdlet gets the status of an Azure SQL Database server upgrade.

## EXAMPLES

### Example 1: Get the status of an upgrade
```
PS C:\>Get-AzureSqlServerUpgrade -ResourceGroupName "ResourceGroup11" -ServerName "Server02" | Format-List
ResourceGroupName               : ResourceGroup11
ServerName                      : Server02
Status                          : Queued
```

This command gets the status of an upgrade request from the server named Server02 in resource group named ResourceGroup11.

## PARAMETERS

### -ServerName
Specifies the name of the server about which this cmdlet gets upgrade status.

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
Specifies the name of the resource group that contains the server about which this cmdlet gets upgrade status.

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

[Start-AzureSqlServerUpgrade]()

[Stop-AzureSqlServerUpgrade]()

