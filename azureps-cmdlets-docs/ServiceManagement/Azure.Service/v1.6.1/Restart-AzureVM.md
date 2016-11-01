---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 247FAC9D-2E66-42D6-9D4A-87E96C08F6FA
---

# Restart-AzureVM

## SYNOPSIS
Restarts an Azure virtual machine.

## SYNTAX

### ByName (Default)
```
Restart-AzureVM [-ServiceName] <String> [-Profile <AzureSMProfile>] [-InformationAction <ActionPreference>]
 [-InformationVariable <String>] [<CommonParameters>]
```

### RestartByName
```
Restart-AzureVM [-Name] <String> [-ServiceName] <String> [-Profile <AzureSMProfile>]
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [<CommonParameters>]
```

### RedeployByName
```
Restart-AzureVM [-Name] <String> [-Redeploy] [-ServiceName] <String> [-Profile <AzureSMProfile>]
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [<CommonParameters>]
```

### RestartInput
```
Restart-AzureVM -VM <PersistentVM> [-ServiceName] <String> [-Profile <AzureSMProfile>]
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [<CommonParameters>]
```

### RedeployInput
```
Restart-AzureVM -VM <PersistentVM> [-Redeploy] [-ServiceName] <String> [-Profile <AzureSMProfile>]
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Restart-AzureVM** cmdlet requests a restart of an Azure virtual machine.

## EXAMPLES

### Example 1: Restart a virtual machine
```
PS C:\>Restart-AzureVM -ServiceName "MyService01" -Name "MyVM"
```

This command restarts the VirtualMachine27 virtual machine running in the Azure service named Service01.

### Example 2: Restart a virtual machine by using a virtual machine object
```
PS C:\>Get-AzureVM -ServiceName "MyService01" -Name "VirtualMachine27" | Restart-AzureVM
```

This command retrieves the virtual machine object for the virtual machine named MyVM and then restarts it.

## PARAMETERS

### -Name
Specifies the name of the virtual machine to restart.

```yaml
Type: String
Parameter Sets: RestartByName, RedeployByName
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ServiceName
Specifies the name of the Azure service that contains the virtual machine to restart.

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

### -VM
Specifies a virtual machine object that identifies the virtual machine to restart.

```yaml
Type: PersistentVM
Parameter Sets: RestartInput, RedeployInput
Aliases: InputObject

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Redeploy
Redeploy the virtual machine.

```yaml
Type: SwitchParameter
Parameter Sets: RedeployByName, RedeployInput
Aliases: 

Required: True
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

[Get-AzureVM](./Get-AzureVM.md)

[Remove-AzureVM](./Remove-AzureVM.md)

[Start-AzureVM](./Start-AzureVM.md)

[Stop-AzureVM](./Stop-AzureVM.md)

[Update-AzureVM](./Update-AzureVM.md)


