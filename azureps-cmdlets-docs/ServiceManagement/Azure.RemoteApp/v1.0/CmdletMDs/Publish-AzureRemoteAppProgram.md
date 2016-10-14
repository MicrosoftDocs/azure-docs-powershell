---
external help file: Microsoft.WindowsAzure.Commands.RemoteApp.dll-Help.xml
online version: .\Get-AzureRemoteAppProgram.md
schema: 2.0.0
---

# Publish-AzureRemoteAppProgram

## SYNOPSIS
Publishes an azure_2 RemoteApp program.

## SYNTAX

### App Id (Default)
```
Publish-AzureRemoteAppProgram [-CollectionName] <String> [-StartMenuAppId] <String> [-CommandLine <String>]
 [-DisplayName <String>] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

### App Path
```
Publish-AzureRemoteAppProgram [-CollectionName] <String> [-FileVirtualPath] <String> [-CommandLine <String>]
 [-DisplayName <String>] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Publish-AzureRemoteAppProgram** cmdlet publishes an azure_2 RemoteApp program, which makes it available to users of the azure_2 RemoteApp collection.

## EXAMPLES

### Example 1: Publish a program in a collection
```
PS C:\>Publish-AzureRemoteAppProgram -CollectionName "ContosoApps" -StartMenuAppId "a3732322-89a5-4cbc-9844-9634c74d337f" -DisplayName "Finance App"
```

This command publishes the program in the ContosoApps collection with the specified *StartMenuAppId* to add the program to the Start Menu.
The published app will have a display name of "Finance App".

## PARAMETERS

### -CollectionName
Specifies the name of the azure_2 RemoteApp collection.

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

### -CommandLine
Specifies command-line arguments for the program that this cmdlet publishes.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisplayName
Specifies the user-friendly display name of the azure_2 RemoteApp program.
Users see this as the name of the application.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FileVirtualPath
Specifies the path of the program within the template image of the program.

```yaml
Type: String
Parameter Sets: App Path
Aliases: 

Required: True
Position: 2
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

### -StartMenuAppId
Specifies a GUID that this cmdlet uses to add the program to the Start Menu.

```yaml
Type: String
Parameter Sets: App Id
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-AzureRemoteAppProgram](.\Get-AzureRemoteAppProgram.md)

[Unpublish-AzureRemoteAppProgram](.\Unpublish-AzureRemoteAppProgram.md)

