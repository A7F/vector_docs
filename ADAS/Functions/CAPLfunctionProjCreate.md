[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ADAS/Functions/CAPLfunctionProjCreate.md)

[CAPL Functions](../../CAPLfunctions.md) » [ADAS](../CAPLfunctionsADASOverview.md) » Proj_Create (ADAS)

# Proj_Create (ADAS)

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

**Note**  
This CAPL function is also available in C#.

## Function Syntax

**C#**

```csharp
bool result = _ADAS.DataModel.ProjAccess.Proj_Create.Call(proj_string);
```

**CAPL**

```capl
long result;
result = _ADAS.DataModel.ProjAccess.Proj_Create.Call(proj_string);
```

## Description

This function initializes the Proj Access (interface IProjAccess) with a proj definition. After this, the methods Proj_TransformToGeo or Proj_TransformToInertial can be used to transform coordinates using the Proj Access.

## Parameters

- **definition : string**  
  The Proj String

## Return Values

- **bool**  
  true if initialization is correct, false otherwise

## Example

In the examples it is assumed in each case that a DO object of the type IScenarioManager was created.

### CAPL

```capl
long result = _ADAS.DataModel.ProjAccess.Proj_Create.Call("+proj=tmerc +a=6378137 +b=6378137 +lon_0=8.8995026301666247 +x_0=-0 +y_0=-5423575.9170007547 +k=1.0 +units=m +nadgrids=@null +wktext +no_defs");
```

### C#

```csharp
bool result = _ADAS.DataModel.ProjAccess.Proj_Create.Call("+proj=tmerc +a=6378137 +b=6378137 +lon_0=8.8995026301666247 +x_0=-0 +y_0=-5423575.9170007547 +k=1.0 +units=m +nadgrids=@null +wktext +no_defs");
```

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)