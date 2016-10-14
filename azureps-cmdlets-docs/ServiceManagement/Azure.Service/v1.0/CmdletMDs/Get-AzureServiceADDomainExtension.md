---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.dll-Help.xml
online version: .\Remove-AzureServiceADDomainExtension.md
schema: 2.0.0
---

# Get-AzureServiceADDomainExtension

## SYNOPSIS
Gets the cloud service Active Directory (AD) domain extension that applies to all roles or to named roles at a specified deployment slot.

## SYNTAX

```
Get-AzureServiceADDomainExtension [[-ServiceName] <String>] [[-Slot] <String>] [-Profile <AzureSMProfile>]
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureServiceADDomainExtension** cmdlet gets the cloud service AD domain extension that applies to all roles or named roles at a specified deployment slot.

## EXAMPLES

### Example 1: Get the AD domain extension for a specified service
```
PS C:\>Get-AzureServiceADDomainExtension -ServiceName $Svc
```

This command gets the AD domain extension for the service specified in $Svc.

## PARAMETERS

### -ServiceName
Specifies the azure_2 service name of the deployment.

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

### -Slot
Specifies the deployment environment.
psdx_paramvalues Production or Staging.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
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

## NOTES

## RELATED LINKS

[Remove-AzureServiceADDomainExtension](.\Remove-AzureServiceADDomainExtension.md)

[Set-AzureServiceADDomainExtension](.\Set-AzureServiceADDomainExtension.md)

