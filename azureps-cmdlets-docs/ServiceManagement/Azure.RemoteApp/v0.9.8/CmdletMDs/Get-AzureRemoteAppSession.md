---
external help file: Microsoft.WindowsAzure.Commands.RemoteApp.dll-Help.xml
online version: .\Disconnect-AzureRemoteAppSession.md
schema: 2.0.0
---

# Get-AzureRemoteAppSession

## SYNOPSIS
Lists all active and disconnected RemoteApp sessions for a RemoteApp collection.

## SYNTAX

```
Get-AzureRemoteAppSession [-CollectionName] <String> [[-UserUpn] <String>] [-Profile <AzureProfile>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureRemoteAppSession** cmdlet lists all active and disconnected RemoteApp sessions for an Azure RemoteApp collection.

## EXAMPLES

### Example 1: List all the sessions in a RemoteApp collection
```
PS C:\>Get-AzureRemoteAppSession -CollectionName "ContosoApps"
```

This command lists all sessions in the RemoteApp collection named ContosoApps.

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
Specifies the user Principal Name (UPN) of a user for which to get RemoteApp sessions.
For example, the UPN can be in the following format: PattiFuller@contoso.com.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Disconnect-AzureRemoteAppSession](.\Disconnect-AzureRemoteAppSession.md)

[Invoke-AzureRemoteAppSessionLogoff](.\Invoke-AzureRemoteAppSessionLogoff.md)

[Send-AzureRemoteAppSessionMessage](.\Send-AzureRemoteAppSessionMessage.md)

