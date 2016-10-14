---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.dll-Help.xml
online version: .\Get-AzureService.md
schema: 2.0.0
---

# New-AzureService

## SYNOPSIS
Creates an azure_2 service.

## SYNTAX

### ParameterSetAffinityGroup (Default)
```
New-AzureService [-ServiceName] <String> [-AffinityGroup] <String> [[-Label] <String>]
 [[-Description] <String>] [[-ReverseDnsFqdn] <String>] [-Profile <AzureSMProfile>]
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [<CommonParameters>]
```

### ParameterSetLocation
```
New-AzureService [-ServiceName] <String> [-Location] <String> [[-Label] <String>] [[-Description] <String>]
 [[-ReverseDnsFqdn] <String>] [-Profile <AzureSMProfile>] [-InformationAction <ActionPreference>]
 [-InformationVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **New-AzureService** cmdlet creates a new azure_2 service in the current subscription.

## EXAMPLES

### Example 1: Create a service
```
PS C:\>New-AzureService -ServiceName "MySvc01" -Label "MyTestService" -Location "South Central US"
```

This command creates a new service named MySvc01 in the South Central US location.

### Example 2: Create a service in an affinity group
```
PS C:\>New-AzureService -ServiceName "MySvc01" -AffinityGroup NorthRegion
```

This command creates a new service named MySvc01 using the NorthRegion affinity group.

## PARAMETERS

### -ServiceName
Specifies the name of the new service.
The name must be unique to the subscription.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -AffinityGroup
Specifies the affinity group associated with the subscription.
If you do not specify the *Location* parameter, an affinity group is required.

```yaml
Type: String
Parameter Sets: ParameterSetAffinityGroup
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Label
Specifies a label for the service.
The label may be up to 100 characters in length.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Description
Specifies a description for the service.
The description may be up to 1024 characters in length.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ReverseDnsFqdn
Specifies the fully qualified domain name for reverse DNS.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 4
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

### -InformationAction
@{Text=}```yaml
Type: ActionPreference
Parameter Sets: (All)
Aliases: infa

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InformationVariable
@{Text=}```yaml
Type: String
Parameter Sets: (All)
Aliases: iv

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Location
Specifies the location for the service.
A location is required if there isn't a specified Affinity Group.

```yaml
Type: String
Parameter Sets: ParameterSetLocation
Aliases: 

Required: True
Position: 1
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

[Get-AzureService](.\Get-AzureService.md)

[Set-AzureService](.\Set-AzureService.md)

