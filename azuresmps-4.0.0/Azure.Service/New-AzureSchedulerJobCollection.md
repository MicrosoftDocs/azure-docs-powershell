---
external help file: Microsoft.WindowsAzure.Commands.dll-Help.xml
ms.assetid: DF12406D-894C-4732-95EE-D75524023B82
online version: 
schema: 2.0.0
---

# New-AzureSchedulerJobCollection

## SYNOPSIS
Creates a scheduler job collection.

## SYNTAX

```
New-AzureSchedulerJobCollection -Location <String> -JobCollectionName <String> [-Plan <String>]
 [-MaxJobCount <Int32>] [-Frequency <String>] [-Interval <Int32>] [-Profile <AzureSMProfile>]
 [<CommonParameters>]
```

## DESCRIPTION
This topic describes the cmdlet in the 0.8.10 version of the Microsoft Azure PowerShell module.
To get the version of the module you're using, in the Azure PowerShell console, type `(Get-Module -Name Azure).Version`.

The **New-AzureSchedulerJobCollection** cmdlet creates a scheduler job collection.
If you do not specify a value for the *Plan* parameter, the cmdlet creates a standard job collection.

## EXAMPLES

### Example 1: Create a scheduler job collection that includes default values
```
PS C:\> New-AzureSchedulerJobCollection -JobCollectionName "JobCollection01" -Location "North Central US" -Plan "Standard"
```

This command creates a standard scheduler job collection named JobCollection01.
The new collection has a default job count and maximum recurrence values for a standard scheduler job collection.

### Example 2: Create a scheduler job collection with specified values
```
PS C:\> New-AzureSchedulerJobCollection -JobCollectionName "JobCollection02" -Location "North Central US" -Frequency "Hour" -Interval 12 -MaxJobCount 30 -Plan "Standard"
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
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Interval
Specifies the interval of recurrence at the frequency specified by using the *Frequency* parameter.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
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
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Location
Specifies the name of the location that hosts the cloud service.
Valid values are: 

- Anywhere Asia
- Anywhere Europe
- Anywhere US
- East Asia
- East US
- North Central US
- North Europe
- South Central US
- Southeast Asia
- West Europe
- West US

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
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
Default value: None
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
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Profile
Specifies the Azure profile from which this cmdlet reads.
If you do not specify a profile, this cmdlet reads from the local default profile.

```yaml
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-AzureSchedulerJobCollection](./Get-AzureSchedulerJobCollection.md)

[Remove-AzureSchedulerJobCollection](./Remove-AzureSchedulerJobCollection.md)

[Set-AzureSchedulerJobCollection](./Set-AzureSchedulerJobCollection.md)


