---
external help file: Microsoft.Azure.Commands.NotificationHubs.dll-Help.xml
online version: .\Get-AzureRmNotificationHubsNamespace.md
schema: 2.0.0
---

# Set-AzureRmNotificationHubsNamespace

## SYNOPSIS
Sets property values for a notification hub namespace.

## SYNTAX

```
Set-AzureRmNotificationHubsNamespace [-ResourceGroup] <String> [-Namespace] <String> -Location <String>
 [[-State] <NamespaceState>] [[-Critical] <Boolean>] [[-Tags] <Hashtable>]
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-AzureRmNotificationHubsNamespace** cmdlet sets the property values of an existing notification hub namespace.

Namespaces are logical containers that help you organize and manage your notification hubs.
You must have at least one notification hub namespace.
Additionally, all notification hubs must have an assigned namespace.

This cmdlet is primarily used to enable and disable a namespace.
When a namespace is disabled, users cannot connect to any of the notification hubs in the namespace, nor can administrators use those hubs to send push notifications.
To re-enable a disabled namespace, use this cmdlet to set the **State** property of the namespace to Active.

You can also use this cmdlet to tag a namespace as critical.
This prevents the namespace from being deleted.
To remove a critical namespace you must first remove the Critical tag.

## EXAMPLES

### Example 1: Disable a namespace
```
PS C:\>Set-AzureRmNotificationHubsNamespace -Namespace "ContosoPartners" -Location "West US" -ResourceGroup "ContosoNotificationsGroup" -State "Disabled"
```

This command disables the namespace named ContosoPartners located in the West US datacenter and assigned to the ContosoNotificationsGroup resource group.

### Example 2: Enable a namespace
```
PS C:\>Set-AzureRmNotificationHubsNamespace -Namespace "ContosoPartners" -Location "West US" -ResourceGroup "ContosoNotificationsGroup" -State "Active"
```

This command enables the namespace named ContosoPartners located in the West US datacenter and assigned to the ContosoNotificationsGroup resource group.

## PARAMETERS

### -ResourceGroup
Specifies the resource group to which the namespace is assigned.

Resource groups organize items such as namespaces, notification hubs, and authorization rules in ways that help simply inventory management and azure_2 administration.

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

### -Namespace
Specifies the namespace that this cmdlet modifies.

Namespaces provide a way to group and categorize notification hubs.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -State
Specifies the current state of the namespace.
psdx_paramvalues Active and Disabled.

```yaml
Type: NamespaceState
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Critical
Indicates whether the namespace is a critical namespace.
Critical namespaces cannot be deleted.
To delete a critical namespace, you must set the value of this property to False in order to mark the namespace as non-critical.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Tags
Specifies name-value pairs that can be used to categorize and organize azure_2 items.
Tags function similar to keywords, and operate across a deployment.
For example, if you search for all items with the tag Department:IT the search will return all the azure_2 items that have that tag, regardless of such things as item type, location, or resource group.

An individual tag consists of two parts: the *Name* and (optionally) the *Value*.
For example, in Department:IT, the tag name is Department and the tag value is IT.
To add a tag, use hash table syntax similar to this, which creates the tag CalendarYear:2016:

-Tags @{Name="CalendarYear";Value="2016"}

To add multiple tags in the same command, separate the individual tags by using commas:

-Tag @{Name="CalendarYear";Value="2016"}, @{Name="FiscalYear";Value="2017"}

```yaml
Type: Hashtable
Parameter Sets: (All)
Aliases: 

Required: False
Position: 4
Default value: None
Accept pipeline input: True (ByPropertyName)
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
Specifies the display name of the datacenter that hosts the namespace.
Although you can set this parameter to any valid azure_2 location, for optimal performance you should use a datacenter located near the majority of your users.

To get an up-to-date list of azure_2 locations run the following command:

`Get-AzureLocation | Select-Object DisplayName`

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-AzureRmNotificationHubsNamespace](.\Get-AzureRmNotificationHubsNamespace.md)

[New-AzureRmNotificationHubsNamespace](.\New-AzureRmNotificationHubsNamespace.md)

[Remove-AzureRmNotificationHubsNamespace](.\Remove-AzureRmNotificationHubsNamespace.md)

