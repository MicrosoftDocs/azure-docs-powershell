---
external help file: Microsoft.WindowsAzure.Commands.dll-Help.xml
ms.assetid: D0A2B454-7BFF-4D4D-8A85-FDB47249758F
online version: 
schema: 2.0.0
---

# Set-AzureServiceProject

## SYNOPSIS
Sets default location, subscription, slot, and storage account for the current service.

## SYNTAX

```
Set-AzureServiceProject [[-Location] <String>] [[-Slot] <String>] [[-Storage] <String>] [-PassThru]
 [-Profile <AzureSMProfile>] [-InformationAction <ActionPreference>] [-InformationVariable <String>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Set-AzureServiceProject** cmdlet sets the deployment location, slot, storage account, and subscription for the current service.
These values are used whenever the service is published to the cloud.

## EXAMPLES

### Example 1: Basic settings
```
PS C:\> Set-AzureServiceProject -Location "North Central US" -Slot Production -Storage myStorageAccount -Subscription myAzureSubscription
```

Sets the deployment location for the service to the North Central US region.
Sets the deployment slot to Production. 
Sets the storage account that will be used to stage the service definition to myStorageAccount.
Sets the subscription that will host the service to mySubscription.
Whenever the service is published to the cloud, it will be hosted in a data center in the North Central US region, it will update the deployment slot, and it will use the specified subscription and storage account.

## PARAMETERS

### -InformationAction
Specifies how this cmdlet responds to an information event.

The acceptable values for this parameter are:

- Continue
- Ignore
- Inquire
- SilentlyContinue
- Stop
- Suspend

```yaml
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
Specifies an information variable.

```yaml
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
The region in which the service will be hosted.
This value is used whenever the service is published to the cloud.
Possible values are: Anywhere Asia, Anywhere Europe, Anywhere US, East Asia, East US, North Central US, North Europe, South Central US, Southeast Asia, West Europe, West US.

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

### -PassThru
Indicates that this cmdlet returns an object representing the item on which it operates.
By default, this cmdlet does not generate any output.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Profile
Specifies the Azure profile from which this cmdlet reads.
If you do not specify a profile, this cmdlet reads from the local default profile.

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

### -Slot
The slot (production or staging) in which the service will be hosted.
This value is used whenever the service is published to the cloud.
Possible values are: Production, Staging.

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

### -Storage
The storage account to be used when uploading the service package to the cloud.
If the storage account doesn't exist, it will be created when the service is published to the cloud.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES
* node-dev, php-dev, python-dev

## RELATED LINKS

[New-AzureServiceProject](./New-AzureServiceProject.md)

[Publish-AzureServiceProject](./Publish-AzureServiceProject.md)

[Set-AzureServiceProjectRole](./Set-AzureServiceProjectRole.md)


