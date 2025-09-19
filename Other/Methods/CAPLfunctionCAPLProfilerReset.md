[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Methods/CAPLfunctionCAPLProfilerReset.md)

## CAPLProfiler::Reset

[CAPL Functions](../../CAPLfunctions.md) » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » CAPLProfiler::Reset

### Function Syntax

```plaintext
long CAPLProfiler::Reset();
```

### Description

Resets the profiler statistics. After the call, the profiler won’t have any time measurements stored.

### Parameters

—

### Return Values

- **0**: Success
- **1**: Profiler is currently running; Reset call is not allowed.

### Example

—

[Start](CAPLfunctionCAPLProfilerStart.md) • [Stop](CAPLfunctionCAPLProfilerStop.md) • GetAverageCallTimeNS

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
