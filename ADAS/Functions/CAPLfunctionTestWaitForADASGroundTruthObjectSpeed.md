[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ADAS/Functions/CAPLfunctionTestWaitForADASGroundTruthObjectSpeed.md)

## CAPL Functions » ADAS » TestWaitForADASGroundTruthObjectSpeed

### TestWaitForADASGroundTruthObjectSpeed

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

### Function Syntax

- `long TestWaitForADASGroundTruthObjectSpeed (dword overUnder, float threshold, int64 movingObjectId, long aTimeout); // form 1`
- `long TestWaitForADASGroundTruthObjectSpeed (dword overUnder, float threshold, int64 movingObjectId, int64 laneId, long aTimeout); // form 2`

### Description

Waits for the occurrence of the first Moving Object matching the speed conditions passed as arguments. Should the Moving Object not occur before the expiration of the time `aTimeout`, the wait condition is resolved, nevertheless.

### Parameters

- **overUnder**: Specifies if the speed should be over or under the specified value.
- **threshold**: Specified value that determines the maximum or minimum speed.
- **movingObjectId**: GroundTruthId of the Moving Object. Only a Moving Object with this `groundTruthId` triggers the wait condition. A `movingObjectdId` of -1 triggers for every Moving Object.
- **laneId**: Only a Moving Objects in the lane with this `laneId` can trigger the wait condition.
- **aTimeout**: Maximum time that should be waited [ms]. Transmission of 0: no timeout controlling.

### Return Values

- **-1**: General error, for example, functionality is not available.
- **0**: Resume due to timeout.
- **1**: Resume due to event occurred.

### Example

```c
enum VWaitThreshold
{
  kUnderThreshold = 0,
  kOverThreshold = 1
};

// form 1
if (TestWaitForADASGroundTruthObjectSpeed(kUnderThreshold, 3, -1, 1000))
{
  testStepPass("A Moving Object with speed under 30 m/s is present ");
}
else
{
  testStepFail("Timeout");
}

// form 2
if (TestWaitForADASGroundTruthObjectSpeed(kUnderThreshold, 30, 3, 1 , 1000))
{
  testStepPass("A Moving Object with Id 3 on lane 1 with a speed under 30 m/s is present ");
}
else
{
  testStepFail("Timeout");
}
```

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
