---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.dll-Help.xml
online version: .\New-AzureService.md
schema: 2.0.0
---

# Get-AzureService

## SYNOPSIS
Returns an object with information about the cloud services for the current subscription.

## SYNTAX

```
Get-AzureService [[-ServiceName] <String>] [-Profile <AzureSMProfile>] [-InformationAction <ActionPreference>]
 [-InformationVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureService** cmdlet returns a list object with all of the azure_2 cloud services associated with the current subscription.
If you specify the *ServiceName* parameter, **Get-AzureService** returns information on only the matching service.

## EXAMPLES

### Example 1: Get information about all services
```
PS C:\>Get-AzureService
```

This command returns an object that contains information about all of the azure_2 services associated with the current subscription.

### Example 2: Get information about a specified service
```
PS C:\>Get-AzureService -ServiceName $MySvc
```

This command returns information about the $MySvc service.

### Example 3: Display available methods and properties
```
PS C:\>Get-AzureService | Get-Member
```

This command displays the properties and methods that are available from the **Get-AzureService** cmdlet.

## PARAMETERS

### -ServiceName
Specifies the name of a service on which to return information.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### HostedServiceContext

## NOTES

## RELATED LINKS

[New-AzureService](.\New-AzureService.md)

[Set-AzureService](.\Set-AzureService.md)

