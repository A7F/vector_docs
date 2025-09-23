[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ADAS/Functions/CAPLfunctionTestGetWaitADASDetectedObject.md)

## TestGetWaitADASDetectedObject

[CAPL Functions](../../CAPLfunctions.md) » [ADAS](../CAPLfunctionsADASOverview.md) » TestGetWaitADASDetectedObject

### Function Syntax

```
long TestGetWaitADASDetectedObject (char[] detectedObjectName)
```

### Description

If a Detected Object was the last event that triggered a wait Instruction, the name of the Detected Object can be called up with the `TestGetWaitADASDetectedObject` function.

### Parameters

- **detectedObjectName**: The name of the Detected Object that triggered the wait instruction.

### Return Values

- **0**: Data access successful
- **-1**: Data access could not be executed

### Example

```c
enum VWaitThreshold
{
  kUnderThreshold = 0,
  kOverThreshold = 1
};

distObjRef ::ADAS::IDetectedMovingObject detMovingObj;
char buffer[100];

if(TestWaitForADASDistance(kUnderThreshold,30, 1000))
{
  if(TestGetWaitADASDetectedObject(buffer) == 0) // Get the name of the Detected Object that triggered the Wait Condition
    detMovingObj = (distObjRef ADAS::IDetectedMovingObject) lookupDistObj(buffer); // Get the Detected Object with the CAPL Function lookupDistObj
  if(detMovingObj.IsValid) // Check if the Detected Object is valid
  {
    // Do something with the Detected Object
  }
}
```
