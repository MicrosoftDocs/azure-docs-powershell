---
external help file: Microsoft.WindowsAzure.Commands.dll-Help.xml
online version: .\New-WAPackVM.md
schema: 2.0.0
---

# Get-WAPackVM

## SYNOPSIS
Gets virtual machine objects.

## SYNTAX

### Empty (Default)
```
Get-WAPackVM [-Profile <AzureSMProfile>] [<CommonParameters>]
```

### FromName
```
Get-WAPackVM [[-Name] <String>] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

### FromId
```
Get-WAPackVM [[-ID] <Guid>] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
These topics are deprecated and will be removed in the future.
For the updated topics, see  Azure WAPack Cmdletshttp://msdn.microsoft.com/library/dn776450.aspx.
This topic describes the cmdlet in the 0.8.1 version of the Microsoft Azure PowerShell module.
To find out the version of the module you're using, from the Azure PowerShell console, type (get-module azure).version.

The **Get-WAPackVM** cmdlet gets virtual machine objects.

## EXAMPLES

### Example 1: Get a virtual machine by using a name
```
PS C:\>Get-WAPackVM -Name "ContosoV126"
```

This command gets the virtual machine named ContosoV126.

### Example 2: Get a virtual machine by using an ID
```
PS C:\>Get-WAPackVM -Id 66242D17-189F-480D-87CF-8E1D749998C8
```

This command gets the virtual machine that has the specified ID.

### Example 3: Get all virtual machines
```
PS C:\>Get-WAPackVM
```

This command gets all virtual machines.

## PARAMETERS

### -ID
Specifies the unique ID of a virtual machine.

```yaml
Type: Guid
Parameter Sets: FromId
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies the name of a virtual machine.

```yaml
Type: String
Parameter Sets: FromName
Aliases: 

Required: False
Position: 1
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

[New-WAPackVM](.\New-WAPackVM.md)

[Remove-WAPackVM](.\Remove-WAPackVM.md)

[Restart-WAPackVM](.\Restart-WAPackVM.md)

[Resume-WAPackVM](.\Resume-WAPackVM.md)

[Set-WAPackVM](.\Set-WAPackVM.md)

[Start-WAPackVM](.\Start-WAPackVM.md)

[Stop-WAPackVM](.\Stop-WAPackVM.md)

[Suspend-WAPackVM](.\Suspend-WAPackVM.md)

[Get-WAPackVMOSDisk](.\Get-WAPackVMOSDisk.md)

