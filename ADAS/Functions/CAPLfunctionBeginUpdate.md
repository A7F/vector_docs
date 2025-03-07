[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ADAS/Functions/CAPLfunctionBeginUpdate.md)

# BeginUpdate

[CAPL Functions](../../CAPLfunctions.md) » [ADAS](../CAPLfunctionsADASOverview.md) » BeginUpdate

**Valid for**: CANoe DE

**Note**: This CAPL function is also available in C#.

## Function Syntax

**C#**

```csharp
void BeginUpdate.Call();
```

**CAPL**

```capl
void BeginUpdate.Call();
```

## Description

This method is only required if data of a sensor and those of its detected objects are not to be sent directly after assignment. This can be useful if sensor data are received from different sources and at different times (e.g. CAN messages) and these are to be successively assigned to a sensor object until the data structure has been completely filled. The call of the method Update then sends all data of the sensor and the detected objects that were marked as completed.

## Parameters

—

## Return Values

—

## Example

In the examples it is assumed in each case that a DO object of the type IScenarioManager was created.

### CAPL

```capl
variables
{
  int trackingId;

  distObjRef ::_ADAS::DataModel::IDetectedMovingObject detObj;

  char detObjName [100];
  char detObjNameWithAdasPrefix [100];

}
on message SampleFrame1.sampleFrame1
{
  radar.BeginUpdate.Call();

  trackingId = sampleFrame1.Id;

  memcpy(detObjName, radar.GetOrCreateDetectedObject.Call_Phys(trackingId, _ADAS::DataModel::EDetectedObjectType::IDetectedMovingObject), elCount(radar.GetOrCreateDetectedObject.Call_Phys(trackingId, _ADAS::DataModel::EDetectedObjectType:: IDetectedMovingObject)));

  snprintf(detObjNameWithAdasPrefix, elcount(detObjNameWithAdasPrefix),"ADAS::%s", detObjName);
  detObj = (distObjRef _ADAS::DataModel::IDetectedMovingObject) lookupDistObj(detObjNameWithAdasPrefix);

  if(detObj.IsValid)
  {
    $detObj.moving_object.baseInfo.position.x.impl = sampleFrame1.pos.x;
    $detObj.moving_object.baseInfo.position.y.impl = sampleFrame1.pos.y;
    $detObj.moving_object.baseInfo.position.z.impl = sampleFrame1.pos.z;
  }
}

on message SampleFrame2.sampleFrame2
{
  memcpy(detObjName, radar.GetDetectedObjectByTrackingId.Call(trackingId), elCount(radar.GetDetectedObjectByTrackingId.Call(trackingId)));

  snprintf(detObjNameWithAdasPrefix, elcount(detObjNameWithAdasPrefix),"ADAS::%s", detObjName);
  detObj = (distObjRef _ADAS::DataModel::IDetectedMovingObject) lookupDistObj(detObjNameWithAdasPrefix);

  if (detObj.IsValid)
  {
    $detObj.moving_object.baseInfo.dimension.height.impl = sampleFrame2.dim.height;
    $detObj.moving_object.baseInfo.dimension.width.impl = sampleFrame2.dim.width;
    $detObj.moving_object.baseInfo.dimension.length.impl = sampleFrame2.dim.length;
  }

  radar.SetDetectedObjectCompleted.Call(trackingId, true);

  // alternative: Set all detected objects for this sensor completed
  // radar.SetDetectedObjectsCompleted.Call(true);

  radar.Update.Call();
}

on fctCalled ADAS::radar.OnDetectedObjectUpdate
{
  if(this.detObj.header.trackingId == trackingId)
  {
    // Possibility to set values manually
    this.detObj.header.existence_probability.PhysValue = 50.0;
  }
}
```

### C#

```csharp
public int trackingId;
[OnCANFrame]
public void OnCANFrame(NetworkDB.Frames.SampleFrame1 sampleFrame1)
{
  radar.BeginUpdate.Call();

  trackingId = sampleFrame1.Id;

  string detObjName = radar.GetOrCreateDetectedObject.Call_Phys(trackingId, _ADAS.DataModel.EDetectedObjectType.IDetectedMovingObject);

  _ADAS.DataModel.IDetectedMovingObject detObj =  DORegistry.LookupDistributedObject<_ADAS.DataModel.IDetectedMovingObject>(detObjName, "ADAS");

  if (detObj != null)
  {
    detObj.moving_object.baseInfo.position.x.ImplValue = sampleFrame1.pos.x;
    detObj.moving_object.baseInfo.position.y.ImplValue = sampleFrame1.pos.y;
    detObj.moving_object.baseInfo.position.z.ImplValue = sampleFrame1.pos.z;
  }
}

[OnCANFrame]
public void OnCANFrame(NetworkDB.Frames.SampleFrame2 sampleFrame2)
{
  string detObjName = radar.GetDetectedObjectByTrackingId.Call(trackingId);

  _ADAS.DataModel.IDetectedMovingObject detObj =  DORegistry.LookupDistributedObject<_ADAS.DataModel.IDetectedMovingObject>(detObjName, "ADAS");

  if (detObj != null)
  {
    detObj.moving_object.baseInfo.dimension.height.ImplValue = sampleFrame2.dim.height;
    detObj.moving_object.baseInfo.dimension.width.ImplValue = sampleFrame2.dim.width;
    detObj.moving_object.baseInfo.dimension.length.ImplValue = sampleFrame2.dim.length;
  }

  radar.SetDetectedObjectCompleted.Call(trackingId, true);

  // alternative: Set all detected objects for this sensor completed
  // radar.SetDetectedObjectsCompleted.Call(true);

  radar.Update.Call();
}

[OnCalled(radar.MemberIDs.OnDetectedObjectUpdate)]
public void OnDetectedObjectUpdate(_ADAS.DataModel.ISensor_Types.OnDetectedObjectUpdate.TransientCallContext tcc)
{
  if(tcc.detObj.header.trackingId == trackingId)
  {
    // Possibility to set values manually
    tcc.detObj.header.existence_probability.PhysValue = 50.0;
  }
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)