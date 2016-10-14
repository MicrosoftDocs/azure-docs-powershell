---
external help file: Microsoft.WindowsAzure.Commands.Profile.dll-Help.xml
online version: http://go.microsoft.com/fwlink/?LinkID=397623
schema: 2.0.0
---

# Get-AzureSubscription

## SYNOPSIS
Gets  Azure subscriptions in Azure account.

## SYNTAX

### ByName (Default)
```
Get-AzureSubscription [[-SubscriptionName] <String>] [-ExtendedDetails] [-Profile <AzureSMProfile>]
 [<CommonParameters>]
```

### ById
```
Get-AzureSubscription [-SubscriptionId <String>] [-ExtendedDetails] [-Profile <AzureSMProfile>]
 [<CommonParameters>]
```

### Default
```
Get-AzureSubscription [-Default] [-ExtendedDetails] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

### Current
```
Get-AzureSubscription [-Current] [-ExtendedDetails] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureSubscription** cmdlet gets the subscriptions in your Azure account.
You can use this cmdlet to get information about the subscription and to pipe the subscription to other cmdlets.

**Get-AzureSubscription** requires access to your Azure accounts.
Before you run **Get-AzureSubscription**, you must run the **Add-AzureAccount** cmdlet or the cmdlets that download and install a publish settings file (**Get-AzurePublishSettingsFile**, **Import-AzurePublishSettingsFile**.

This topic describes the cmdlet in the 0.8.10 version of the Microsoft Azure PowerShell module.
To get the version of the module you're using, in the Azure PowerShell console, type (Get-Module -Name Azure).Version.

## EXAMPLES

### Example 1: Get all subscriptions
```
C:\PS>Get-AzureSubscription
```

This command gets all subscriptions in the account.

### Example 2: Get a subscription by name
```
C:\PS>Get-AzureSubscription  ¢â‚¬"SubscriptionName "MyProdSubscription"
```

This command gets only the "MyProdSubsciption" subscription.

### Example 3: Get the default subscription
```
C:\PS>(Get-AzureSubscription -Default).SubscriptionName
```

This command gets only the name of the default subscription.
The command first gets the subscription and then uses the dot method to get the SubscriptionName property of the subscription.

### Example 4: Get selected subscription properties
```
C:\PS>Get-AzureSubscription -Current | Format-List -Property SubscriptionName, Certificate
```

This command returns a list with the name and certificate of the current subscription.
It uses a **Get-AzureSubscription** command to get the current subscription.
Then it pipes the subscription to a **Format-List** command that displays the selected properties in a list.

### Example 5: Use an alternate subscription data file
```
C:\PS>Get-AzureSubscription -SubscriptionDataFile "C:\Temp\MySubscriptions.xml"
```

This command gets subscriptions from  the C:\Temp\MySubscriptions.xml subscription data file.
Use the **SubscriptionDataFile** parameter if you specified an alternate subscription data file when you ran the **Add-AzureAccount** or **Import-PublishSettingsFile** cmdlets.

## PARAMETERS

### -SubscriptionName
Gets only the specified subscription.
Enter the subscription name.
The value is case-sensitive.
Wildcard characters are not supported.
By default, **Get-AzureSubscription** gets all subscriptions in your Azure accounts.

```yaml
Type: String
Parameter Sets: ByName
Aliases: Name

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ExtendedDetails
Returns quota information for the subscription, in addition to the standard settings.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Profile
@{Text=}

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

### -SubscriptionId
@{Text=}

```yaml
Type: String
Parameter Sets: ById
Aliases: Id

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Default
Gets only the default subscription, that is, the subscription designated as "default." By default, **Get-AzureSubscription** gets all subscriptions in your Azure accounts.
To designate a subscription as "default," use the **Default** parameter of the **Select-AzureSubscription** cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: Default
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Current
Gets only the current subscription, that is, the subscription designated as "current." By default, **Get-AzureSubscription** gets all subscriptions in your Azure accounts.
To designate a subscription as "current," use the **Current** parameter of the **Select-AzureSubscription** cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: Current
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

### None
You can pipe input to the **SubscriptionName** property by name, but not by value.

## OUTPUTS

### Microsoft.WindowsAzure.Commands.Utilities.Common.WindowsAzureSubscription

## NOTES
* Get-AzureSubscription gets data from the subscription data file that the **Add-AzureAccount** and **Import-PublishSettingsFile** cmdlets create.

## RELATED LINKS

[Add-AzureAccount](.\Add-AzureAccount.md)

[Get-AzurePublishSettingsFile](.\Get-AzurePublishSettingsFile.md)

[Import-AzurePublishSettingsFile](.\Import-AzurePublishSettingsFile.md)

[Remove-AzureSubscription](.\Remove-AzureSubscription.md)

[Set-AzureSubscription](.\Set-AzureSubscription.md)

