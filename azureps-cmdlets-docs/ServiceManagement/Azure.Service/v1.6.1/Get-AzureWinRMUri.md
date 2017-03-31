---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: CE9A4DA9-E98F-4AAA-A8E0-FE4B424B028C
---

# Get-AzureWinRMUri

## SYNOPSIS
Gets the URI to WinRM https listener to a virtual machine or a list of virtual machines in a hosted service.

## SYNTAX

```
Get-AzureWinRMUri [-ServiceName] <String> [[-Name] <String>] [-Profile <AzureSMProfile>]
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The Get-AzureWinRMUri cmdlet gets the URI of the Windows Remote Management (WinRM) https listener to a virtual machine or a list of virtual machines in a hosted service.

## EXAMPLES

### Example 1: Get the URI of the WinRM https listener to a virtual machine
```
PS C:\>Get-AzureWinRMUri -ServiceName MyService -Name MyVM
```

This command gets the UIR of the WinRM https listener to a virtual machine.

### Example 2: Get the URI of the WinRM https listener to a virtual machine of a specific service
```
PS C:\>Get-AzureWinRMUri -ServiceName MyService
```

This command gets the UIR of the WinRM https listener to a virtual machine.

## PARAMETERS

### -ServiceName
Specifies the name of the Microsoft Azure service that hosts the virtual machine.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies the name of the virtual machine to which the WinRM URI is generated.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Profile
ps_azureprofile_description

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

[New-AzureVM](./New-AzureVM.md)

[New-AzureQuickVM](./New-AzureQuickVM.md)


