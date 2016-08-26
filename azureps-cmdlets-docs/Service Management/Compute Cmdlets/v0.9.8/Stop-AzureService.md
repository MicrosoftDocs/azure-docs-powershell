---
external help file: SMAzure_Compute.xml
online version: 
schema: 2.0.0
---

# Stop-AzureService
## SYNOPSIS
Stops the current hosted service.

## SYNTAX

```
Stop-AzureService [[-ServiceName] <String>] [[-Slot] <String>] [[-Subscription] <String>] [-PassThru]
```

## DESCRIPTION
This topic describes the cmdlet in the 0.8.10 version of the Microsoft Azure PowerShell module.
To get the version of the module you're using, in the Azure PowerShell console, type (Get-Module -Name Azure).Version.

The Stop-AzureService cmdlet stops the current hosted service in the specified slot in Windows Azure.
If no slot is specified, the cmdlet stops the service in the Production slot.

## EXAMPLES

### 1:
```
PS C:\>
```

## PARAMETERS

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
Specifies the name of the hosted service to stop.
If no name is specified, the cmdlet stops the current hosted service.

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

### -Slot
Specifies the slot where the service is hosted, either Staging or Production.
If no slot is specified, Production is assumed.

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

### -Subscription
Specifies the subscription to use when stopping the service.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
Default value: 
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Remove-AzureService](19376209-6c0d-46e0-ad98-b8e2f13c0893)

[Start-AzureService](56e58937-4763-467c-a98c-c89ae4326e84)

