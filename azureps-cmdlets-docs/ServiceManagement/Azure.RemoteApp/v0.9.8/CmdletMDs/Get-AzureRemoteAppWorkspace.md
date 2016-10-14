---
external help file: Microsoft.WindowsAzure.Commands.RemoteApp.dll-Help.xml
online version: .\Set-AzureRemoteAppWorkspace.md
schema: 2.0.0
---

# Get-AzureRemoteAppWorkspace

## SYNOPSIS
Retrieves information about a RemoteApp workspace.

## SYNTAX

```
Get-AzureRemoteAppWorkspace [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureRemoteAppWorkspace** cmdlet retrieves information about an Azure RemoteApp workspace.

## EXAMPLES

### Example 1: Retrieve information about a RemoteApp workspace
```
PS C:\>Get-AzureRemoteAppWorkspace


ClientUrl                               EndUserFeedName

---------                               ---------------

https://www.remoteapp.windowsazure.com/ Contoso Work Applications
```

This command retrieves information about the RemoteApp workspace.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Set-AzureRemoteAppWorkspace](.\Set-AzureRemoteAppWorkspace.md)

