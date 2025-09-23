[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ADAS/Functions/CAPLfunctionGetDetectedObjectByGroundTruthId.md)

## CAPL Functions » ADAS » GetDetectedObjectByGroundTruthId

### GetDetectedObjectByGroundTruthId

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

**Note**  
This CAPL function is also available in C#.

### Function Syntax

**C#**  
`string GetDetectedObjectByGroundTruthId.Call(int groundTruthId);`

**CAPL**  
`char[] GetDetectedObjectByGroundTruthId.Call(int groundTruthId);`

### Description

This function gets the name of a ground truth object of a sensor based on the ground truth Id as a string. If no object with the given ground truth Id is present, an empty string is returned.

### Parameters

- **groundTruthId**: Id of the object

### Return Values

- A string containing the name of the ground truth object.
- If no object with the given ground truth Id is present, an empty string is returned.

### Example

In the examples it is assumed in each case that a DO object of the type IScenarioManager was created.

#### CAPL

```plaintext
char groundTruthObjName [100];
memcpy(groundTruthObjName, radar.GetDetectedObjectByGroundTruthId.Call(5), elCoun
(radar.GetDetectedObjectByGroundTruthId.Call(5)));
```

#### C#

```plaintext
string groundTruthObjName = radar.GetDetectedObjectByGroundTruthId.Call(5);
```
