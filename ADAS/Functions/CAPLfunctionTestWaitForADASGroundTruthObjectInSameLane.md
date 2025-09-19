# TestWaitForADASGroundTruthObjectInSameLane

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Changes

This function was renamed from **TestWaitForADASObjectInSameLane** in CANoe DE product version 16 SP3.

## Function Syntax

```plaintext
long TestWaitForADASGroundTruthObjectInSameLane(int64 movingObjectId, dword timeout);
```

## Description

Waits for the first occurrence of a specified Moving Object which is completely in the lane of the ego vehicle. The wait condition triggers only if the Moving Object field **assigned_lanes** only contains one element.

## Parameters

- **movingObjectId**: GroundTruthId of the Moving Object. Only a Moving Object with this groundTruthId triggers the wait condition.
- **timeout**: Maximum time that should be waited [ms]. Transmission of 0: no timeout controlling.

## Return Values

- **-1**: General error, for example, functionality is not available.
- **0**: Resume due to timeout.
- **1**: Resume due to event occurred.

## Example

```plaintext
if(TestWaitForADASGroundTruthObjectInSameLane(103, 1000)) // Waits for MovingObject with ID 103 on the lane of the ego vehicle
{
    testStepPass("MovingObject 103 on EgoLane");
}
else
{
    testStepFail("Timeout");
}
```

[TestWaitForADASGroundTruthObjectInLane](CAPLfunctionTestWaitForADASGroundTruthObjectInLane.md) • [TestWaitForADASGroundTruthObjectLaneSwitch](CAPLfunctionTestWaitForADASGroundTruthObjectLaneSwitch.md)
