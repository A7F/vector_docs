# ILControlInit

**Valid for**: CANoe DE • CANoe4SW DE

## Function Syntax

```
long ILControlInit ()
```

## Description

Initialization of CANoe IL. This function may only be used in [on preStart](../../Other/EventProcedures/CAPLfunctionsEventproceduresMeasurementSystem.md) to prevent the IL autostart function.

## Parameters

—

## Return Values

- **0**: No error.
- **-1**: Momentary state of the IL does not permit this query.
- **-50**: Nodelayer is inactive — possibly deactivated in the node’s configuration dialog.

## Example

—

[ILControlStart](CAPLfunctionILControlStart.md) • [ILControlStop](CAPLfunctionILControlStop.md)
