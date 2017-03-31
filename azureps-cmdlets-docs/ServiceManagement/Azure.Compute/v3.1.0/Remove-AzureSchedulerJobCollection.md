---
external help file: Microsoft.WindowsAzure.Commands.dll-Help.xml
ms.assetid: D4349562-1392-44B6-9353-6231F0CB5C51
online version: 
schema: 2.0.0
---

# Remove-AzureSchedulerJobCollection

## SYNOPSIS
Deletes a scheduler job collection.

## SYNTAX

```
Remove-AzureSchedulerJobCollection [-Force] [[-Location] <String>] [-JobCollectionName] <String>
 [-Profile <AzureSMProfile>] [-InformationAction <ActionPreference>] [-InformationVariable <String>]
 [<CommonParameters>]
```

## DESCRIPTION
This topic describes the cmdlet in the 0.8.10 version of the Microsoft Azure PowerShell module.
To get the version of the module you're using, in the Azure PowerShell console, type `(Get-Module -Name Azure).Version`.

The **Remove-AzureSchedulerJobCollection** cmdlet deletes a scheduler job collection and any jobs under that collection.

## EXAMPLES

### Example 1: Delete a job collection for a location
```
PS C:\> Remove-AzureSchedulerJobCollection -Location "North Central US" -JobCollectionName "JobCollection01"
```

This command deletes the scheduler job collection named JobCollection01 in the North Central US location.
The command also deletes the jobs under JobCollection01.

### Example 2: Delete a job location
```
PS C:\> Remove-AzureSchedulerJobCollection -JobCollectionName "JobCollection02"
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
Default value: None
Accept pipeline input: False
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
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -JobCollectionName
Specifies the name of the scheduler job collection to delete.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-AzureSchedulerJobCollection](./Get-AzureSchedulerJobCollection.md)

[New-AzureSchedulerJobCollection](./New-AzureSchedulerJobCollection.md)

[Set-AzureSchedulerJobCollection](./Set-AzureSchedulerJobCollection.md)


