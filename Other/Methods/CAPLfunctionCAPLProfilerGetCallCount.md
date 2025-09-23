[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Methods/CAPLfunctionCAPLProfilerGetCallCount.md)

**CAPL Functions** » **General** » **Function Overview** » **CAPLProfiler::GetCallCount**

# CAPLProfiler::GetCallCount

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```
qword CAPLProfiler::GetCallCount();
```

## Description

Returns the number of measured profiler calls (i.e., times between Start and Stop). With this method, you can also use the profiler to check how often some code is called.

## Parameters

—

## Return Values

- **0**: No measurements yet.
- **> 0**: Number of measurements.

## Example

```c
void MyFunctionProfiler()
{
  CAPLProfiler profiler;
  char avgTimeString[20];
  profiler.Start();

  MyFunction();

  profiler.Stop();
  TimeToString(profiler.GetAverageCallTimeNS(), avgTimeString);
  Write("MyFunction execution time: %s on average (%I64d calls)", avgTimeString, profiler.GetCallCount());
}
```

[Start](CAPLfunctionCAPLProfilerStart.md) • [Stop](CAPLfunctionCAPLProfilerStop.md) • [Reset](CAPLfunctionCAPLProfilerReset.md)
