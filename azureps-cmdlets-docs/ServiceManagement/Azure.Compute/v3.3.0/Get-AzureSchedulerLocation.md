---
external help file: Microsoft.WindowsAzure.Commands.dll-Help.xml
ms.assetid: 410A58A3-CB0E-43FE-B490-B1520BD1CCEC
online version: 
schema: 2.0.0
---

# Get-AzureSchedulerLocation

## SYNOPSIS
Gets available scheduler locations.

## SYNTAX

```
Get-AzureSchedulerLocation [-Profile <AzureSMProfile>] [-InformationAction <ActionPreference>]
 [-InformationVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
This topic describes the cmdlet in the 0.8.10 version of the Microsoft Azure PowerShell module.
To get the version of the module you're using, in the Azure PowerShell console, type `(Get-Module -Name Azure).Version`.

The **Get-AzureSchedulerLocation** cmdlet gets available scheduler locations.

## EXAMPLES

### Example 1: Get available scheduler locations
```
PS C:\> Get-AzureSchedulerLocation
```

This command gets available scheduler locations.

## PARAMETERS

### -InformationAction
Specifies how this cmdlet responds to an information event.

The acceptable values for this parameter are:

- Continue
- Ignore
- Inquire
- SilentlyContinue
- Stop
- Suspend

```yaml
Type: ActionPreference
Parameter Sets: (All)
Aliases: infa

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InformationVariable
Specifies an information variable.

```yaml
Type: String
Parameter Sets: (All)
Aliases: iv

Required: False
Position: Named
Default value: None
Accept pipeline input: False
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-AzureSchedulerJob](./Get-AzureSchedulerJob.md)

[Get-AzureSchedulerJobCollection](./Get-AzureSchedulerJobCollection.md)

[Get-AzureSchedulerJobHistory](./Get-AzureSchedulerJobHistory.md)


