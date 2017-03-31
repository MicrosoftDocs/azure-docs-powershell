---
external help file: Microsoft.WindowsAzure.Commands.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: E7F1F621-3F4A-488E-A92C-073080B1AF04
---

# Get-WAPackStaticIPAddressPool

## SYNOPSIS
Gets static IP address pool objects.

## SYNTAX

### FromVMSubnetObject (Default)
```
Get-WAPackStaticIPAddressPool [-VMSubnet] <VMSubnet> [-Profile <AzureSMProfile>] [<CommonParameters>]
```

### FromName
```
Get-WAPackStaticIPAddressPool [-VMSubnet] <VMSubnet> [-Name] <String> [-Profile <AzureSMProfile>]
 [<CommonParameters>]
```

## DESCRIPTION
These topics are deprecated and will be removed in the future.
For the updated topics, see  [Azure WAPack Cmdlets](http://msdn.microsoft.com/library/dn776450.aspx) (http://msdn.microsoft.com/library/dn776450.aspx).
This topic describes the cmdlet in the 0.8.1 version of the Microsoft Azure PowerShell module.
To find out the version of the module you're using, from the Azure PowerShell console, type `(Get-Module -Name Azure).Version`.

The **Get-WAPackStaticIPAddressPool** cmdlet gets static IP address pool objects.

## EXAMPLES

### Example 1: Get a static IP address pool from a given VMSubnet
```
PS C:\> $Subnet = Get-WAPackVMSubet -Name "ContosoVMSubnet01"
PS C:\> Get-WAPackStaticIPAddressPool -VMSubnet $Subnet -Name "ContosoStaticIPAddressPool01"
```

This command gets the static IP address pool named ContosoStaticIPAddressPool01 from a specified VMSubnet.

### Example 2: Get all static IP address pools from a given VMSubnet
```
PS C:\> $Subnet = Get-WAPackVMSubet -Name "ContosoVMSubnet01"
PS C:\> Get-WAPackStaticIPAddressPool -VMSubnet $Subnet
```

This command gets all the static IP pools from a specified VMSubet.

## PARAMETERS

### -VMSubnet
Specifies the **VMSubnet** object associated to the static IP address pool.

```yaml
Type: VMSubnet
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Specifies the name of a static IP address pool.

```yaml
Type: String
Parameter Sets: FromName
Aliases: 

Required: True
Position: 1
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[New-WAPackStaticIPAddressPool](./New-WAPackStaticIPAddressPool.md)

[Remove-WAPackStaticIPAddressPool](./Remove-WAPackStaticIPAddressPool.md)


