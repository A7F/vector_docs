[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ADAS/Functions/CAPLfunctionTestWaitForADASGroundTruthObjectInLane.md)

**CAPL Functions** » **ADAS** » **TestWaitForADASGroundTruthObjectInLane**

# TestWaitForADASGroundTruthObjectInLane

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Changes

This function was renamed from **TestWaitForADASObjectInLane** in CANoe DE product version 16 SP3.

## Function Syntax

```plaintext
long TestWaitForADASGroundTruthObjectInLane(int64 movingObjectId, int64 laneId, dword timeout);
```

## Description

Waits for the first occurrence of a specified Moving Object which is completely in the given lane. The wait condition triggers only if the Moving Object field **assigned_lanes** only contains one element.

## Parameters

- **movingObjectId**: GroundTruthId of the Moving Object. The Moving Object can be the ego vehicle. Only a Moving Object with this groundTruthId triggers the wait condition.

- **laneId**: Only a Moving Objects in the lane with this laneId can trigger the wait condition.

- **timeout**: Maximum time that should be waited [ms]. Transmission of 0: no timeout controlling.

## Return Values

- **-1**: General error, for example, functionality is not available.

- **0**: Resume due to timeout.

- **1**: Resume due to event occurred.

## Example

```plaintext
if(TestWaitForADASGroundTruthObjectInLane(103, 1, 1000)) // Waits for MovingObject with ID 103 on the lane with ID 1
{
    testStepPass("MovingObject 103 on Lane 1");
}
else
{
    testStepFail("Timeout");
}
```

[TestWaitForADASGroundTruthObjectInSameLane](CAPLfunctionTestWaitForADASGroundTruthObjectInSameLane.md) • [TestWaitForADASGroundTruthObjectLaneSwitch](CAPLfunctionTestWaitForADASGroundTruthObjectLaneSwitch.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)