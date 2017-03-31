---
external help file: Microsoft.WindowsAzure.Commands.dll-Help.xml
ms.assetid: 61CF7F95-F0BB-4282-A971-537CB73708B1
online version: 
schema: 2.0.0
---

# Get-AzureStoreAddOn

## SYNOPSIS
Gets the available Azure Store add-ons.

## SYNTAX

### ListAvailable
```
Get-AzureStoreAddOn [-ListAvailable] [[-Country] <String>] [-Profile <AzureSMProfile>]
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [<CommonParameters>]
```

### GetAddOn
```
Get-AzureStoreAddOn [[-Name] <String>] [-Profile <AzureSMProfile>] [-InformationAction <ActionPreference>]
 [-InformationVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
This topic describes the cmdlet in the 0.8.10 version of the Microsoft Azure PowerShell module.
To get the version of the module you're using, in the Azure PowerShell console, type `(Get-Module -Name Azure).Version`.

Gets all the available add-ons for purchasing from the Azure Store, or gets the existing add-on instances for the current subscription.

## EXAMPLES

### Example 1
```
PS C:\> Get-AzureStoreAddOn
```

This example gets all purchased add-on instances for the current subscription.

### Example 2
```
PS C:\> Get-AzureStoreAddOn -ListAvailable
```

This example gets all the available add-ons for purchasing in United States from the Azure Store.

### Example 3
```
PS C:\> Get-AzureStoreAddOn -Name MyAddOn
```

This example gets an add-on named MyAddOn from the purchased add-on instance in the current subscription.

## PARAMETERS

### -Country
If specified, returns only the Azure Store add-on instances available in the specified country.
The default is "US".

```yaml
Type: String
Parameter Sets: ListAvailable
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### -ListAvailable
If specified, gets available add-ons for purchasing from the Azure Store.

```yaml
Type: SwitchParameter
Parameter Sets: ListAvailable
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Returns the add-on that matches the specified name.

```yaml
Type: String
Parameter Sets: GetAddOn
Aliases: 

Required: False
Position: 0
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[New-AzureStoreAddOn](./New-AzureStoreAddOn.md)

[Remove-AzureStoreAddOn](./Remove-AzureStoreAddOn.md)

[Set-AzureStoreAddOn](./Set-AzureStoreAddOn.md)


