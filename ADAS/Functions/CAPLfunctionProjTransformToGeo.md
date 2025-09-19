# Proj_TransformToGeo (ADAS)

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

**Note**  
This CAPL function is also available in C#.

## Function Syntax

**C#**  
`bool result = _ADAS.DataModel.ProjAccess.Proj_TransformToGeo.Call(inertialCoordinate, out geoCoordinate);`

**CAPL**  

```plaintext
long result;
result = _ADAS.DataModel.ProjAccess.Proj_TransformToGeo.Call(inertialCoordinate, out geoCoordinate);
```

## Description

This function transforms an inertial coordinate to a geodetic coordinate. Proj_Create has to be called first to initialize the Proj Access with a definition/proj_string.

## Parameters

- **inertialCoordinate : _ADAS.DataModel.Position3d**  
  An inertial coordinate

- **geoCoordinate : _ADAS.DataModel.GeoPosition**  
  A geodetic coordinate (out-param)

## Return Values

- **bool**  
  true if transformation is correct, false otherwise

## Example

In the examples it is assumed in each case that a DO object of the type IScenarioManager was created.

### CAPL

```plaintext
struct _ADAS::DataModel::Position3d inertialPos;
struct _ADAS::DataModel::GeoPosition result;

_ADAS::DataModel::ProjAccess.Proj_Create.Call("+proj=tmerc +a=6378137 +b=6378137 +lon_0=8.8995026301666247 +x_0=-0 +y_0=-5423575.9170007547 +k=1.0 +units=m +nadgrids=@null +wktext +no_defs");

inertialPos.x = -1436.30287110635;
inertialPos.y = 1107.91554956408;
inertialPos.z = 445.773842805044;
_ADAS::DataModel::ProjAccess.Proj_TransformToGeo.Call(inertialPos, result);
```

### C#

```plaintext
_ADAS.DataModel.ProjAccess.Proj_Create.Call("+proj=tmerc +a=6378137 +b=6378137 +lon_0=8.8995026301666247 +x_0=-0 +y_0=-5423575.9170007547 +k=1.0 +units=m +nadgrids=@null +wktext +no_defs");
_ADAS.DataModel.Position3d inertialPos = new _ADAS.DataModel.Position3d();
inertialPos.x.ImplValue = -1436.30287110635;
inertialPos.y.ImplValue = 1107.91554956408;
inertialPos.z.ImplValue = 445.773842805044;

_ADAS.DataModel.GeoPosition result;

_ADAS.DataModel.ProjAccess.Proj_TransformToGeo.Call(inertialPos, out result);
```
