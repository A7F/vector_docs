# TestWaitForADASGroundTruthObjectLaneSwitch

[CAPL Functions](../../CAPLfunctions.md) » [ADAS](../CAPLfunctionsADASOverview.md) » TestWaitForADASGroundTruthObjectLaneSwitch

Valid for: CANoe DE

## Changes

This function was renamed from **TestWaitForADASObjectLaneSwitch** in CANoe DE product version 16 SP3.

## Function Syntax

- `long TestWaitForADASGroundTruthObjectLaneSwitch (int64 movingObjectId, dword timeout); //form 1`
- `long TestWaitForADASGroundTruthObjectLaneSwitch (int64 movingObjectId, int64 laneId, dword timeout); //form 2`

## Description

Waits for the first occurrence of a specified Moving Object which switches the lanes. If a laneId is specified, only lane switches to this lane trigger the wait condition. The wait condition triggers as soon as the Moving Object field **assigned_lanes** contains the given laneId. If the laneId isn’t specified, every change of the Moving Object field **assigned_lanes** triggers the wait condition.

## Parameters

- **movingObjectId**: GroundTruthId of the Moving Object. Only a Moving Object with this groundTruthId triggers the wait condition.
- **laneId**: Only a Moving Objects in the lane with this laneId can trigger the wait condition.
- **timeout**: Maximum time that should be waited [ms]. Transmission of 0: no timeout controlling.

## Return Values

- **-1**: General error, for example, functionality is not available.
- **0**: Resume due to timeout.
- **1**: Resume due to event occurred.

## Example

```c
if(TestWaitForADASGroundTruthObjectLaneSwitch(100, 1000)) // form 1; Waits for a Moving Object with ID 100 to switch the lane
{
    testStepPass("EgoVehicle LaneSwitch");
}
else
{
    testStepFail("timeout");
}

if(TestWaitForADASGroundTruthObjectLaneSwitch(100, 1, 1000)) // form 2; Waits for a Moving Object with ID 100 to switch to lane 1
{
    testStepPass("EgoVehicle LaneSwitch Lane 1");
}
else
{
    testStepFail("timeout");
}
```

[TestWaitForADASGroundTruthObjectInLane](CAPLfunctionTestWaitForADASGroundTruthObjectInLane.md) • [TestWaitForADASGroundTruthObjectInSameLane](CAPLfunctionTestWaitForADASGroundTruthObjectInSameLane.md)
