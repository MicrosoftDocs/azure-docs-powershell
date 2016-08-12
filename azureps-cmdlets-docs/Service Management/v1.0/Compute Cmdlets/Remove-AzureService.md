---
external help file: SMAzure_Compute.xml
online version: 
schema: 2.0.0
---

# Remove-AzureService
## SYNOPSIS
Removes the current cloud service.

## SYNTAX

```
Remove-AzureService [[-ServiceName] <String>] [[-Subscription] <String>] [-Force] [-PassThru] [-Confirm]
 [-WhatIf]
```

## DESCRIPTION
This topic describes the cmdlet in the 0.8.10 version of the Microsoft Azure PowerShell module.
To get the version of the module you're using, in the Azure PowerShell console, type (Get-Module -Name Azure).Version.

The Remove-AzureService cmdlet stops and removes the current cloud service, or the service matching the specified service and subscription name.

## EXAMPLES

### 1:
```

```

## PARAMETERS

### -Force
Removes the service without prompting for confirmation.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
Default value: 
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru
@{Text=}

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: 4
Default value: 
Accept pipeline input: False
Accept wildcard characters: False
```

### -ServiceName
Specifies the name of the service to be removed.
If the command is run from a service directory and no name is specified, uses the current service name.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: 
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Subscription
Specifies the name of the subscription that was used to host the service.
If no subscription is specified, uses the subscription specified in the last call to Set-AzureDeploymentSubscription.
If no subscription has ever been specified, uses the first subscription in the current Windows Azure publish profile.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: 
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Confirm
Prompts you for confirmation before running the cmdlet.Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Publish-AzureServiceProject](4c0c0966-919e-49a6-9d38-c3c97355e281)

[Stop-AzureService](82d56ef9-9651-4224-9ba0-498750f6f551)

[Start-AzureService](56e58937-4763-467c-a98c-c89ae4326e84)

