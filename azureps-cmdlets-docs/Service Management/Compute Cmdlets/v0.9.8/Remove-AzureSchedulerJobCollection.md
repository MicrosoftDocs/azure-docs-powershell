---
external help file: SMAzure_Compute.xml
online version: 1f6e64a2-021e-4ad7-93a4-9e1138607f01
schema: 2.0.0
---

# Remove-AzureSchedulerJobCollection
## SYNOPSIS
Deletes a scheduler job collection.

## SYNTAX

```
Remove-AzureSchedulerJobCollection [[-Location] <String>] [-JobCollectionName] <String> [-Force]
```

## DESCRIPTION
This topic describes the cmdlet in the 0.8.10 version of the Microsoft Azure PowerShell module.
To get the version of the module you're using, in the Azure PowerShell console, type (Get-Module -Name Azure).Version.

The Remove-AzureSchedulerJobCollection cmdlet deletes a scheduler job collection and any jobs under that collection.

## EXAMPLES

### Example 1: Delete a job collection for a location
```
PS C:\>Remove-AzureSchedulerJobCollection -Location "North Central US" -JobCollectionName "JobCollection01"
```

This command deletes the scheduler job collection named JobCollection01 in the North Central US location.
The command also deletes the jobs under JobCollection01.

### Example 2: Delete a job location
```
PS C:\>Remove-AzureSchedulerJobCollection -JobCollectionName "JobCollection02"
```

This command deletes the scheduler job collection named JobCollection02.
The command also deletes the jobs under JobCollection02.

## PARAMETERS

### -Force
Indicates that this cmdlet removes the scheduler job collection without prompting you for confirmation.

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

### -JobCollectionName
Specifies the name of the scheduler job collection to delete.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
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
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-AzureSchedulerJobCollection](1f6e64a2-021e-4ad7-93a4-9e1138607f01)

[New-AzureSchedulerJobCollection](ac55e6be-eb22-4b33-afac-beb371fbbd32)

[Set-AzureSchedulerJobCollection](154ab9dd-0d0a-4709-9e5a-716088bf59e0)

