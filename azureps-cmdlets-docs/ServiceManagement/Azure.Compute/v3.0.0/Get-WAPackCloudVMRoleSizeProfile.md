---
external help file: Microsoft.WindowsAzure.Commands.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 20573540-6BE0-4461-A0E8-325EF49DBC44
---

# Get-WAPackCloudVMRoleSizeProfile

## SYNOPSIS
Gets Cloud VM Role Size profile objects.

## SYNTAX

### Empty (Default)
```
Get-WAPackCloudVMRoleSizeProfile [-Profile <AzureSMProfile>] [<CommonParameters>]
```

### FromName
```
Get-WAPackCloudVMRoleSizeProfile [[-Name] <String>] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-WAPackCloudVMRoleSizeProfile** cmdlet gets Cloud VM Role size profile objects for virtual machines.

## EXAMPLES

### Example 1: Get a Cloud VM Role size profile by using a name
```
PS C:\> Get-WAPackCloudVMRoleSizeProfile -Name "Small"
```

This command gets the size profile named Small.

### Example 2: Get all Cloud VM Role size profiles
```
PS C:\> Get-WAPackCloudVMRoleSizeProfile
```

This command gets all the size profiles.

## PARAMETERS

### -Name
Specifies the name of a Cloud VM Role size profile.

```yaml
Type: String
Parameter Sets: FromName
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Profile
Specifies the Azure profile from which this cmdlet reads.
If you do not specify a profile, this cmdlet reads from the local default profile.

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

[Get-WAPackVM](./Get-WAPackVM.md)


