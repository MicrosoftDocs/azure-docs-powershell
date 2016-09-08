---
external help file: RMAzure_Automation.xml
online version: 7fed73b4-73cf-4642-8e10-167ea6158372
schema: 2.0.0
---

# Get-AzureRMAutomationConnection
## SYNOPSIS
Gets an Automation connection.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Get-AzureRMAutomationConnection [-ResourceGroupName] <String> [-AutomationAccountName] <String>
```

### UNNAMED_PARAMETER_SET_2
```
Get-AzureRMAutomationConnection [-ResourceGroupName] <String> [-AutomationAccountName] <String>
 [-Name] <String>
```

### UNNAMED_PARAMETER_SET_3
```
Get-AzureRMAutomationConnection [-ResourceGroupName] <String> [-AutomationAccountName] <String>
 [-ConnectionTypeName] <String>
```

## DESCRIPTION
The **Get-AzureRmAutomationConnection** cmdlet gets one or more azure_2 Automation connections.
By default, this cmdlet retrieves all connections.
Specify the name of a connection to get a specific connection.
Specify the connection type name to get all connections of a specific type.

## EXAMPLES

### Example 1: Get all connections
```
PS C:\>Get-AzureRmAutomationConnection -ResourceGroupName "ResourceGroup01" -AutomationAccountName "Contoso17"
```

This command gets metadata for all connections in the Automation account named Contoso17.

### Example 2: Get all connections of a type
```
PS C:\>Get-AzureRmAutomationConnection -ResourceGroupName "ResourceGroup01" -AutomationAccountName "Contoso17" -ConnectionTypeName "SqlServer"
```

This command gets metadata for connections in the Automation account named Contoso17.
This command gets connections of the type SqlServer.

### Example 3: Get a connection
```
PS C:\>Get-AzureRmAutomationConnection -ResourceGroupName "ResourceGroup01" -AutomationAccountName "Contoso17" -Name "ContosoConnection"
```

This command gets metadata for the connection named ContosoConnection.

## PARAMETERS

### -AutomationAccountName
Specifies the name of the Automation account for which this cmdlet gets connections.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True(ByPropertyName)
Accept wildcard characters: False
```

### -ConnectionTypeName
Specifies the name of a connection type for which this cmdlet retrieves connections.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_3
Aliases: 

Required: True
Position: 3
Default value: None
Accept pipeline input: True(ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies the name of a connection that this cmdlet retrieves.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: 3
Default value: None
Accept pipeline input: True(ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Specifies the name of a resource group for which this cmdlet gets connections.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True(ByPropertyName)
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

### Microsoft.Azure.Commands.Automation.Model.Connection

## NOTES

## RELATED LINKS

[New-AzureRmAutomationConnection](7fed73b4-73cf-4642-8e10-167ea6158372)

[Remove-AzureRmAutomationConnection](76dc3b3d-2dd3-49ad-a28c-afbfc754e020)

