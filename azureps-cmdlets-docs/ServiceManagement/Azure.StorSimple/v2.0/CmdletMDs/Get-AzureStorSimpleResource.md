---
external help file: Microsoft.WindowsAzure.Commands.StorSimple.dll-Help.xml
online version: .\Get-AzureStorSimpleResourceContext.md
schema: 2.0.0
---

# Get-AzureStorSimpleResource

## SYNOPSIS
Gets all resources that you created.

## SYNTAX

```
Get-AzureStorSimpleResource [[-ResourceName] <String>] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureStorSimpleResource** cmdlet gets all resources that you created by using Azure Portal.
The cmdlet gets details you can use to connect to the resources.

## EXAMPLES

### Example 1: Get all resources
```
PS C:\>Get-AzureStorSimpleResource
VERBOSE: ClientRequestId: 5cd61b91-ef40-43b4-986d-156e06d2ed65_PS

ResourceName                                      ResourceId           ResourceState
------------                                      ----------           -------------
Contoso63-Tsqa                                    8838459798595306468  Started
Contoso68-Tsqa                                    2859070203638134681  Started
Contoso73-Tsqa                                    7871392677286863733  Started
Contoso87-Tsqa                                    1909806764156522689  Started
VERBOSE: Found 4 StorSimple resources.
```

This command gets all the resources you created.
In this example, there are three resources.

### Example 2: Get a resource by using its name
```
PS C:\>Get-AzureStorSimpleResource -ResourceName "Contoso63-Tsqa"
VERBOSE: ClientRequestId: efc3c85c-12aa-4345-b6eb-ccc532de4825_PS

ResourceName                                      ResourceId           ResourceState
------------                                      ----------           -------------
Contoso63-Tsqa                                    1909806764156522689  Started
VERBOSE: Found 1 StorSimple resource.
```

This command gets the resource named Contoso63-Tsqa.

### Example 3: Attempt to get a nonexistent resource
```
PS C:\>Get-AzureStorSimpleResource -ResourceName "Contoso64-Tsqa"
VERBOSE: ClientRequestId: 5d08d40b-f9d7-4d43-956f-13f01e89625b_PS
VERBOSE: Invalid input : Could not find a resource named Contoso64-Tsqa in your subscription.
```

This command attempts to get the resource named Contoso64-Tsqa.
There is no resource that has this name.
This example does not return any resource.

## PARAMETERS

### -Profile
Specifies an Azure profile.

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

### -ResourceName
Specifies the name of the resource that this cmdlet gets.

```yaml
Type: String
Parameter Sets: (All)
Aliases: Name

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### IEnumerable<ResourceCredentials>, ResourceCredentials
This cmdlet returns **ResourceCredentials** objects that contain the following properties: 

- **ResourceName**
- **ResouceId**
- **ResourceState**

## NOTES

## RELATED LINKS

[Get-AzureStorSimpleResourceContext](.\Get-AzureStorSimpleResourceContext.md)

[Select-AzureStorSimpleResource](.\Select-AzureStorSimpleResource.md)

