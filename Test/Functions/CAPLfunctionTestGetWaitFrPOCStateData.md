# TestGetWaitFrPOCStateData

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long TestGetWaitFrPOCStateData (FrPOCState aPOCState);`
- `long TestGetWaitFrPOCStateData (dword index, FrPOCState aPOCState);`

## Description

If an event indicating a change of state on the FlexRay Communication Controller's protocol operation state machine is the last event that triggers a wait instruction, the event’s content can be called up with the first function.

The second function can only be used for "joined events". The number of the "joined event" (return value of "testJoin...") is here being used as an index.

## Parameters

- **aPOCState**: Event structure that should be filled in with this function (see selectors of event procedure [on FrPOCState](../../FlexRay/EventProcedures/CAPLfunctionOnFRPocState.md)).

- **Index**: Number of the "joined event" corresponds with the return value of "testJoin...".

## Return Values

- **0**: Data access successful
- **-1**: Data access could not be executed, the last event was not a FlexRay POC event

## Example

For an example see function [TestWaitForFrPOCState](CAPLfunctionTestWaitForFrPOCState.md).

[TestWaitForFrPOCState](CAPLfunctionTestWaitForFrPOCState.md) • [TestJoinFrPOCState](CAPLfunctionTestJoinFrPOCState.md)
