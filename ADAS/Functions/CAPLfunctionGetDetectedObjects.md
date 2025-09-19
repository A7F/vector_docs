# GetDetectedObjects

[CAPL Functions](../../CAPLfunctions.md) » [ADAS](../CAPLfunctionsADASOverview.md) » GetDetectedObjects

Valid for: CANoe DE

**Note**  
This CAPL function is also available in C#.

## Function Syntax

**C#**  
`ADAS.DetectedObject_List GetDetectedObjects.Call();`

**CAPL**  
`ADAS.DetectedObject_List GetDetectedObjects.Call();`

## Description

Gets all detected objects of a sensor.

## Parameters

—

## Return Values

A string array containing all detected objects of the sensor.

## Example

In the examples it is assumed in each case that a DO object of the type IScenarioManager was created.

### CAPL

```plaintext
int countDetObj = 0;
array _ADAS::DataModel::DetectedObject_List detectedObjectNames;
memcpy(detectedObjectNames, radar.GetDetectedObjects.Call());
countDetObj = elCount(detectedObjectNames);
```

### C#

```plaintext
_ADAS.DataModel.DetectedObject_List detObjNames = radar.GetDetectedObjects.Call();
int countDetObj = detObjNames.Length;
```
