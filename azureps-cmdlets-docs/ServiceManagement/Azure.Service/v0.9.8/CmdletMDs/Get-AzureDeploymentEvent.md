---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.dll-Help.xml
online version: .\Get-AzureDeployment.md
schema: 2.0.0
---

# Get-AzureDeploymentEvent

## SYNOPSIS
Gets information about events that Azure initiates that impact virtual machines and cloud services.

## SYNTAX

### GetDeploymentEventBySlot (Default)
```
Get-AzureDeploymentEvent -ServiceName <String> -StartTime <DateTime> -EndTime <DateTime> [-Slot <String>]
 [-Profile <AzureProfile>] [<CommonParameters>]
```

### GetDeploymentEventByName
```
Get-AzureDeploymentEvent -ServiceName <String> -StartTime <DateTime> -EndTime <DateTime>
 -DeploymentName <String> [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureDeploymentEvent** cmdlet gets information regarding events that Azure initiates that impact virtual machines and cloud services.
These events include planned maintenance events.
This cmdlet returns a list of events that identify the role instance or virtual machine impacted, the reason for the impact, and the start time of the event.

## EXAMPLES

### 1:
```

```

## PARAMETERS

### -EndTime
Specifies the ending time for the scheduled events that this cmdlet gets.

```yaml
Type: DateTime
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ServiceName
Specifies the name of the hosted service for which this cmdlet gets scheduled events.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -StartTime
Specifies the starting time for the scheduled events that this cmdlet gets.

```yaml
Type: DateTime
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DeploymentName
Specifies the name of the deployment for which this cmdlet gets events.

```yaml
Type: String
Parameter Sets: GetDeploymentEventByName
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

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

### -Slot
Specifies the environment of the deployment for which this cmdlet gets scheduled events.
Valid values are: Staging and Production.
The default value is Production.

```yaml
Type: String
Parameter Sets: GetDeploymentEventBySlot
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

[Get-AzureDeployment](.\Get-AzureDeployment.md)

