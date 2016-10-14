---
external help file: Microsoft.WindowsAzure.Commands.RemoteApp.dll-Help.xml
online version: .\Clear-AzureRemoteAppVmStaleAdObject.md
schema: 2.0.0
---

# Get-AzureRemoteAppVmStaleAdObject

## SYNOPSIS
Gets objects in azure_2 Active Directory that are associated with azure_2 RemoteApp virtual machines that no longer exist.

## SYNTAX

```
Get-AzureRemoteAppVmStaleAdObject [-CollectionName] <String> [[-Credential] <PSCredential>]
 [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureRemoteAppVmStaleAdObject** cmdlet gets objects in azure_2 Active Directory that are associated with azure_2 RemoteApp virtual machines that no longer exist.
This cmdlet displays the name of each object that it gets.

## EXAMPLES

### Example 1: Get stale objects for a collection
```
PS C:\>Clear-AzureRemoteAppVmStaleAdObject -CollectionName "Contoso"
```

This second command gets the stale objects for the collection named Contoso.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### String

## NOTES

## RELATED LINKS

[Clear-AzureRemoteAppVmStaleAdObject](.\Clear-AzureRemoteAppVmStaleAdObject.md)

