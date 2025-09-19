[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Methods/CAPLfunctionCAPLProfilerStop.md)

[CAPL Functions](../../CAPLfunctions.md) » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » CAPLProfiler::Stop

# CAPLProfiler::Stop

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
long CAPLProfiler::Stop();
```

## Description

Stops the time measurement of the profiler. Stop() must be called as many times as Start() has been called. Then the measured time is used to update the statistics of the profiler.

## Parameters

—

## Return Values

- **0**: Success
- **> 0**: Profiler was already running. You will need to call Stop once for each Start call.
- **-1**: Profiler is not running (Start was not called).

## Example

```plaintext
void MyFunctionProfiler()
{
  CAPLProfiler profiler;
  char avgTimeString[20]; char maxTimeString[20];
  profiler.Start();

  MyFunction();

  profiler.Stop();
  TimeToString(profiler.GetAverageCallTimeNS(), avgTimeString);
  TimeToString(profiler.GetMaximumCallTimeNS(), maxTimeString);
  Write("MyFunction execution time: %s on average, %s maximum", avgTimeString, maxTimeString);
}
```

[Start](CAPLfunctionCAPLProfilerStart.md) • [Reset](CAPLfunctionCAPLProfilerReset.md) • GetAverageCallTimeNS

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
