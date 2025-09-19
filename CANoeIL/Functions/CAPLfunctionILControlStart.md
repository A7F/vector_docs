# ILControlStart

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

**Note**  
This function can only be used in the CAPL file that is attached to the appropriate node. The corresponding function [ILNodeControlStart](CAPLfunctionILNodeControlStart.md) can be used in a global node outside or in test modules.

## Function Syntax

`long ILControlStart ()`

## Description

Cyclical sending starts; setting signals is now possible. Signal changes that occurred while the interaction layer was switched off (by [ILControlStop](CAPLfunctionILControlStop.md) or [ILControlSimulationOff](CAPLfunctionILControlSimulationOff.md)) are not considered on its activation.

## Parameters

—

## Return Values

- **0**: No error.
- **-1**: Momentary state of the IL does not permit this query.
- **-50**: Nodelayer is inactive — possibly deactivated in the node’s configuration dialog.

## Example

—

[ILControlInit](CAPLfunctionILControlInit.md) • [ILControlStop](CAPLfunctionILControlStop.md)
