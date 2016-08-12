---
external help file: SMAzure_Compute.xml
online version: 
schema: 2.0.0
---

# Start-AzureService
## SYNOPSIS
Starts the specified hosted service in Windows Azure.

## SYNTAX

```
Start-AzureService [[-ServiceName] <String>] [[-Slot] <String>] [[-Subscription] <String>] [-PassThru]
```

## DESCRIPTION
This topic describes the cmdlet in the 0.8.10 version of the Microsoft Azure PowerShell module.
To get the version of the module you're using, in the Azure PowerShell console, type (Get-Module -Name Azure).Version.

The Start-AzureService cmdlet starts the specified hosted service in Windows Azure, if the service is in the stopped state.
Note that the Publish-AzureServiceProject cmdlet automatically attempts to start the service.

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
Specifies the name of the hosted service to start.
If no name is specified, the cmdlet starts the current hosted service.

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
Specifies the deployment slot in which to start the service, either Staging or Production.

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
Specifies the subscription to use when starting the specified service.

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

[Publish-AzureServiceProject](4c0c0966-919e-49a6-9d38-c3c97355e281)

[Remove-AzureService](19376209-6c0d-46e0-ad98-b8e2f13c0893)

[Stop-AzureService](82d56ef9-9651-4224-9ba0-498750f6f551)

