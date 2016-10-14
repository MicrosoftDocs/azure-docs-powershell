---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.dll-Help.xml
online version: .\Remove-AzureServiceDiagnosticsExtension.md
schema: 2.0.0
---

# Get-AzureServiceDiagnosticsExtension

## SYNOPSIS
Gets the cloud service diagnostics extension applied on all roles or named roles at a certain deployment slot.

## SYNTAX

```
Get-AzureServiceDiagnosticsExtension [[-ServiceName] <String>] [[-Slot] <String>] [-Profile <AzureProfile>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureServiceDiagnosticsExtension** cmdlet gets the cloud service diagnostics extension applied on all roles or named roles at a certain deployment slot.

## EXAMPLES

### Example 1: Enable a diagnostic extension
```
PS C:\>Get-AzureServiceDiagnosticsExtension -ServiceName $Svc
```

This command enables a diagnostic service across all roles.

## PARAMETERS

### -ServiceName
Specifies the Azure service name of the deployment.

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

### -Slot
Specifies the environment of the deployment to modify.
The acceptable values for this parameter are: Production or Staging.

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

[Remove-AzureServiceDiagnosticsExtension](.\Remove-AzureServiceDiagnosticsExtension.md)

[Set-AzureServiceDiagnosticsExtension](.\Set-AzureServiceDiagnosticsExtension.md)

