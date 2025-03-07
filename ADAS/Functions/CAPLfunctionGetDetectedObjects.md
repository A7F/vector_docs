[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ADAS/Functions/CAPLfunctionGetDetectedObjects.md)

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

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)