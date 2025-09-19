[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestGetWaitFrFrameErrorData.md)

[CAPL Functions](../../CAPLfunctions.md) » [Test Feature Set](../CAPLfunctionsTFSOverview.md) » TestGetWaitFrFrameErrorData

# TestGetWaitFrFrameErrorData

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long TestGetWaitFrFrameErrorData (frFrameError aFrameError);`
- `long TestGetWaitFrFrameErrorData (dword index, frFrameError aFrameError);`

## Description

If a FlexRay frame error is the last event that triggers a wait instruction, the event’s content can be called up with the first function.

The second function can only be used for "joined events". The number of the "joined event" (return value of `testJoin...`) is here being used as an index.

## Parameters

- **aFrameError**: Event variable that should be filled in with this function.
- **Index**: Number of the "joined event" corresponds with the return value of `testJoin...`.

## Return Values

- **0**: Data access successful
- **-1**: Data access could not be executed, the last event was not a FlexRay Error Frame event

## Example

For an example see function [TestWaitForFrFrame](CAPLfunctionTestWaitForFrFrame.md) and replace all FrFrame by FrFrameError.

[TestWaitForFrFrameError](CAPLfunctionTestWaitForFrFrameError.md) • [TestJoinFrFrameErrorEvent](CAPLfunctionTestJoinFrFrameErrorEvent.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
