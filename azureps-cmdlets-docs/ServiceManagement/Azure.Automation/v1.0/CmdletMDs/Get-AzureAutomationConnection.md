---
external help file: Microsoft.Azure.Commands.Automation.dll-Help.xml
online version: .\New-AzureAutomationConnection.md
schema: 2.0.0
---

# Get-AzureAutomationConnection

## SYNOPSIS
Gets an Azure Automation connection.

## SYNTAX

### ByAll (Default)
```
Get-AzureAutomationConnection [-AutomationAccountName] <String> [-Profile <AzureSMProfile>]
 [<CommonParameters>]
```

### ByConnectionName
```
Get-AzureAutomationConnection -Name <String> [-AutomationAccountName] <String> [-Profile <AzureSMProfile>]
 [<CommonParameters>]
```

### ByConnectionTypeName
```
Get-AzureAutomationConnection -ConnectionTypeName <String> [-AutomationAccountName] <String>
 [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureAutomationConnection** cmdlet gets one or more Microsoft Azure Automation connections.
By default, all connections are returned.
To get a specific connection, specify its name.
To get all connections of a certain type, specify the connection type name.

## EXAMPLES

### Example 1: Get all connections
```
PS C:\>Get-AzureAutomationConnection -AutomationAccountName "Contoso17"
```

This command gets all connections in the Automation account named Contoso17.

### Example 2: Get all connections of a type
```
PS C:\>Get-AzureAutomationConnection -AutomationAccountName "Contoso17"  ¢â‚¬"ConnectionTypeName "Azure"
```

This command gets all Azure connections in the Automation account named Contoso17.

### Example 3: Get a connection
```
PS C:\>Get-AzureAutomationConnection -AutomationAccountName "Contoso17"  ¢â‚¬"Name "Azure"
```

This command gets the connection named MyConnection.

## PARAMETERS

### -AutomationAccountName
Specifies the name of the automation account with the connection to retrieve.

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

### -ConnectionTypeName
Specifies the name of a connection type for the connections to retrieve.

```yaml
Type: String
Parameter Sets: ByConnectionTypeName
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies the name of a connection to retrieve.

```yaml
Type: String
Parameter Sets: ByConnectionName
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Profile
In-memory profile.```yaml
Type: AzureSMProfile
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

### Microsoft.Azure.Commands.Automation.Model.Connection

## NOTES

## RELATED LINKS

[New-AzureAutomationConnection](.\New-AzureAutomationConnection.md)

[Remove-AzureAutomationConnection](.\Remove-AzureAutomationConnection.md)

[Set-AzureAutomationConnectionFieldValue](.\Set-AzureAutomationConnectionFieldValue.md)

