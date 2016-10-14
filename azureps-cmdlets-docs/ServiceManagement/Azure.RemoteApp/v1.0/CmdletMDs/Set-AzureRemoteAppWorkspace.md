---
external help file: Microsoft.WindowsAzure.Commands.RemoteApp.dll-Help.xml
online version: .\Get-AzureRemoteAppWorkspace.md
schema: 2.0.0
---

# Set-AzureRemoteAppWorkspace

## SYNOPSIS
Sets the properties of an azure_2 RemoteApp workspace.

## SYNTAX

```
Set-AzureRemoteAppWorkspace [-WorkspaceName] <String> [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-AzureRemoteAppWorkspace** cmdlet sets the properties of an azure_2 RemoteApp workspace.

## EXAMPLES

### Example 1: Set the workspace name
```
PS C:\>Set-AzureRemoteAppWorkspace -WorkspaceName "Contoso Work Applications"
TrackingId
----------
12345
```

This command sets the azure_2 RemoteApp workspace name to Contoso Work Applications.

## PARAMETERS

### -WorkspaceName
Specifies the name of the azure_2 RemoteApp workspace.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES
* All azure_2 RemoteApp collections for a specified subscription exist within a shared workspace.

## RELATED LINKS

[Get-AzureRemoteAppWorkspace](.\Get-AzureRemoteAppWorkspace.md)

