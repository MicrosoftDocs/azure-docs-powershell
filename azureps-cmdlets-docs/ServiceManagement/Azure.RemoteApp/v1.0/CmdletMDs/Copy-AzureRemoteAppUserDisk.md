---
external help file: Microsoft.WindowsAzure.Commands.RemoteApp.dll-Help.xml
online version: .\Remove-AzureRemoteAppUserDisk.md
schema: 2.0.0
---

# Copy-AzureRemoteAppUserDisk

## SYNOPSIS
Copies the user disk of a user from one azure_2 RemoteApp collection to another.

## SYNTAX

```
Copy-AzureRemoteAppUserDisk [-SourceCollectionName] <String> [-DestinationCollectionName] <String>
 [-UserUpn] <String> [-OverwriteExistingUserDisk] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Copy-AzureRemoteAppUserDisk** cmdlet copies the user disk of a user from one azure_2 RemoteApp collection to another.

## EXAMPLES

### Example 1: Copy a user disk
```
PS C:\>Copy-AzureRemoteAppUserDisk -DestinationCollectionName "Contoso02" -SourceCollectionName "Contoso01" -UserUpn "PattiFuller@contoso.com" -OverwriteExistingUserDisk
```

This command copies the user disk of an azure_2 Active Directory user who has the UPN PattiFuller@contoso.com from the collection Contoso01 to the collection Contoso02.
If a user disk for PattiFuller@contoso.com already exists on Contoso02, this command overwrites it.

## PARAMETERS

### -SourceCollectionName
Specifies the name of the source azure_2 RemoteApp collection.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DestinationCollectionName
Specifies the name of the destination azure_2 RemoteApp collection.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -UserUpn
Specifies the user principal name (UPN) of the user for whom this cmdlet copies the disk.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -OverwriteExistingUserDisk
Indicates that this cmdlet overwrites an existing user disk.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
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

## NOTES

## RELATED LINKS

[Remove-AzureRemoteAppUserDisk](.\Remove-AzureRemoteAppUserDisk.md)

