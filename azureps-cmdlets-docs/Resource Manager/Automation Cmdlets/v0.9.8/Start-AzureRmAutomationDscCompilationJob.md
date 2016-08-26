---
external help file: RMAzure_Automation.xml
online version: cbd50659-1e44-425c-9b97-a58be040e3b9
schema: 2.0.0
---

# Start-AzureRmAutomationDscCompilationJob
## SYNOPSIS
Compiles a DSC configuration in Automation.

## SYNTAX

```
Start-AzureRmAutomationDscCompilationJob [-ResourceGroupName] <String> [-AutomationAccountName] <String>
 [-ConfigurationName] <String> [-ConfigurationData <IDictionary>] [-Parameters <IDictionary>]
```

## DESCRIPTION
The **Start-AzureRmAutomationDscCompilationJob** cmdlet compiles an APS Desired State Configuration (DSC) configuration in azure_2 Automation.

## EXAMPLES

### Example 1: Compile an Azure DSC configuration in Automation
```
PS C:\>$Params = @{"StringParam"="Hello World";"IntegerParam"=32}
PS C:\> Start-AzureRmAutomationDscCompilationJob -ConfigurationName "Config01" -Parameters $Params -ResourceGroupName "ResourceGroup01"
```

The first command creates a dictionary of parameters, and stores them in the $Params variable.

The second command compiles the DSC configuration named Config01.
The command includes the values in $Params for DSC configuration parameters.

## PARAMETERS

### -AutomationAccountName
Specifies the name of the Automation account that contains the DSC configuration that this cmdlet compiles.

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

### -ConfigurationData
Specifies a dictionary of configuration data for DSC configuration.

```yaml
Type: IDictionary
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ConfigurationName
Specifies the name of the DSC configuration that this cmdlet compiles.

```yaml
Type: String
Parameter Sets: (All)
Aliases: Name

Required: True
Position: 3
Default value: None
Accept pipeline input: True(ByPropertyName)
Accept wildcard characters: False
```

### -Parameters
Specifies a dictionary of parameters that this cmdlet uses to compile the DSC configuration.

```yaml
Type: IDictionary
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Specifies the name of a resource group in which this cmdlet compiles a configuration.

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

## NOTES

## RELATED LINKS

[Get-AzureRmAutomationDscCompilationJob](cbd50659-1e44-425c-9b97-a58be040e3b9)

[Get-AzureRmAutomationDscCompilationJobOutput](0375f514-6679-4488-be72-816df6f13124)

