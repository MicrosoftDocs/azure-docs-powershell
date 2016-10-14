---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.dll-Help.xml
online version: .\Get-AzureVMDiagnosticsExtension.md
schema: 2.0.0
---

# Set-AzureVMDiagnosticsExtension

## SYNOPSIS

## SYNTAX

### SetDiagnosticsExtension (Default)
```
Set-AzureVMDiagnosticsExtension [-DiagnosticsConfigurationPath] <String>
 [-StorageContext] <AzureStorageContext> [[-Version] <String>] [-Disable] -VM <IPersistentVM>
 [-Profile <AzureProfile>] [<CommonParameters>]
```

### SetDiagnosticsWithReferenceExtension
```
Set-AzureVMDiagnosticsExtension [-DiagnosticsConfigurationPath] <String>
 [-StorageContext] <AzureStorageContext> [[-Version] <String>] [-Disable] [[-ReferenceName] <String>]
 -VM <IPersistentVM> [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION

## EXAMPLES

### 1:
```

```

## PARAMETERS

### -DiagnosticsConfigurationPath
Specifies a path for the diagnostics configuration.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StorageContext
Specifies an Azure storage context.

```yaml
Type: AzureStorageContext
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Version
Specifies the extension version as a string.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Disable
Indicates that this cmdlet disables the diagnostics extension on the virtual machine.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VM
Specifies the persistent virtual machine object.

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

### -ReferenceName
Specifies the reference name for the diagnostics extension.

```yaml
Type: String
Parameter Sets: SetDiagnosticsWithReferenceExtension
Aliases: 

Required: False
Position: 4
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Profile
Specifies the Azure profile from which this cmdlet reads.
If you do not specify a profile, this cmdlet reads from the local default profile.

```yaml
Type: AzureProfile
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

[Get-AzureVMDiagnosticsExtension](.\Get-AzureVMDiagnosticsExtension.md)

[Remove-AzureVMDiagnosticsExtension](.\Remove-AzureVMDiagnosticsExtension.md)

