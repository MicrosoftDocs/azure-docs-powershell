---
external help file: SMAzure_Compute.xml
online version: 1f6e64a2-021e-4ad7-93a4-9e1138607f01
schema: 2.0.0
---

# New-AzureSchedulerJobCollection
## SYNOPSIS
Creates a scheduler job collection.

## SYNTAX

```
New-AzureSchedulerJobCollection [-Frequency <String>] [-Interval <Int32>] [-MaxJobCount <Int32>]
 [-Plan <String>] -JobCollectionName <String> -Location <String>
```

## DESCRIPTION
This topic describes the cmdlet in the 0.8.10 version of the Microsoft Azure PowerShell module.
To get the version of the module you're using, in the Azure PowerShell console, type (Get-Module -Name Azure).Version.

The New-AzureSchedulerJobCollection cmdlet creates a scheduler job collection.
If you do not specify a value for the Plan parameter, the cmdlet creates a standard job collection.

## EXAMPLES

### Example 1: Create a scheduler job collection that includes default values
```
PS C:\>New-AzureSchedulerJobCollection -JobCollectionName "JobCollection01" -Location "North Central US" -Plan "Standard"
```

This command creates a standard scheduler job collection named JobCollection01.
The new collection has a default job count and maximum recurrence values for a standard scheduler job collection.

### Example 2: Create a scheduler job collection with specified values
```
PS C:\>New-AzureSchedulerJobCollection -JobCollectionName "JobCollection02" -Location "North Central US" -Frequency "Hour" -Interval 12 -MaxJobCount 30 -Plan "Standard"
```

This command creates a standard scheduler job collection named JobCollection02.
The new collection has a maximum job count of 30 and a maximum recurrence of 12 per hour.

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
Specifies the name for the new scheduler job collection.

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

[Remove-AzureSchedulerJobCollection](fc46c4d9-4116-4760-9884-3e5ee1bc66f5)

[Set-AzureSchedulerJobCollection](154ab9dd-0d0a-4709-9e5a-716088bf59e0)

