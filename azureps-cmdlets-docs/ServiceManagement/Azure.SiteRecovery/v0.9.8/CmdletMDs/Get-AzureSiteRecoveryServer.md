---
external help file: Microsoft.Azure.Commands.RecoveryServices.dll-Help.xml
online version: cb922d26-cb13-483d-866f-a7c11f088689
schema: 2.0.0
---

# Get-AzureSiteRecoveryServer

## SYNOPSIS
Gets information about an Azure Site Recovery server.

## SYNTAX

### Default (Default)
```
Get-AzureSiteRecoveryServer [-Profile <AzureProfile>] [<CommonParameters>]
```

### ById
```
Get-AzureSiteRecoveryServer -Id <String> [-Profile <AzureProfile>] [<CommonParameters>]
```

### ByName
```
Get-AzureSiteRecoveryServer -Name <String> [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureSiteRecoveryServer** cmdlet gets information about the Microsoft Azure Site Recovery server for the current Azure Site Recovery vault.

## EXAMPLES

### Example 1: Get information about an Azure Site Recovery server
```
PS C:\>Get-AzureSiteRecoveryServer
ID              : cd7dec80-1144-4531-9ab3-888b8ab39bee
Name            : server1.contoso.com
LastHeartbeat   : 9/23/2014 3:51:22 PM
ProviderVersion : 3.5.520.0
ServerVersion   : 3.2.7634.0

ID              : f5e713fe-5b6d-4641-9690-6fe74c976b8e
Name            : Server2.contoso.com
LastHeartbeat   : 8/13/2014 2:28:58 PM
ProviderVersion : 3.5
ServerVersion   : 3.2.7510.0
```

This command gets information about an Azure Site Recovery server.

## PARAMETERS

### -Id
Specifies the ID of the server about which to get information.

```yaml
Type: String
Parameter Sets: ById
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of the server about which to get information.

```yaml
Type: String
Parameter Sets: ByName
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Profile
Specifies an Azure profile.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

