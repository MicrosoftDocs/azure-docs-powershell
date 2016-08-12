---
external help file: SMAzure_Compute.xml
online version: 4c0c0966-919e-49a6-9d38-c3c97355e281
schema: 2.0.0
---

# Set-AzureServiceProject
## SYNOPSIS
Sets default location, subscription, slot, and storage account for the current service

## SYNTAX

```
Set-AzureServiceProject [[-Location] <String>] [[-Slot] <String>] [[-Storage] <String>] [-PassThru]
```

## DESCRIPTION
Sets the deployment location, slot, storage account, and subscription for the current service. 
These values are used whenever the service is published to the cloud.

## EXAMPLES

### --------------  Basic Settings --------------
```
C:\PS>Set-AzureServiceProject -Location "North Central US" -Slot Production -Storage myStorageAccount -Subscription myAzureSubscription
```

Sets the deployment location for the service to the North Central US region.
Sets the deloyment slot to Production.

Sets the storage account ahat will be used to stage the service definition to 'myStorageAccount'. 
Sets the subscription

that will host the service to 'mySubscription'. 
Whenever the service is published to the cloud, it will be hosted in a

data center in the North Central US region, it will update the deployment slot, and it will use the specified subscription

and storage account.

## PARAMETERS

### -Location
The region in which the service will be hosted.
This value is used whenever the service is published to the cloud.
Possible values are: Anywhere Asia, Anywhere Europe, Anywhere US, East Asia, East US, North Central US, North Europe, South Central US, Southeast Asia, West Europe, West US.

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

### -PassThru
Indicates that this cmdlet returns an object representing the item on which it operates.
By default, this cmdlet does not generate any output.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: 5
Default value: 
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
Position: 2
Default value: 
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
Position: 3
Default value: 
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES
node-dev, php-dev, python-dev

## RELATED LINKS

[Publish-AzureServiceProject](4c0c0966-919e-49a6-9d38-c3c97355e281)

[Set-AzureServiceProjectRole](80fb7e11-389d-4341-9568-e1a1bc1789df)

[New-AzureServiceProject](68b3e4a9-7aff-4274-bd8c-0f664cb6e65d)

