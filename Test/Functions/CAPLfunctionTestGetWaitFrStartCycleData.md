[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestGetWaitFrStartCycleData.md)

[CAPL Functions](../../CAPLfunctions.md) » [Test Feature Set](../CAPLfunctionsTFSOverview.md) » TestGetWaitFrStartCycleData

# TestGetWaitFrStartCycleData

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```
long TestGetWaitFrStartCycleData (frStartCycle aFrStartCycle);
```

```
long TestGetWaitFrStartCycleData (dword index, frStartCycle aFrStartCycle);
```

## Description

If a FlexRay start cycle is the last event that triggers a wait instruction, the event’s content can be called up with the first function.

The second function can only be used for "joined events". The number of the "joined event" (return value of "testJoin...") is here being used as an index.

## Parameters

- **aFrStartCycleText**: Flexray Start Cycle variable that should be filled in with this function.
- **Index**: Number of the "joined event" corresponds with the return value of "testJoin...".

## Return Values

- **0**: Data access successful
- **-1**: Data access could not be executed, the last event was not a FlexRay start cycle event

## Example

For an example see function [TestWaitForFrStartCycle](CAPLfunctionTestWaitForFrStartCycle.md).

[TestWaitForFrStartCycle](CAPLfunctionTestWaitForFrStartCycle.md) • [TestJoinFrStartCycleEvent](CAPLfunctionTestJoinFrStartCycleEvent.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)