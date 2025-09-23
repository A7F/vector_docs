# GetSteadyClockStartDurationNS

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
int64 GetSteadyClockStartDurationNS();
```

## Description

Returns the duration of the measurement start in nanoseconds. The duration returned is the one needed for all [on start](../EventProcedures/CAPLfunctionsEventproceduresMeasurementSystem.md) handlers of simulation nodes and similar functions. It does not include the time needed e.g. for [on preStart](../EventProcedures/CAPLfunctionsEventproceduresMeasurementSystem.md) handlers, for compilation of CAPL programs, initialization of hardware etc.

You can use the function mainly for detecting whether the measurement start takes too much time, maybe because of an inefficient on start handler.

## Parameters

—

## Return Values

Measurement start time of a steady clock in nanoseconds.

The function returns 0 if called in the [on start](../EventProcedures/CAPLfunctionsEventproceduresMeasurementSystem.md) or [on preStart](../EventProcedures/CAPLfunctionsEventproceduresMeasurementSystem.md) handler.

## Example

```plaintext
Write("Measurement start took %I64d nanoseconds", GetSteadyClockStartDurationNS());
```

[GetSteadyClockStartTimeNS](CAPLfunctionGetSteadyClockStartTimeNS.md) • [GetSteadyClockCurrentTimeNS](CAPLfunctionGetSteadyClockCurrentTimeNS.md) • [GetMeasurementStartTime](CAPLfunctionGetMeasurementStartTime.md)
