# ILControlStop

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

**Note**  
This function can only be used in the CAPL file that is attached to the appropriate node. The corresponding function [ILNodeControlStop](CAPLfunctionILNodeControlStop.md) can be used in a global node outside or in test modules.

## Function Syntax

`long ILControlStop()`

## Description

Sending is completely stopped. In this state the interaction layer is inoperative. Neither function calls, nor signal changes are considered during its inactivity and on its activation (by [ILControlStart](CAPLfunctionILControlStart.md)).

## Parameters

—

## Return Values

- **0**: No error.
- **-1**: Momentary state of the IL does not permit this query.
- **-50**: Nodelayer is inactive — possibly deactivated in the node’s configuration dialog.

## Example

—

[ILControlInit](CAPLfunctionILControlInit.md) • [ILControlStart](CAPLfunctionILControlStart.md)
