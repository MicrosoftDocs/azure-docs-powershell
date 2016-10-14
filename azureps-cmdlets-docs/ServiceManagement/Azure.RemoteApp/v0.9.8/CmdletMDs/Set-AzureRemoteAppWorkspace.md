---
external help file: Microsoft.WindowsAzure.Commands.RemoteApp.dll-Help.xml
online version: .\Get-AzureRemoteAppWorkspace.md
schema: 2.0.0
---

# Set-AzureRemoteAppWorkspace

## SYNOPSIS
Sets the properties of an Azure RemoteApp workspace.

## SYNTAX

```
Set-AzureRemoteAppWorkspace [-WorkspaceName] <String> [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-AzureRemoteAppWorkspace** cmdlet sets the properties of an Azure RemoteApp workspace.

## EXAMPLES

### Example 1: Set the RemoteApp workspace name
```
PS C:\>Set-AzureRemoteAppWorkspace -WorkspaceName "Contoso Work Applications"

TrackingId

----------

12345
```

This command sets the Azure RemoteApp workspace name to Contoso Work Applications.

## PARAMETERS

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

### -WorkspaceName
Specifies the name of the Azure RemoteApp workspace.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES
* All RemoteApp collections for a specified subscription exist within a shared workspace.

## RELATED LINKS

[Get-AzureRemoteAppWorkspace](.\Get-AzureRemoteAppWorkspace.md)

