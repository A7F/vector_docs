[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/LIN/Functions/CAPLfunctionLINStopScheduler.md)

[CAPL Functions](../../CAPLfunctions.md) » [LIN](../CAPLfunctionsLINOverview.md) » linStopScheduler

# linStopScheduler

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```c
void linStopScheduler();
```

## Description

This function stops the internal scheduler. This way a cyclical traversal of the current schedule table is stopped.

Scheduler can be started again by calling [linStartScheduler()](CAPLfunctionLINStartScheduler.md) function.

**Note**

- Calling this function in the event procedure [on preStart](../../Other/EventProcedures/CAPLfunctionsEventproceduresMeasurementSystem.md) prevents the scheduler from starting at the beginning of the measurement.
- If the Master node is not simulated or no schedule tables are defined, then this function will have no effect.

## Parameters

—

## Return Values

—

## Example

—
