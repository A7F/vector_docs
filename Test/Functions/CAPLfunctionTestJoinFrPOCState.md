[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestJoinFrPOCState.md)

[CAPL Functions](../../CAPLfunctions.md) » [Test Feature Set](../CAPLfunctionsTFSOverview.md) » TestJoinFrPOCState

# TestJoinFrPOCState

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long TestJoinFrPOCState () // form 1`
- `long TestJoinFrPOCState (dword aPOCState) // form 2`
- `long TestJoinFrPOCState (dword aPOCState, dword aWUState) // form 3`

## Description

Completes the current set of "joined events" with the transmitted event. This function does not wait.

**Note**: Consider to set always the appropriate bus context in a multibus environment before the function is called. Further information on site [MultiBus Environment](../../../Shared/CAPL/General/TestMultiBusEnvironment.md).

## Parameters

- **aPOCState**: The POC state the function will wait for (see selector 'FR_POCState' in event procedure [on FrPOCState](../../FlexRay/EventProcedures/CAPLfunctionOnFRPocState.md)). If set to '-1' in combination with a 'WUState' the function will wait only for a Wakeup state (any POC state will be accepted). Available from CANoe 7.2.

- **aWUState**: The Wakeup state the function will wait for (see selector 'FR_Info2' in event procedure [on FrPOCState](../../FlexRay/EventProcedures/CAPLfunctionOnFRPocState.md)). Available from CANoe 7.2.

## Return Values

- **-3**: Join error
- **-1**: General error, for example, functionality is not available
- **> 0**: Number of the joined event

## Example

For an example see function [TestWaitForFrPOCState](CAPLfunctionTestWaitForFrPOCState.md).

[TestWaitForFrPOCState](CAPLfunctionTestWaitForFrPOCState.md) • [TestGetWaitFrPOCStateData](CAPLfunctionTestGetWaitFrPOCStateData.md) • [TestWaitForAnyJoinedEvent](CAPLfunctionTestWaitForAnyJoinedEvent.md) • [TestWaitForAllJoinedEvents](CAPLfunctionTestWaitForAllJoinedEvents.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
