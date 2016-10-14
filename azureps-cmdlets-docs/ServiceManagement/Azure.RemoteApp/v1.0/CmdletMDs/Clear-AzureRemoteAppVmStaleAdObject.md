---
external help file: Microsoft.WindowsAzure.Commands.RemoteApp.dll-Help.xml
online version: .\Get-AzureRemoteAppVmStaleAdObject.md
schema: 2.0.0
---

# Clear-AzureRemoteAppVmStaleAdObject

## SYNOPSIS
Removes objects in azure_2 Active Directory that are associated with azure_2 RemoteApp virtual machines that no longer exist.

## SYNTAX

```
Clear-AzureRemoteAppVmStaleAdObject [-CollectionName] <String> [[-Credential] <PSCredential>]
 [-Profile <AzureSMProfile>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Clear-AzureRemoteAppVmStaleAdObject** cmdlet removes objects in azure_2 Active Directory that are associated with azure_2 RemoteApp virtual machines that no longer exist.
You must use credentials that have rights to remove azure_2 Active Directory objects.
If you specify the *Verbose* common parameter, this cmdlet displays the name of each object that it deletes.

## EXAMPLES

### Example 1: Clear stale objects for a collection
```
PS C:\>$AdminCredentials = Get-Credential
PS C:\> Clear-AzureRemoteAppVmStaleAdObject -CollectionName "Contoso" -Credential $AdminCredentials
```

The first command prompts you for a user name and password by using **Get-Credential**.
The command stores the results in the $AdminCredentials variable.

The second command clears the stale objects for the collection named Contoso.
The command uses the credentials stored in $AdminCredentials variable.
In order for the command to succeed, those credentials must have appropriate rights.

## PARAMETERS

### -CollectionName
Specifies the name of the azure_2 RemoteApp collection.

```yaml
Type: String
Parameter Sets: (All)
Aliases: Name

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Confirm
psdx_confirmdesc

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

### -Credential
Specifies a credential that has rights to perform this action.
To obtain a **Credential** object, use the Get-Credential cmdlet.
If you do not specify this parameter, this cmdlet uses the current user credentials.

```yaml
Type: PSCredential
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: False
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

### -WhatIf
psdx_whatifdesc

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-AzureRemoteAppVmStaleAdObject](.\Get-AzureRemoteAppVmStaleAdObject.md)

