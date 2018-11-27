---
external help file: Microsoft.Azure.Commands.EventGrid.dll-Help.xml
Module Name: Az.EventGrid
online version:
schema: 2.0.0
---

# Get-AzEventGridSubscription

## SYNOPSIS
{{Fill in the Synopsis}}

## SYNTAX

### EventSubscriptionTopicNameParameterSet (Default)
```
Get-AzEventGridSubscription [[-EventSubscriptionName] <String>] [[-ResourceGroupName] <String>]
 [[-TopicName] <String>] [-IncludeFullEndpointUrl] [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

### ResourceIdEventSubscriptionParameterSet
```
Get-AzEventGridSubscription [[-EventSubscriptionName] <String>] [-ResourceId] <String>
 [-IncludeFullEndpointUrl] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### EventSubscriptionTopicTypeNameParameterSet
```
Get-AzEventGridSubscription [[-ResourceGroupName] <String>] [[-TopicTypeName] <String>] [[-Location] <String>]
 [-IncludeFullEndpointUrl] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### EventSubscriptionInputObjectSet
```
Get-AzEventGridSubscription [-InputObject] <PSTopic> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
{{Fill in the Description}}

## EXAMPLES

### Example 1
```powershell
PS C:\> {{ Add example code here }}
```

{{ Add example description here }}

## PARAMETERS

### -DefaultProfile
The credentials, account, tenant, and subscription used for communication with Azure.

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EventSubscriptionName
The name of the event subscription

```yaml
Type: System.String
Parameter Sets: EventSubscriptionTopicNameParameterSet, ResourceIdEventSubscriptionParameterSet
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -IncludeFullEndpointUrl
Include the full endpoint URL of the event subscription destination.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: EventSubscriptionTopicNameParameterSet, ResourceIdEventSubscriptionParameterSet, EventSubscriptionTopicTypeNameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
EventGrid Topic object.

```yaml
Type: Microsoft.Azure.Commands.EventGrid.Models.PSTopic
Parameter Sets: EventSubscriptionInputObjectSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Location
Location

```yaml
Type: System.String
Parameter Sets: EventSubscriptionTopicTypeNameParameterSet
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
The name of the resource group

```yaml
Type: System.String
Parameter Sets: EventSubscriptionTopicNameParameterSet, EventSubscriptionTopicTypeNameParameterSet
Aliases: ResourceGroup

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceId
Identifier of the resource to which event subscriptions have been created.

```yaml
Type: System.String
Parameter Sets: ResourceIdEventSubscriptionParameterSet
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -TopicName
The name of the topic type

```yaml
Type: System.String
Parameter Sets: EventSubscriptionTopicNameParameterSet
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -TopicTypeName
The name of the topic type

```yaml
Type: System.String
Parameter Sets: EventSubscriptionTopicTypeNameParameterSet
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.
For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### Microsoft.Azure.Commands.EventGrid.Models.PSTopic

## OUTPUTS

### Microsoft.Azure.Commands.EventGrid.Models.PSEventSubscription

## NOTES

## RELATED LINKS
