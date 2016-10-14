---
external help file: Microsoft.WindowsAzure.Commands.RemoteApp.dll-Help.xml
online version: .\Restart-AzureRemoteAppVM.md
schema: 2.0.0
---

# Get-AzureRemoteAppVM

## SYNOPSIS
Gets the virtual machines in an azure_2 RemoteApp collection.

## SYNTAX

```
Get-AzureRemoteAppVM [-CollectionName] <String> [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureRemoteAppVM** cmdlet gets the virtual machines created under an azure_2 RemoteApp collection for session hosting.

## EXAMPLES

### Example 1: Display the virtual machines in a collection
```
PS C:\>Get-AzureRemoteAppVM -CollectionName "Contoso"
```

This command displays the virtual machines used for session hosting in an azure_2 RemoteApp collection named Contoso.

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

## RELATED LINKS

[Restart-AzureRemoteAppVM](.\Restart-AzureRemoteAppVM.md)

