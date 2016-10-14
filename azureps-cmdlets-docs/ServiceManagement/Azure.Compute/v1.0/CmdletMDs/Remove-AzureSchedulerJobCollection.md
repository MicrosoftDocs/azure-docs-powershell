---
external help file: Microsoft.WindowsAzure.Commands.dll-Help.xml
online version: .\Get-AzureSchedulerJobCollection.md
schema: 2.0.0
---

# Remove-AzureSchedulerJobCollection

## SYNOPSIS
Deletes a scheduler job collection.

## SYNTAX

```
Remove-AzureSchedulerJobCollection [-Force] [-Location <String>] -JobCollectionName <String>
 [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
powershell_prelim

The **Remove-AzureSchedulerJobCollection** cmdlet deletes a scheduler job collection and any jobs under that collection.

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
Default value: None
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
Accept pipeline input: True (ByPropertyName)
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

[Get-AzureSchedulerJobCollection](.\Get-AzureSchedulerJobCollection.md)

[New-AzureSchedulerJobCollection](.\New-AzureSchedulerJobCollection.md)

[Set-AzureSchedulerJobCollection](.\Set-AzureSchedulerJobCollection.md)

