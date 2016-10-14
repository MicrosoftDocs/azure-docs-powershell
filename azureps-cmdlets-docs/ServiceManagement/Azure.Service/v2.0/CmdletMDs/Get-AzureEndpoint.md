---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.dll-Help.xml
online version: .\Add-AzureEndpoint.md
schema: 2.0.0
---

# Get-AzureEndpoint

## SYNOPSIS
Gets information about the endpoints that are assigned to an Azure virtual machine.

## SYNTAX

```
Get-AzureEndpoint [[-Name] <String>] -VM <IPersistentVM> [-Profile <AzureSMProfile>]
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureEndpoint** cmdlet gets information about the endpoints that are assigned to an Azure virtual machine.

## EXAMPLES

### Example 1: Get endpoint information for a virtual machine
```
PS C:\>Get-AzureVM -ServiceName "ContosoService" -Name "VirtualMachine12" | Get-AzureEndpoint
```

This command retrieves the configuration of a virtual machine named VirtualMachine12 by using the Get-AzureVM cmdlet.
The command passes it to the current cmdlet by using the pipeline operator.
This cmdlet gets endpoint information for that virtual machine.

## PARAMETERS

### -Name
Specifies the name of the endpoint for which this cmdlet gets information.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VM
Specifies the virtual machine from which this cmdlet gets endpoint information.

```yaml
Type: IPersistentVM
Parameter Sets: (All)
Aliases: InputObject

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
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
@{Text=}```yaml
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
@{Text=}```yaml
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

[Add-AzureEndpoint](.\Add-AzureEndpoint.md)

[Get-AzureVM](.\Get-AzureVM.md)

[Remove-AzureEndpoint](.\Remove-AzureEndpoint.md)

[Set-AzureEndpoint](.\Set-AzureEndpoint.md)

