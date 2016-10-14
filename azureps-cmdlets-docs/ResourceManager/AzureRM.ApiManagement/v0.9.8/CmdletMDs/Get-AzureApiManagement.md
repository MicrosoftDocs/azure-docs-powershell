---
external help file: Microsoft.Azure.Commands.ApiManagement.dll-Help.xml
online version: .\Backup-AzureApiManagement.md
schema: 2.0.0
---

# Get-AzureApiManagement

## SYNOPSIS
Gets a list or a particular API Management Service description.

## SYNTAX

### All In Subscription (Default)
```
Get-AzureApiManagement [-Profile <AzureProfile>] [<CommonParameters>]
```

### All In Resource Group
```
Get-AzureApiManagement -ResourceGroupName <String> [-Profile <AzureProfile>] [<CommonParameters>]
```

### Specific API Management Service
```
Get-AzureApiManagement -ResourceGroupName <String> -Name <String> [-Profile <AzureProfile>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureApiManagement** cmdlet gets a list of all API Management services under subscription or specified resource group or a particular API Management.

## EXAMPLES

### Example 1: Get all API Management services
```
PS C:\>Get-AzureApiManagement
```

This command gets all API Management services within a subscription.

### Example 2: Get all API Management services by a specific name
```
PS C:\>Get-AzureApiManagement -ResourceGroupName "ContosoGroup" -Name "ContosoApi"
```

This command gets all API Management service by name.

## PARAMETERS

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

### -ResourceGroupName
Specifies the name of the resource group under in which this cmdlet gets the API Management service.

```yaml
Type: String
Parameter Sets: All In Resource Group, Specific API Management Service
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies the name of API Management service.

```yaml
Type: String
Parameter Sets: Specific API Management Service
Aliases: 

Required: True
Position: Named
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

[Backup-AzureApiManagement](.\Backup-AzureApiManagement.md)

[New-AzureApiManagement](.\New-AzureApiManagement.md)

[Remove-AzureApiManagement](.\Remove-AzureApiManagement.md)

[Restore-AzureApiManagement](.\Restore-AzureApiManagement.md)

