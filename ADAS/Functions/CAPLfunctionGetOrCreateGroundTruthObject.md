[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ADAS/Functions/CAPLfunctionGetOrCreateGroundTruthObject.md)

**CAPL Functions** » [ADAS](../CAPLfunctionsADASOverview.md) » GetOrCreateGroundTruthObject

# GetOrCreateGroundTruthObject

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

**Note:** This CAPL function is also available in C#.

## Function Syntax

**C#**

```csharp
string = GroundTruthAccess.GetOrCreateGroundTruthObject.Call(42);
```

**CAPL**

```capl
GroundTruthAccess.GetOrCreateGroundTruthObject.Call(uint64 groundTruthId, _ADAS.DataModel.EEnvironmentObjectType  environmentObjectType);
```

## Description

Gets a ground truth object as string (name of the object). The object is created if it does not exist. The object itself can be retrieved after using a lookup function (see example).

## Parameters

- **groundTruthId**: Id of the ground truth object
- **environmentObjectType**: Type of the ground truth object to be created.

  The following `environmentObjectType` values are supported to be displayed in the Scene Window:
  - IStationaryObject
  - IMovingObject
  - ILane
  - ILaneBounday

## Return Values

The name of the ground truth object as string.

## Example

### CAPL

```capl
variables
{
  distObjRef ::_ADAS::DataModel::IMovingObject moveableObject;
}

on key 'c'
{
  stack char moveableObjName [100];
  stack char moveableObjNameWithAdasPrefix [100];

  memcpy(moveableObjName, GroundTruthAccess.GetOrCreateGroundTruthObject.Call(42, _ADAS::DataModel::EEnvironmentObjectType::IMovingObject),
  elCount(GroundTruthAccess.GetOrCreateGroundTruthObject.Call(42, _ADAS::DataModel::EEnvironmentObjectType:: IMovingObject)));

  snprintf(moveableObjNameWithAdasPrefix, elcount(moveableObjNameWithAdasPrefix), "ADAS::%s", moveableObjName);
  moveableObject = (distObjRef _ADAS::DataModel::IMovingObject) lookupDistObj(moveableObjNameWithAdasPrefix);

  if(moveableObject.IsValid)
  {
    $moveableObject.moving_object.baseInfo.dimension.length.impl = 20;
    $moveableObject.moving_object.baseInfo.dimension.width.impl = 4;
    $moveableObject.moving_object.baseInfo.dimension.height.impl = 3;
  }
}
```

### C#

```csharp
_ADAS.DataModel.IMovingObject GetOrCreatedMovableObject(ulong groundTruthId)
{
  string gtHostVehicle = GroundTruthAccess.GetOrCreateGroundTruthObject.Call(groundTruthId, (int)_ADAS.DataModel.EEnvironmentObjectType.IMovingObject);
  return DORegistry.LookupDistributedObject<_ADAS.DataModel.IMovingObject>(gtHostVehicle, "ADAS");
}

[OnKey('c')]
public void CKeyPress(char c)
{
  var moveableObject = GetOrCreatedMovableObject(42);
  moveableObject.moving_object.baseInfo.dimension.length.PhysValue = 20;
  moveableObject.moving_object.baseInfo.dimension.width.PhysValue = 4;
  moveableObject.moving_object.baseInfo.dimension.height.PhysValue = 3;
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)