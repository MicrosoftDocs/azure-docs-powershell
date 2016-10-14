---
external help file: Microsoft.WindowsAzure.Commands.dll-Help.xml
online version: 
schema: 2.0.0
---

# Enable-AzureServiceProjectRemoteDesktop

## SYNOPSIS
Enables remote desktop access to a cloud service.

## SYNTAX

```
Enable-AzureServiceProjectRemoteDesktop [-Username] <String> [-Password] <SecureString> [-PassThru]
 [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
powershell_prelim

The **Enable-AzureServiceProjectRemoteDesktop** cmdlet enables Remote Desktop access to a cloud service.
You must publish the service using the **Publish-AzureServiceProject** cmdlet after enabling Remote Desktop access for the change to take effect.

## EXAMPLES

### 1:
```

```

## PARAMETERS

### -Username
Specifies the user name to use when connecting to the role instance in Azure via the Remote Desktop Protocol (RDP).

```yaml
Type: String
Parameter Sets: (All)
Aliases: user

Required: True
Position: 1
Default value: None
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
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru
@{Text=}

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

[Disable-AzureServiceProjectRemoteDesktop](.\Disable-AzureServiceProjectRemoteDesktop.md)

[Publish-AzureServiceProject](.\Publish-AzureServiceProject.md)

