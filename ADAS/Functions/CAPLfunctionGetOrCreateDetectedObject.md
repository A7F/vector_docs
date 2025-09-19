# GetOrCreateDetectedObject

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

**Note**  
This CAPL function is also available in C#.

## Function Syntax

**C#**  
`string GetOrCreateDetectedObject.Call_Phys(int trackingId, _ADAS.DataModel.EDetectedObjectType detObjType);`

**CAPL**  
`char[] GetOrCreateDetectedObject.Call_Phys(int trackingId, _ADAS::DataModel::EDetectedObjectType detObjType);`

## Description

This function gets the name of a detected object of a sensor as a string. If no object with the given trackingId exists, it will be created.

## Parameters

- **trackingId**: Id of the object
- **conditionValue**: Type of the detected object

  **C#**
  - `_ADAS.DataModel.EDetectedObjectType.IDetectedMovingObject`
  - `_ADAS.DataModel.EDetectedObjectType.IDetectedStationaryObject`
  - `_ADAS.DataModel.EDetectedObjectType.IDetectedTrafficSign`
  - `_ADAS.DataModel.EDetectedObjectType.IDetectedTrafficLight`
  - `_ADAS.DataModel.EDetectedObjectType.IDetectedRoadMarking`
  - `_ADAS.DataModel.EDetectedObjectType.IDetectedLaneBoundary`
  - `_ADAS.DataModel.EDetectedObjectType.IDetectedLane`
  - `_ADAS.DataModel.EDetectedObjectType.IDetectedOccupant`

  **CAPL**
  - `_ADAS::DataModel::EDetectedObjectType::IDetectedMovingObject`
  - `_ADAS::DataModel::EDetectedObjectType::IDetectedStationaryObject`
  - `_ADAS::DataModel::EDetectedObjectType::IDetectedTrafficSign`
  - `_ADAS::DataModel::EDetectedObjectType::IDetectedTrafficLight`
  - `_ADAS::DataModel::EDetectedObjectType::IDetectedRoadMarking`
  - `_ADAS::DataModel::EDetectedObjectType::IDetectedLaneBoundary`
  - `_ADAS::DataModel::EDetectedObjectType::IDetectedLane`
  - `_ADAS::DataModel::EDetectedObjectType::IDetectedOccupant`

## Return Values

A string containing the name of the detected object.

## Example

In the examples it is assumed in each case that a DO object of the type IScenarioManager was created.

### CAPL

```capl
distObjRef ::_ADAS::DataModel::IDetectedMovingObject detObj;
char detObjName [100];
char detObjNameWithAdasPrefix [100];
memcpy(detObjName, radar.GetOrCreateDetectedObject.Call_Phys(5, _ADAS::DataModel::EDetectedObjectType::
IDetectedMovingObject), elCount(radar.GetOrCreateDetectedObject.Call_Phys(5, _ADAS::DataModel::EDetectedObjectType::
IDetectedMovingObject)));
snprintf(detObjNameWithAdasPrefix, elcount(detObjNameWithAdasPrefix),"ADAS::%s", detObjName);
detObj = (distObjRef _ADAS::DataModel::IDetectedMovingObject) lookupDistObj(detObjNameWithAdasPrefix);
if(detObj.IsValid)
{
  $detObj.moving_object.baseInfo.position.x.impl = 1; // set
  write("Position X: %f", $detObj.moving_object.baseInfo.position.x.impl); // get
}
```

### C#

```csharp
string detObjName = radar.GetOrCreateDetectedObject.Call_Phys(5, _ADAS.DataModel.EDetectedObjectType.IDetectedMovingObject);
_ADAS.DataModel.IDetectedMovingObject detObj = DORegistry.LookupDistributedObject<_ADAS.DataModel.IDetectedMovingObject>(detObjName, "ADAS");
if (detObj != null)
{
  detObj.moving_object.baseInfo.position.x.ImplValue = 1; // set
  Output.WriteLine("Position X: " + detObj.moving_object.baseInfo.position.x.ImplValue); // get
}
```
