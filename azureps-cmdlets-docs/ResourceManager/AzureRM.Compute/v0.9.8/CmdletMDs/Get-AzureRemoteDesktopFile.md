---
external help file: Microsoft.Azure.Commands.Compute.dll-Help.xml
online version: 46815766-c350-4318-a4dd-2250d664cc53
schema: 2.0.0
---

# Get-AzureRemoteDesktopFile

## SYNOPSIS
Gets an .rdp file.

## SYNTAX

### Download
```
Get-AzureRemoteDesktopFile [-ResourceGroupName] <String> [-Name] <String> [-LocalPath] <String>
 [-Profile <AzureProfile>] [<CommonParameters>]
```

### Launch
```
Get-AzureRemoteDesktopFile [-ResourceGroupName] <String> [-Name] <String> [[-LocalPath] <String>] [-Launch]
 [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureRemoteDesktopFile** cmdlet gets a Remote Desktop Protocol (.rdp) file.

## EXAMPLES

### Example 1: Get a Remote Desktop file
```
PS C:\>Get-AzureRemoteDesktopFile -ResourceGroupName "ResourceGroup11" -Name "VirtualMachine07" -LocalPath "D:\RemoteDesktopFile07.rdp"
```

This command gets the Remote Desktop file for the virtual machine named VirtualMachine07.
The command stores the result in the file named D:\RemoteDesktopFile07.rdp.

## PARAMETERS

### -LocalPath
Specifies the local full path where this cmdlet stores the .rdp file.

```yaml
Type: String
Parameter Sets: Download
Aliases: 

Required: True
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

```yaml
Type: String
Parameter Sets: Launch
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies the name of the availability set that this cmdlet gets.

```yaml
Type: String
Parameter Sets: (All)
Aliases: ResourceName, VMName

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Profile
Specifies the Azure profile from which this cmdlet reads.
If you do not specify a profile, this cmdlet reads from the local default profile.

```yaml
Type: AzureProfile
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Specifies the name of a resource group.```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Launch
When specified, launches a remote desktop session to the specified virtual machine.```yaml
Type: SwitchParameter
Parameter Sets: Launch
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

