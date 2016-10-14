---
external help file: Microsoft.WindowsAzure.Commands.RemoteApp.dll-Help.xml
online version: .\Add-AzureRemoteAppUser.md
schema: 2.0.0
---

# Get-AzureRemoteAppUser

## SYNOPSIS
Lists the users in an Azure RemoteApp collection.

## SYNTAX

```
Get-AzureRemoteAppUser [-CollectionName] <String> [[-UserUpn] <String>] [-Profile <AzureProfile>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureRemoteAppUser** cmdlet lists the users in an Azure RemoteApp collection.

## EXAMPLES

### Example 1: List the users of a RemoteApp collection
```
PS C:\>Get-AzureRemoteAppUser -CollectionName "Contoso"
```

This command lists the users who have access to the RemoteApp collection named Contoso.

## PARAMETERS

### -CollectionName
Specifies the name of the RemoteApp collection.

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

### -UserUpn
Specifies the User Principal Name (UPN) of a user for which to list information.
For example, PattiFuller@contoso.com.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
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

[Get-AzureRemoteAppSession](.\Get-AzureRemoteAppSession.md)

[Remove-AzureRemoteAppUser](.\Remove-AzureRemoteAppUser.md)

