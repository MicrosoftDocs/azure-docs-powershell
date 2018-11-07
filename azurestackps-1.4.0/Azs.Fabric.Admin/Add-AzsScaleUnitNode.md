---
external help file: Azs.Fabric.Admin-help.xml
Module Name: Azs.Fabric.Admin
online version: 
schema: 2.0.0
---

# Add-AzsScaleUnitNode

## SYNOPSIS
Add a new scale unit.

## SYNTAX

### ScaleOut (Default)
```
Add-AzsScaleUnitNode -NodeList <ScaleOutScaleUnitParameters[]> -ResourceGroupName <String> -ScaleUnit <String>
 -Location <String> [-AwaitStorageConvergence] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
Scale out a scale unit.

## EXAMPLES

### Example 1
```
$NewNode=New-AzsScaleUnitNodeObject -computername "Prefix-node08" -BMCIPv4Address "10.1.2.4" 

Add-AzsScaleUnitNode -NodeList $NewNode -ScaleUnit "S-cluster" 
```

Adds a new single scale unit node.

### Example 1
```
$NewNode1=New-AzsScaleUnitNodeObject -computername "Prefix-node08" -BMCIPv4Address "BMCIP-Node08" 

$NewNode2=New-AzsScaleUnitNodeObject -computername "Prefix-node09" -BMCIPv4Address "BMCIP-Node09"

Add-AzsScaleUnitNode -NodeList @($NewNode1,$NewNode2) -ScaleUnit "S-cluster" 
```

Adds multiple scale unit nodes.

## PARAMETERS

### -AsJob
Run asynchronous as a job and return the job object.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -AwaitStorageConvergence
Flag indicates if the operation should wait for storage to converge before returning.


```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Location
Location of the resource.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NodeList
A list of input data that allows for adding a set of scale unit nodes.

```yaml
Type: ScaleOutScaleUnitParameters[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Name of the resource group.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ScaleUnit
Name of the scale units.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
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

