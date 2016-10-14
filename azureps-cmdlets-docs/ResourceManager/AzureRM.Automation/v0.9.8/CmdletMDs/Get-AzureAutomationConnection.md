---
external help file: Microsoft.Azure.Commands.ResourceManager.Automation.dll-Help.xml
online version: .\New-AzureAutomationConnection.md
schema: 2.0.0
---

# Get-AzureAutomationConnection

## SYNOPSIS
Gets an Automation connection.

## SYNTAX

### ByAll (Default)
```
Get-AzureAutomationConnection [-ResourceGroupName] <String> [-AutomationAccountName] <String>
 [-Profile <AzureProfile>] [<CommonParameters>]
```

### ByConnectionName
```
Get-AzureAutomationConnection [-Name] <String> [-ResourceGroupName] <String> [-AutomationAccountName] <String>
 [-Profile <AzureProfile>] [<CommonParameters>]
```

### ByConnectionTypeName
```
Get-AzureAutomationConnection [-ConnectionTypeName] <String> [-ResourceGroupName] <String>
 [-AutomationAccountName] <String> [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureAutomationConnection** cmdlet gets one or more Azure Automation connections.
By default, this cmdlet retrieves all connections.
Specify the name of a connection to get a specific connection.
Specify the connection type name to get all connections of a specific type.

## EXAMPLES

### Example 1: Get all connections
```
PS C:\>Get-AzureAutomationConnection -ResourceGroupName "MyResourceGroup" -AutomationAccountName "Contoso17"
```

This command gets metadata on all connections in the Automation account named Contoso17.

### Example 2: Get all connections of a type
```
PS C:\>Get-AzureAutomationConnection -ResourceGroupName "MyResourceGroup" -AutomationAccountName "Contoso17" -ConnectionTypeName "SqlServer"
```

This command gets metadata on all Azure connections in the Automation account named Contoso17.

### Example 3: Get a connection
```
PS C:\>Get-AzureAutomationConnection -ResourceGroupName "MyResourceGroup" -AutomationAccountName "Contoso17" -Name "MyConnection"
```

This command gets metadata on the connection named MyConnection.

## PARAMETERS

### -AutomationAccountName
Specifies the name of the Automation account for which this cmdlet gets a connection.

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
Specifies the name of a connection type for which this cmdlet retrieves connections.

```yaml
Type: String
Parameter Sets: ByConnectionTypeName
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies the name of a connection that this cmdlet retrieves.

```yaml
Type: String
Parameter Sets: ByConnectionName
Aliases: 

Required: True
Position: 2
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

### -ResourceGroupName
The resource group name.```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
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

