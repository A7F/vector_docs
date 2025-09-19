[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionGetSteadyClockStartTimeNS.md)

**CAPL Functions** » **General** » **Function Overview** » **GetSteadyClockStartTimeNS**

# GetSteadyClockStartTimeNS

[Valid for: CANoe DE](../../../Shared/FeatureAvailability.md) • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
int64 GetSteadyClockStartTimeNS();
```

## Description

Returns the measurement start time of a steady clock. This time is only useful in comparison with other times from that clock which you can get through `GetSteadyClockCurrentTimeNS()`.

The steady clock provides a monotonic **realtime**. That time has no relation to a **wallclock time** and may drift slightly in comparison to the time stamps of measured frames, since the used clock in the computer is not synchronized to the one in the network interfaces (e.g. Vector VN devices). The time also has no relation to the simulation time, which is correlated to those time stamps, but which is constant during the processing of an event and which is explicitly set to the target time of simulation timers.

The measurement start time is taken immediately before the [on start](../EventProcedures/CAPLfunctionsEventproceduresMeasurementSystem.md) handlers of the simulation nodes and similar functions are called.

The function returns 0 if called in the [on preStart](../EventProcedures/CAPLfunctionsEventproceduresMeasurementSystem.md) handler.

## Parameters

—

## Return Values

Measurement start time of a steady clock in nanoseconds.

## Example

```plaintext
Write("Since measurement start, %I64d nanoseconds have elapsed in realtime", 
      GetSteadyClockCurrentTimeNS() – GetSteadyClockStartTimeNS());
```

[GetSteadyClockStartDurationNS](CAPLfunctionGetSteadyClockStartDurationNS.md) • [GetSteadyClockCurrentTimeNS](CAPLfunctionGetSteadyClockCurrentTimeNS.md) • [GetMeasurementStartTime](CAPLfunctionGetMeasurementStartTime.md)

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
