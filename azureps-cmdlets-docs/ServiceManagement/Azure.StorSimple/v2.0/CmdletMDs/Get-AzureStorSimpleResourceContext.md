---
external help file: Microsoft.WindowsAzure.Commands.StorSimple.dll-Help.xml
online version: .\Get-AzureStorSimpleResource.md
schema: 2.0.0
---

# Get-AzureStorSimpleResourceContext

## SYNOPSIS
Gets the current resource context.

## SYNTAX

```
Get-AzureStorSimpleResourceContext [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureStorSimpleResourceContext** cmdlet gets the current resource context.

## EXAMPLES

### Example 1: Get the current context
```
PS C:\>Select-AzureStorSimpleResource -ResourceName "Contoso63-Tsqa" 
PS C:\> Get-AzureStorSimpleResourceContext
ResourceId           ResourceName
----------           ------------
1909806764156522689  Contoso63-Tsqa
```

The first command sets the current context to be the resource named Contoso63-Tsqa by using the **Select-AzureStorSimpleResource** cmdlet.

The second command gets the current resource context.

### Example 2: Attempt to get the current context
```
PS C:\>Get-AzureStorSimpleResourceContext
Get-AzureStorSimpleResourceContext : Resource Context is not set for your subscription. Please use
Select-AzureStorSimpleResource -ResourceName <<name>> to set
```

This command gets the current context.
In this example, no context has been set.
The command returns a message that explains the problem.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### StorSimpleResourceContext
This cmdlet returns a **ResourceContext** object.

## NOTES

## RELATED LINKS

[Get-AzureStorSimpleResource](.\Get-AzureStorSimpleResource.md)

[Select-AzureStorSimpleResource](.\Select-AzureStorSimpleResource.md)

