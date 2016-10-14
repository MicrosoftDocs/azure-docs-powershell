---
external help file: Microsoft.WindowsAzure.Commands.RemoteApp.dll-Help.xml
online version: .\Publish-AzureRemoteAppProgram.md
schema: 2.0.0
---

# Get-AzureRemoteAppProgram

## SYNOPSIS
Retrieves the properties of one or more published RemoteApp programs for a collection.

## SYNTAX

### FilterByName (Default)
```
Get-AzureRemoteAppProgram [-CollectionName] <String> [[-RemoteAppProgram] <String>] [-Profile <AzureProfile>]
 [<CommonParameters>]
```

### FilterByAlias
```
Get-AzureRemoteAppProgram [-CollectionName] <String> [[-Alias] <String>] [-Profile <AzureProfile>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureRemoteAppProgram** cmdlet retrieves the properties of one or more published Azure RemoteApp programs for a collection.

## EXAMPLES

### Example 1: Retrieve the properties of a RemoteApp program
```
PS C:\>Get-AzureRemoteAppProgram -CollectionName "ContosoApps" -RemoteAppProgram "Finance App"

Alias                : edc85816-4b9e-4284-b3dc-faedb505f5d9

AvailableToUsers     : True

CommandLineArguments : 

IconPngUris          : Microsoft.Azure.Management.RemoteApp.Models.IconPngUrisType

IconUri              : https://liverdcxstorage.blob.core.windows.net/icons/12345678-1234-1234-1234-123412341234.ico?se=2015-03-01T17%3A29%3A51Z&amp;amp;sr=b&amp;amp;sp=r&amp;amp;sig=abcdCCavbcF%2asY4RascaBauishCasd2FasdBHtasd2BPasdi5dasdD

Name                 : Contoso Finance

Status               : Published

VirtualPath          : %SYSTEMDRIVE%\Program Files (x86)\Contoso Finance\Finance.exe
```

This command displays the properties of a RemoteApp program.
The program, named Finance App, is in the RemoteApp collection named ContosoApps.

## PARAMETERS

### -Alias
Specifies the alias of the program for which to retrieve properties.

```yaml
Type: String
Parameter Sets: FilterByAlias
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

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

### -RemoteAppProgram
Specifies the name of the program for which to retrieve properties.

```yaml
Type: String
Parameter Sets: FilterByName
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

[Publish-AzureRemoteAppProgram](.\Publish-AzureRemoteAppProgram.md)

[Unpublish-AzureRemoteAppProgram](.\Unpublish-AzureRemoteAppProgram.md)

