# ILControlResume

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

**Note**  
This function can only be used in the CAPL file that is attached to the appropriate node. The corresponding function [ILNodeControlResume](CAPLfunctionILNodeControlResume.md) can be used in a global node outside or in test modules.

## Function Syntax

```
long ILControlResume ()
```

## Description

Cyclical sending restarts.  
This function may only be used after [ILControlWait](CAPLfunctionILControlWait.md).

## Parameters

—

## Return Values

- **0**: No error.
- **-1**: Momentary state of the IL does not permit this query.
- **-50**: Node layer is inactive — possibly deactivated in the node's configuration dialog.

## Example

—

[ILControlInit](CAPLfunctionILControlInit.md) • [ILControlStart](CAPLfunctionILControlStart.md) • [ILControlStop](CAPLfunctionILControlStop.md) • [ILControlWait](CAPLfunctionILControlWait.md)
