---
external help file: Microsoft.WindowsAzure.Commands.dll-Help.xml
ms.assetid: 42042533-9F84-4189-8C9F-01FD62F89DC3
online version:
schema: 2.0.0
---

# Remove-WAPackVNet

## SYNOPSIS
Removes virtual network objects.

## SYNTAX

```
Remove-WAPackVNet -VNet <VMNetwork> [-PassThru] [-Force] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
These topics are deprecated and will be removed in the future.
This topic describes the cmdlet in the 0.8.1 version of the Microsoft Azure PowerShell module.
To find out the version of the module you're using, from the Azure PowerShell console, type `(Get-Module -Name Azure).Version`.

The **Remove-WAPackVNet** cmdlet removes virtual network objects.

## EXAMPLES

### Example 1: Remove a virtualized network
```
PS C:\> $VNet = Get-WAPackVNet -Name "ContosoVNet01"
PS C:\> Remove-WAPackVM -VNet $VNet
```

The first command gets the virtualized network named ContosoVNet01 by using the **Get-WAPackVNet** cmdlet, and then stores that object in the $VNet variable.
The second command removes the virtualized network stored in $VNet.
The command prompts you for confirmation.

### Example 2: Remove a virtualized network without confirmation
```
PS C:\> $VNet = Get-WAPackVNet -Name "ContosoVNet02"
PS C:\> Remove-WAPackVNet -VNet $VNet -Force
```

The first command gets the cloud service named ContosoVNet02 by using the **Get-WAPackVNet** cmdlet, and then stores that object in the $VNet variable.
The second command removes the virtualized network stored in $VNet.
This command includes the *Force* parameter.
The command does not prompt you for confirmation.

## PARAMETERS

### -Force
Forces the command to run without asking for user confirmation.

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

### -PassThru
Returns an object representing the item with which you are working.
By default, this cmdlet does not generate any output.

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

### -VNet
Specifies a virtualized network.
To obtain a virtualized network, use the **Get-WAPackVNet** cmdlet.

```yaml
Type: VMNetwork
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-WAPackVNet](./Get-WAPackVNet.md)

[New-WAPackVNet](./New-WAPackVNet.md)


