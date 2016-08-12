---
external help file: SMAzure_Compute.xml
online version: ac55e6be-eb22-4b33-afac-beb371fbbd32
schema: 2.0.0
---

# Get-AzureSchedulerJobCollection
## SYNOPSIS
Gets scheduler job collections.

## SYNTAX

```
Get-AzureSchedulerJobCollection [[-Location] <String>] [[-JobCollectionName] <String>]
```

## DESCRIPTION
This topic describes the cmdlet in the 0.8.10 version of the Microsoft Azure PowerShell module.
To get the version of the module you're using, in the Azure PowerShell console, type (Get-Module -Name Azure).Version.

The Get-AzureSchedulerJobCollection cmdlet gets one or more scheduler job collections.

## EXAMPLES

### Example 1: Get all collections
```
PS C:\>Get-AzureSchedulerJobCollection
```

This command gets all scheduler job collections across all locations in the current subscription.

### Example 2: Get all collections for a location
```
PS C:\>Get-AzureSchedulerJobCollection -Location "North Central US"
```

This command gets all scheduler job collections in the location named North Central US.

### Example 3: Get a collection by using a name
```
PS C:\>Get-AzureSchedulerJobCollection -Location "North Central US" -JobCollectionName "JobCollection01"
```

This command gets the scheduler job collection named JobCollection01.

## PARAMETERS

### -JobCollectionName
Specifies the name of the scheduler job collection to get.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
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

Required: False
Position: 1
Default value: 
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[New-AzureSchedulerJobCollection](ac55e6be-eb22-4b33-afac-beb371fbbd32)

[Remove-AzureSchedulerJobCollection](fc46c4d9-4116-4760-9884-3e5ee1bc66f5)

[Set-AzureSchedulerJobCollection](154ab9dd-0d0a-4709-9e5a-716088bf59e0)

