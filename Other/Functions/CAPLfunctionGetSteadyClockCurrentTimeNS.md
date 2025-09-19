[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionGetSteadyClockCurrentTimeNS.md)

[CAPL Functions](../../CAPLfunctions.md) » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » GetSteadyClockCurrentTimeNS

# GetSteadyClockCurrentTimeNS

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
int64 GetSteadyClockCurrentTimeNS();
```

## Description

Returns the current time of a steady clock. This time is only useful in comparison with other times from that clock.

The steady clock provides a monotonic **realtime**. That time has no relation to a **wallclock time** and may drift slightly in comparison to the time stamps of measured frames, since the used clock in the computer is not synchronized to the one in the network interfaces (e.g. Vector VN devices). The time also has no relation to the simulation time, which is correlated to those time stamps, but which is constant during the processing of an event and which is explicitly set to the target time of simulation timers. Also note that the time stamps on different processes may not be comparable due to different drifts; this is in particular true when multiple machines are involved (e.g., distributed mode).

You can use this function mainly for measuring how much time a particular CAPL function or handler (or part of it) takes, so you can detect code which may have a performance impact.

**Note:** The function is equivalent to a C++ call of `std::chrono::duration_cast<std::chrono::nanoseconds>(std::chrono::steady_clock::now().time_since_epoch()).count();`

## Parameters

—

## Return Values

Current time of a steady clock in nanoseconds.

## Example

```plaintext
void SomePotentiallySlowFunction()
{
  stack int64 time = GetSteadyClockCurrentTimeNS();

  // do some potentially time consuming work

  Write("Function execution took %I64d nanoseconds",
  GetSteadyClockCurrentTimeNS() - time);
}
```

[GetSteadyClockStartDurationNS](CAPLfunctionGetSteadyClockStartDurationNS.md) • [GetSteadyClockStartTimeNS](CAPLfunctionGetSteadyClockStartTimeNS.md) • [timeNowInt64](CAPLfunctionTimeNowNS.md) • [getLocalTime](CAPLfunctionGetLocalTime.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) • [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
