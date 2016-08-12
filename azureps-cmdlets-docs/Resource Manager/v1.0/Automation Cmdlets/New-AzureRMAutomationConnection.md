---
external help file: RMAzure_Automation.xml
online version: 68f56d1c-23a9-4cb5-8fe8-c3a1e7c2ac1a
schema: 2.0.0
---

# New-AzureRMAutomationConnection
## SYNOPSIS
Creates an Automation connection.

## SYNTAX

```
New-AzureRMAutomationConnection [-ResourceGroupName] <String> [-AutomationAccountName] <String>
 [-Name] <String> [-ConnectionTypeName] <String> [-ConnectionFieldValues] <IDictionary> [-Description <String>]
```

## DESCRIPTION
The **New-AzureRmAutomationConnection** cmdlet creates a connection in azure_2 Automation.

## EXAMPLES

### Example 1: Create a connection
```
PS C:\>$FieldValues = @{"AutomationCertificateName"="ContosoCertificate";"SubscriptionID"="81b59010-dc55-45b7-89cd-5ca26db62472"}
PS C:\> New-AzureRmAutomationConnection -Name "Connection12" -ConnectionTypeName Azure -ConnectionFieldValues $FieldValues -ResourceGroupName "ResourceGroup01" -AutomationAccountName "AutomationAccount01"
```

The first command assigns a hash table of field values to the $FieldValue variable.

The second command creates an azure_2 connection named Connection12 in the Automation account named AutomationAccount01.
The command uses the connection field values in $FieldValues.

## PARAMETERS

### -AutomationAccountName
Specifies the name of the Automation account for which this cmdlet creates a connection.

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

### -ConnectionFieldValues
Specifies a hash table that contains key/value pairs.
The keys represent the connection fields for the specified connection type.
The values represent the specific values of each connection field for the connection instance.

```yaml
Type: IDictionary
Parameter Sets: (All)
Aliases: 

Required: True
Position: 5
Default value: None
Accept pipeline input: True(ByPropertyName)
Accept wildcard characters: False
```

### -ConnectionTypeName
Specifies the name of the connection type.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 4
Default value: None
Accept pipeline input: True(ByPropertyName)
Accept wildcard characters: False
```

### -Description
Specifies a description for the connection.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True(ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies a name for the connection.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 3
Default value: None
Accept pipeline input: True(ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Specifies the name of the resource group for which this cmdlet creates a connection.

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

[Get-AzureRmAutomationConnection](68f56d1c-23a9-4cb5-8fe8-c3a1e7c2ac1a)

[Remove-AzureRmAutomationConnection](76dc3b3d-2dd3-49ad-a28c-afbfc754e020)

