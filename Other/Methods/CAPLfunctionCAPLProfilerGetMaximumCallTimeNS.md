[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Methods/CAPLfunctionCAPLProfilerGetMaximumCallTimeNS.md)

[CAPL Functions](../../CAPLfunctions.md) » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » CAPLProfiler::GetMaximumCallTimeNS

# CAPLProfiler::GetMaximumCallTimeNS

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```
qword CAPLProfiler::GetMaximumCallTimeNS();
```

## Description

Returns the maximum time for a measured profiler call (i.e., time between Start and Stop) in nanoseconds. If there are no measurements yet, returns 0.

## Parameters

—

## Return Values

- **0**: No measurements yet.
- **> 0**: Maximum time measured.

## Example

```cpp
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

[Start](CAPLfunctionCAPLProfilerStart.md) • [Stop](CAPLfunctionCAPLProfilerStop.md) • [Reset](CAPLfunctionCAPLProfilerReset.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)