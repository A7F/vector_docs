# GetDetectedObjectByTrackingId

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

**Note:** This CAPL function is also available in C#.

## Function Syntax

**C#**

```csharp
string GetDetectedObjectByTrackingId.Call(int trackingId);
```

**CAPL**

```capl
char[] GetDetectedObjectByTrackingId.Call(int trackingId);
```

## Description

This function gets the name of a detected object of a sensor based on the tracking Id as a string. If no object with the given tracking Id is present, an empty string is returned.

## Parameters

- **trackingId**: Id of the object

## Return Values

A string containing the name of the detected object. If no object with the given tracking Id is present, an empty string is returned.

## Example

In the examples it is assumed in each case that a DO object of the type IScenarioManager was created.

### CAPL

```capl
char detObjName [100];
memcpy(detObjName, radar.GetDetectedObjectByTrackingId.Call(5), elCount(radar.GetDetectedObjectByTrackingId.Call(5)));
```

### C#

```csharp
string detObjName = radar.GetDetectedObjectByTrackingId.Call(5);
```
