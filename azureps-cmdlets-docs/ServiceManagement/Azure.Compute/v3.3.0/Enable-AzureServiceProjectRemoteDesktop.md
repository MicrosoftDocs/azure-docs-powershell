---
external help file: Microsoft.WindowsAzure.Commands.dll-Help.xml
ms.assetid: 163D2F00-E041-43A9-B077-9034F54B4F3D
online version: 
schema: 2.0.0
---

# Enable-AzureServiceProjectRemoteDesktop

## SYNOPSIS
Enables remote desktop access to a cloud service.

## SYNTAX

```
Enable-AzureServiceProjectRemoteDesktop [-Username] <String> [-Password] <SecureString> [-PassThru]
 [-Profile <AzureSMProfile>] [-InformationAction <ActionPreference>] [-InformationVariable <String>]
 [<CommonParameters>]
```

## DESCRIPTION
This topic describes the cmdlet in the 0.8.10 version of the Microsoft Azure PowerShell module.
To get the version of the module you're using, in the Azure PowerShell console, type `(Get-Module -Name Azure).Version`.

The **Enable-AzureServiceProjectRemoteDesktop** cmdlet enables Remote Desktop access to a cloud service.
You must publish the service using the **Publish-AzureServiceProject** cmdlet after enabling Remote Desktop access for the change to take effect.

## EXAMPLES

## PARAMETERS

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

### -PassThru
Returns an object representing the item with which you are working.
By default, this cmdlet does not generate any output.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Password
Specifies the password.

```yaml
Type: SecureString
Parameter Sets: (All)
Aliases: pwd

Required: True
Position: 1
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

### -Username
Specifies the user name to use when connecting to the role instance in Azure via the Remote Desktop Protocol (RDP).

```yaml
Type: String
Parameter Sets: (All)
Aliases: user

Required: True
Position: 0
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

[Disable-AzureServiceProjectRemoteDesktop](./Disable-AzureServiceProjectRemoteDesktop.md)

[Publish-AzureServiceProject](./Publish-AzureServiceProject.md)


