---
external help file: Microsoft.WindowsAzure.Commands.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 985635AC-A9D8-4578-82A9-DBD71ABC9B87
---

# Save-AzureServiceProjectPackage

## SYNOPSIS
Packages the service project into Azure cloud package (*.cspkg).

## SYNTAX

```
Save-AzureServiceProjectPackage [-Local] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
powershell_prelim

The **Save-AzureServiceProjectPackage** cmdlet packages the service project into an Azure cloud package (*.cspkg).

## EXAMPLES

### 1: Create a service project package
```
PS C:\>Save-AzureServiceProjectPackage
```

This example creates a *.cspgk for a service project named MyAzureServiceProject.

## PARAMETERS

### -Local

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: l

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Profile
In-memory profile.

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

## OUTPUTS

## NOTES

## RELATED LINKS

[Publish-AzureServiceProject](./Publish-AzureServiceProject.md)


