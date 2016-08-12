---
external help file: SMAzure_Compute.xml
online version: 1f6e64a2-021e-4ad7-93a4-9e1138607f01
schema: 2.0.0
---

# Set-AzureSchedulerJobCollection
## SYNOPSIS
Updates a scheduler job collection.

## SYNTAX

```
Set-AzureSchedulerJobCollection [-Frequency <String>] [-Interval <Int32>] [-MaxJobCount <Int32>] [-PassThru]
 [-Plan <String>] -JobCollectionName <String> -Location <String>
```

## DESCRIPTION
This topic describes the cmdlet in the 0.8.10 version of the Microsoft Azure PowerShell module.
To get the version of the module you're using, in the Azure PowerShell console, type (Get-Module -Name Azure).Version.

The Set-AzureSchedulerJobCollection cmdlet updates a scheduler job collection.

## EXAMPLES

### Example 1: Change the maximum job count for a collection
```
PS C:\>Set-AzureSchedulerJobCollection -Location "North Central US" -JobCollectionName "JobCollection01" -MaxJobCount 30
```

This command changes the maximum job count to 30 on the existing scheduler job collection named JobCollection01.

## PARAMETERS

### -Frequency
Specifies the maximum frequency that can be specified on any job in this scheduler job collection.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: 
Accept pipeline input: False
Accept wildcard characters: False
```

### -Interval
Specifies the interval of recurrence at the frequency specified by using the Frequency parameter.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: 
Accept pipeline input: False
Accept wildcard characters: False
```

### -JobCollectionName
Specifies the name of scheduler job collection to update.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: 
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Location
Specifies the name of the location that hosts the cloud service.
Valid values are: 

-- Anywhere Asia
-- Anywhere Europe
-- Anywhere US
-- East Asia
-- East US
-- North Central US
-- North Europe
-- South Central US
-- Southeast Asia
-- West Europe
-- West US

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: 
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaxJobCount
Specifies the maximum number of jobs that can be created in the scheduler job collection.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: 
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru
Indicates that this cmdlet returns an object representing the item on which it operates.
By default, this cmdlet does not generate any output.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: 
Accept pipeline input: False
Accept wildcard characters: False
```

### -Plan
Specifies the scheduler job collection plan.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: 
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-AzureSchedulerJobCollection](1f6e64a2-021e-4ad7-93a4-9e1138607f01)

[New-AzureSchedulerJobCollection](ac55e6be-eb22-4b33-afac-beb371fbbd32)

[Remove-AzureSchedulerJobCollection](fc46c4d9-4116-4760-9884-3e5ee1bc66f5)

