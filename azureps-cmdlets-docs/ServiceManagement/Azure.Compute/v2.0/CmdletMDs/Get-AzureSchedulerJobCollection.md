---
external help file: Microsoft.WindowsAzure.Commands.dll-Help.xml
online version: .\New-AzureSchedulerJobCollection.md
schema: 2.0.0
---

# Get-AzureSchedulerJobCollection

## SYNOPSIS
Gets scheduler job collections.

## SYNTAX

```
Get-AzureSchedulerJobCollection [-Location <String>] [-JobCollectionName <String>] [-Profile <AzureSMProfile>]
 [<CommonParameters>]
```

## DESCRIPTION
This topic describes the cmdlet in the 0.8.10 version of the Microsoft Azure PowerShell module.
To get the version of the module you're using, in the Azure PowerShell console, type (Get-Module -Name Azure).Version.

The **Get-AzureSchedulerJobCollection** cmdlet gets one or more scheduler job collections.

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

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Profile
In-memory profile.```yaml
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[New-AzureSchedulerJobCollection](.\New-AzureSchedulerJobCollection.md)

[Remove-AzureSchedulerJobCollection](.\Remove-AzureSchedulerJobCollection.md)

[Set-AzureSchedulerJobCollection](.\Set-AzureSchedulerJobCollection.md)

