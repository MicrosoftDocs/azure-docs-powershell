---
external help file: Microsoft.WindowsAzure.Commands.RemoteApp.dll-Help.xml
online version: .\Get-AzureRemoteAppSession.md
schema: 2.0.0
---

# Disconnect-AzureRemoteAppSession

## SYNOPSIS
Disconnects a RemoteApp session.

## SYNTAX

```
Disconnect-AzureRemoteAppSession [-CollectionName] <String> [-UserUpn] <String> [-Profile <AzureProfile>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Disconnect-AzureRemoteAppSession** cmdlet disconnects a user's Azure RemoteApp session. 
The user's client disconnects from their RemoteApp session, but the user's programs continue to run.

## EXAMPLES

### Example 1: Disconnect a user's RemoteApp session
```
PS C:\>Disconnect-AzureRemoteAppSession -CollectionName "ContosoApps" -UserUpn "PattiFuller@contoso.com"
```

This command disconnects the RemoteApp session in the ContosoApps collection for the user whose UPN is PattiFuller@contoso.com.

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
Specifies the User Principal Name (UPN) of a user, for example PattiFuller@contoso.com.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
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

[Get-AzureRemoteAppSession](.\Get-AzureRemoteAppSession.md)

[Invoke-AzureRemoteAppSessionLogoff](.\Invoke-AzureRemoteAppSessionLogoff.md)

[Send-AzureRemoteAppSessionMessage](.\Send-AzureRemoteAppSessionMessage.md)

