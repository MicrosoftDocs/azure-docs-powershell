---
external help file: RMAzure_Automation.xml
online version: 19472f94-5827-4878-a17a-d7bb10932861
schema: 2.0.0
---

# Get-AzureRmAutomationDscNodeReport
## SYNOPSIS
Gets reports sent from a DSC node to Automation.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Get-AzureRmAutomationDscNodeReport [-ResourceGroupName] <String> [-AutomationAccountName] <String>
 [-EndTime <DateTimeOffset]>] [-StartTime <DateTimeOffset]>] -NodeId <Guid>
```

### UNNAMED_PARAMETER_SET_2
```
Get-AzureRmAutomationDscNodeReport [-ResourceGroupName] <String> [-AutomationAccountName] <String> -Id <Guid>
 -NodeId <Guid>
```

### UNNAMED_PARAMETER_SET_3
```
Get-AzureRmAutomationDscNodeReport [-ResourceGroupName] <String> [-AutomationAccountName] <String> [-Latest]
 -NodeId <Guid>
```

## DESCRIPTION
The **Get-AzureRmAutomationDscNodeReport** cmdlet gets reports sent from an APS Desired State Configuration (DSC) node to azure_2 Automation.

## EXAMPLES

### Example 1: Get all reports for a DSC node
```
PS C:\>$Node = Get-AzureRmAutomationDscNode -ResourceGroupName "ResourceGroup03" -AutomationAccountName "Contoso17" -Name "Computer14"
PS C:\> Get-AzureRmAutomationDscNodeReport -ResourceGroupName "ResourceGroup14" -AutomationAccountName "Contoso17" -NodeId $Node.Id
```

The first command gets the DSC node for the computer named Computer14 in the Automation account named Contoso17.
The command stores this object in the $Node variable.

The second command gets metadata for all reports sent from the DSC node named Computer14 to the Automation account named Contoso17.
The command specifies the node by using the **Id** property of the $Node object.

### Example 2: Get a report for a DSC node by report ID
```
PS C:\>$Node = Get-AzureRmAutomationDscNode -ResourceGroupName "ResourceGroup03" -AutomationAccountName "Contoso17" -Name "Computer14"
PS C:\> Get-AzureRmAutomationDscNodeReport -ResourceGroupName "ResourceGroup03" -AutomationAccountName "Contoso17" -NodeId $Node.Id -Id c0a1718e-d8be-4fa3-91b6-82e1d3a36298
```

The first command gets the DSC node for the computer named Computer14 in the Automation account named Contoso17.
The command stores this object in the $Node variable.

The second command gets metadata for the report identified by the specified ID sent from the DSC node named Computer14 to the Automation account named Contoso17.

### Example 3: Get the latest report for a DSC node
```
PS C:\>$Node = Get-AzureRmAutomationDscNode -ResourceGroupName "ResourceGroup03" -AutomationAccountName "Contoso17" -Name "Computer14"
PS C:\> Get-AzureRmAutomationDscNodeReport -ResourceGroupName "ResourceGroup03" -AutomationAccountName "Contoso17" -NodeId $Node.Id -Latest
```

The first command gets the DSC node for the computer named Computer14 in the Automation account named Contoso17.
The command stores this object in the $Node variable.

The second command gets metadata for the latest report sent from the DSC node named Computer14 to the Automation account named Contoso17.

## PARAMETERS

### -AutomationAccountName
Specifies the name of an Automation account.
This cmdlet exports reports for a DSC node that belongs to the account that this parameter specifies.

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

### -EndTime
Specifies an end time.
This cmdlet gets reports that Automation received before this time.

```yaml
Type: DateTimeOffset]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True(ByPropertyName)
Accept wildcard characters: False
```

### -Id
Specifies the unique ID of the DSC node report for this cmdlet to get.

```yaml
Type: Guid
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: ReportId

Required: True
Position: Named
Default value: None
Accept pipeline input: True(ByPropertyName)
Accept wildcard characters: False
```

### -Latest
Indicates that this cmdlet gets the latest DSC report for the specified node only.

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_3
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NodeId
Specifies the unique ID of the DSC node for which this cmdlet gets reports.

```yaml
Type: Guid
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True(ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Specifies the name of a resource group that contains the DSC node for which this cmdlet gets reports.

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

### -StartTime
Specifies a start time.
This cmdlet gets reports that Automation received after this time.

```yaml
Type: DateTimeOffset]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True(ByPropertyName)
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-AzureRmAutomationDscNode](19472f94-5827-4878-a17a-d7bb10932861)

[Export-AzureRmAutomationDscNodeReportContent](0bfb6a70-3a4a-4e58-a0b9-e41eb52a90ef)

