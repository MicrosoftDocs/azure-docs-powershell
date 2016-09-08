---
external help file: SMAzure_Compute.xml
online version: 
schema: 2.0.0
---

# Enable-AzureServiceProjectRemoteDesktop
## SYNOPSIS
Enables remote desktop access to a cloud service.

## SYNTAX

```
Enable-AzureServiceProjectRemoteDesktop [-Username] <String> [-Password] <SecureString> [-PassThru]
```

## DESCRIPTION
This topic describes the cmdlet in the 0.8.10 version of the Microsoft Azure PowerShell module.
To get the version of the module you're using, in the Azure PowerShell console, type (Get-Module -Name Azure).Version.

The Enable-AzureServiceProjectRemoteDesktop cmdlet enables Remote Desktop access to a cloud service.
You must publish the service using the Publish-AzureServiceProject cmdlet after enabling Remote Desktop access for the change to take effect.

## EXAMPLES

### 1:
```

```

## PARAMETERS

### -PassThru
@{Text=}

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
Default value: 
Accept pipeline input: False
Accept wildcard characters: False
```

### -Password
@{Text=}

```yaml
Type: SecureString
Parameter Sets: (All)
Aliases: pwd

Required: True
Position: 2
Default value: 
Accept pipeline input: False
Accept wildcard characters: False
```

### -Username
Specifies the user name to use when connecting to the role instance in Azure via the Remote Desktop Protocol (RDP).

```yaml
Type: String
Parameter Sets: (All)
Aliases: user

Required: True
Position: 1
Default value: 
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Disable-AzureServiceProjectRemoteDesktop](848333f0-4687-4e7c-a775-1c6f148aa111)

[Publish-AzureServiceProject](4c0c0966-919e-49a6-9d38-c3c97355e281)

