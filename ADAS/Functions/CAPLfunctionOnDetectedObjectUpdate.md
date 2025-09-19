# OnDetectedObjectUpdate

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

**Note**: This CAPL function is also available as C# function.

## Function Syntax

**C#**

```csharp
void OnDetectedObjectUpdate(_ADAS.DataModel.ISensor_Types.OnDetectedObjectUpdate.TransientCallContext tcc)
```

**CAPL**

```capl
void OnDetectedObjectUpdate()
```

## Description

A call of this method for a sensor sends all the data of the sensor and the detected objects that have been marked as completed. This method is called when a detected object has been updated. In this callback method there is a possibility to change the data before the actual update.

## Parameters

- **tcc**

  **C#**: Call Context of the Callback. Contains the detected object (cct.detObj)

  **CAPL**: —

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
