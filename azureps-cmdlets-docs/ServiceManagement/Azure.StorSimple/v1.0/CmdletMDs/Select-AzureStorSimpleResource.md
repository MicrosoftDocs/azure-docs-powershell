---
external help file: Microsoft.WindowsAzure.Commands.StorSimple.dll-Help.xml
online version: .\Get-AzureStorSimpleResource.md
schema: 2.0.0
---

# Select-AzureStorSimpleResource

## SYNOPSIS
Sets a resource as the current resource.

## SYNTAX

```
Select-AzureStorSimpleResource [-ResourceName] <String> [[-RegistrationKey] <String>]
 [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Select-AzureStorSimpleResource** cmdlet sets a resource as the current resource.
After you select a resource, other cmdlets apply within that resource context.

## EXAMPLES

### Example 1: Select a resource for the first time
```
PS C:\>Select-AzureStorSimpleResource -ResourceName "Contoso64-Tsqa" -RegistrationKey "<your registration key>"
ResourceId           ResourceName
----------           ------------
1909806764156522689  Contoso64-Tsqa
```

This command selects the resource named Contoso64-Tsqa as the current context.
In this example, the computer has not had this context initialized previously, and, therefore, you must specify a value for the *RegistrationKey* parameter.

### Example 2: Attempt to select a resource
```
This command gets the current context for this computer by using the **Get-AzureStorSimpleResourceContext** cmdlet. The current selected resource is Contoso64-Tsqa. This is consistent with the previous example. 
PS C:\>Get-AzureStorSimpleResourceContext
ResourceId           ResourceName
----------           ------------
1909806764156522689  Contoso64-Tsqa 

This command attempts to reset the resource to be Contoso02-Resource. For this example, this resource has not been previously selected. The registration key is not saved or included in the command. The command cannot select the resource. 
PS C:\>Select-AzureStorSimpleResource -ResourceName "Contoso02-Resource"
Select-AzureStorSimpleResource : Could not find the persisted secret. Please use Select-AzureStorSimpleResource and
provide the Registration key once again.
```

### Example 3: Select a previously selected resource
```
PS C:\>Select-AzureStorSimpleResource -ResourceName "Contoso64-Tsqa"
ResourceId           ResourceName
----------           ------------
1909806764156522689  Contoso64-Tsqa
```

This command selects the resource named Contoso64-Tsqa as the current context.
In this example, that context has previously been selected, and, therefore, you do not need to specify a value for the *RegistrationKey* parameter.

## PARAMETERS

### -Profile
Specifies an azure_2 profile.

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

### -RegistrationKey
Specifies a registration key.
Specify a key the first time that you select a resource.
After this cmdlet selects the current resource, cmdlets use this key, as required.
For more information, see Get the service registration keyhttp://msdn.microsoft.com/en-us/library/azure/dn772346.aspx (http://msdn.microsoft.com/en-us/library/azure/dn772346.aspx) on the Microsoft Developer Network.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceName
Specifies the name of the resource to select as the current resource.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### StorSimpleResourceContext
This cmdlet returns a **StorSimpleResourceContext** object that contains details for the resource context.

## NOTES

## RELATED LINKS

[Get-AzureStorSimpleResource](.\Get-AzureStorSimpleResource.md)

[Get-AzureStorSimpleResourceContext](.\Get-AzureStorSimpleResourceContext.md)

