---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.dll-Help.xml
online version: .\Set-AzureServiceRemoteDesktopExtension.md
schema: 2.0.0
---

# Remove-AzureServiceRemoteDesktopExtension

## SYNOPSIS
Removes the cloud service remote desktop extension applied on all roles or named roles at a specified deployment slot.

## SYNTAX

### RemoveByRoles (Default)
```
Remove-AzureServiceRemoteDesktopExtension [[-ServiceName] <String>] [[-Slot] <String>] [[-Role] <String[]>]
 [-Profile <AzureProfile>] [<CommonParameters>]
```

### RemoveAllRoles
```
Remove-AzureServiceRemoteDesktopExtension [[-ServiceName] <String>] [[-Slot] <String>]
 [-UninstallConfiguration] [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-AzureServiceRemoteDesktopExtension** cmdlet removes the cloud service remote desktop extension applied on all roles or named roles at a certain deployment slot.

## EXAMPLES

### Example 1: Remove the remote desktop extension
```
PS C:\>Remove-AzureServiceRemoteDesktopExtension -ServiceName $svc
```

This command removes the remote desktop extension.

### Example 2: Remove the remote desktop extension from a specified role
```
PS C:\>Remove-AzureServiceRemoteDesktopExtension -ServiceName $svc -Role "WebRole1"
```

This command removes the remote desktop extension from a specified role.

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
Supported values are "Production" or "Staging".

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

### -Role
Specifies an optional array of roles to specify the remote desktop configuration for.
If not specified the remote desktop configuration is applied as the default configuration for all roles.

```yaml
Type: String[]
Parameter Sets: RemoveByRoles
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -UninstallConfiguration
Specifies that this cmdlet uninstalls all RDP configurations from the cloud service.

```yaml
Type: SwitchParameter
Parameter Sets: RemoveAllRoles
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: False
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

[Set-AzureServiceRemoteDesktopExtension](.\Set-AzureServiceRemoteDesktopExtension.md)

