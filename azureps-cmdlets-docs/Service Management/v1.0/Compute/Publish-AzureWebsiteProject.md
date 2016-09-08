---
external help file: SMAzure_Compute.xml
online version: 0c2a5092-db45-4ce7-b39b-d1e499b4a867
schema: 2.0.0
---

# Publish-AzureWebsiteProject
## SYNOPSIS
Publish a Visual Studio web project to a Microsoft Azure web site using WebDeploy.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Publish-AzureWebsiteProject [[-Name] <String>] [-ProjectFile] <String> [[-Configuration] <String>]
 [[-ConnectionString] <Hashtable>] [-Slot <String>]
```

### UNNAMED_PARAMETER_SET_2
```
Publish-AzureWebsiteProject [[-Name] <String>] [-Package] <String> [[-ConnectionString] <Hashtable>]
 [-Slot <String>]
```

## DESCRIPTION
Publish a Visual Studio web project to a Microsoft Azure web site using WebDeploy.
It can either take a WebDeploy package and publish directly, or take a Visual Studio web project, build the project and publish.
It can also replace the connection strings in the Web.config during publish.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
C:\PS>Publish-AzureWebsiteProject -Name site1 -ProjectFile .\WebApplication1.csproj -Configuration Debug
```

Description

-----------

Build a Visual Studio web project with "Debug" configuration (meaning use Web.Debug.config) and publish to a Microsoft Azure Web Site using WebDeploy.

### -------------------------- EXAMPLE 2 --------------------------
```
C:\PS>Publish-AzureWebsiteProject -Name site1 -Package .\WebApplication1.zip
```

Description

-----------

Publish a WebDeploy Pacakge .zip file to a Microsoft Azure Web Site using WebDeploy.

### -------------------------- EXAMPLE 3 --------------------------
```
C:\PS>Publish-AzureWebsiteProject -Name site1 -Package .\WebApplication1
```

Description

-----------

Publish a WebDeploy Pacakge folder to a Microsoft Azure Web Site using WebDeploy.

### -------------------------- EXAMPLE 4 --------------------------
```
C:\PS>Publish-AzureWebsiteProject -Name site1 -ProjectFile .\WebApplication1.csproj -ConnectionString @{ DefaultConnection = "my connection string" }
```

Description

-----------

Build a Visual Studio web project, overwrite the "DefaultConnection" connection string in Web.config and publish to a Microsoft Azure Web Site using WebDeploy.

### -------------------------- EXAMPLE 5 --------------------------
```
C:\PS>Publish-AzureWebsiteProject -Name site1 -ProjectFile .\WebApplication1.csproj -DefaultConnection "my connection string"
```

Description

-----------

Build a Visual Studio web project, overwrite the "DefaultConnection" connection string in Web.config and publish to a Microsoft Azure Web Site using WebDeploy.
Notice that -DefaultConnection is a dynamic parameter which gets added by parsing Web.config.

## PARAMETERS

### -Configuration
The configuration used to build the Visual Studio web application project.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: 3
Default value: Release
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ConnectionString
The connection strings to use for the deployment.

```yaml
Type: Hashtable
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
Default value: 
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
The web site name.

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

### -Package
The WebDeploy package folder for zip file of the Visual Studio web application project to be published.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: 2
Default value: 
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ProjectFile
The Visual Studio web application project to be published.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: 2
Default value: 
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Slot
The web site slot name.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: 
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-AzureWebsite](0c2a5092-db45-4ce7-b39b-d1e499b4a867)

[New-AzureWebsite](498c1abd-298b-43e9-ac53-bc57054a5387)

[Remove-AzureWebsite](3997c3b8-37ce-4135-a17d-63ae3bdd8e74)

[Set-AzureWebsite](7b386051-005d-499d-a106-1eb34d5c9f47)

