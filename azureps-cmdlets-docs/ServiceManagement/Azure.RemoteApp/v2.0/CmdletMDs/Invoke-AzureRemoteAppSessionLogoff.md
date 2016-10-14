---
external help file: Microsoft.WindowsAzure.Commands.RemoteApp.dll-Help.xml
online version: .\Add-AzureRemoteAppUser.md
schema: 2.0.0
---

# Invoke-AzureRemoteAppSessionLogoff

## SYNOPSIS
Logs off an Azure RemoteApp session immediately.

## SYNTAX

```
Invoke-AzureRemoteAppSessionLogoff [-CollectionName] <String> [-UserUpn] <String> [-Profile <AzureSMProfile>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Invoke-AzureRemoteAppSessionLogoff** cmdlet immediately logs off a user from a remote session running in Azure RemoteApp.

## EXAMPLES

### Example 1: Log off a user
```
PS C:\>Invoke-AzureRemoteAppSessionLogoff -CollectionName ContosoApps -UserUpn PattiFuller@contoso.com
```

This command logs off the user whose UPN is PattiFuller@contoso.com.

## PARAMETERS

### -CollectionName
Specifies the name of the Azure RemoteApp collection.

```yaml
Type: String
Parameter Sets: (All)
Aliases: Name

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -UserUpn
Specifes the user Principal Name (UPN) of a user, for example, PattiFuller@contoso.com.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm
Prompts you for confirmation before running the cmdlet.Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Add-AzureRemoteAppUser](.\Add-AzureRemoteAppUser.md)

[Disconnect-AzureRemoteAppSession](.\Disconnect-AzureRemoteAppSession.md)

[Get-AzureRemoteAppSession](.\Get-AzureRemoteAppSession.md)

