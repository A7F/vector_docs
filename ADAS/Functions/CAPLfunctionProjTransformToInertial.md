[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ADAS/Functions/CAPLfunctionProjTransformToInertial.md)

# Proj_TransformToInertial (ADAS)

[CAPL Functions](../../CAPLfunctions.md) » [ADAS](../CAPLfunctionsADASOverview.md) » Proj_TransformToInertial (ADAS)

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

**Note**: This CAPL function is also available in C#.

## Function Syntax

**C#**

```csharp
bool result = _ADAS.DataModel.ProjAccess.Proj_TransformToInertial.Call(geoCoordinate, out inertialCoordinate);
```

**CAPL**

```capl
long result;
result = _ADAS.DataModel.ProjAccess.Proj_TransformToInertial.Call(geoCoordinate, out inertialCoordinate);
```

## Description

This function transforms a geodetic coordinate to an inertial coordinate. Proj_Create has to be called first to initialize the Proj Access with a definition/proj_string.

## Parameters

- **geoCoordinate : _ADAS.DataModel.GeoPosition**  
  A geodetic coordinate

- **inertialCoordinate : _ADAS.DataModel.Position3d**  
  An inertial coordinate (out-Param)

## Return Values

- **bool**  
  true if transformation is correct, false otherwise

## Example

In the examples it is assumed in each case that a DO object of the type IScenarioManager was created.

### CAPL

```capl
struct _ADAS::DataModel::GeoPosition geoPosition;
struct _ADAS::DataModel::Position3d result;

_ADAS::DataModel::ProjAccess.Proj_Create.
ll("+proj=tmerc +a=6378137 +b=6378137 +lon_0=8.8995026301666247 +x_0=-0 +y_0=-5423575.9170007547 +k=1.0 +units=m +nadgrids=@null +wktext +no_defs");

geoPosition.latitude = 8.87994143680241;
geoPosition.longitude = 48.73076232751458;
geoPosition.altitude = 445.773842805044;

_ADAS::DataModel::ProjAccess.Proj_TransformToInertial.Call(geoPosition, result);
```

### C#

```csharp
_ADAS.DataModel.ProjAccess.Proj_Create.Call("+proj=tmerc +a=6378137 +b=6378137 +lon_0=8.8995026301666247 +x_0=-0 +y_0=-5423575.9170007547 +k=1.0 +units=m +nadgrids=@null +wktext +no_defs");
_ADAS.DataModel.GeoPosition geoPos = new _ADAS.DataModel.GeoPosition();
_ADAS.DataModel.Position3d result;

geoPos.latitude.ImplValue = 8.87994143680241;
geoPos.longitude.ImplValue = 48.7307623275145;
geoPos.altitude.ImplValue = 445.773842805044;

_ADAS.DataModel.ProjAccess.Proj_TransformToInertial.Call(geoPos, out result);
```

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)