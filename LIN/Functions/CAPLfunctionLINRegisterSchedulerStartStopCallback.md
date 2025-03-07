[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/LIN/Functions/CAPLfunctionLINRegisterSchedulerStartStopCallback.md)

[CAPL Functions](../../CAPLfunctions.md) » [LIN](../CAPLfunctionsLINOverview.md) » linRegisterSchedulerStartStopCallback

# linRegisterSchedulerStartStopCallback

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```
dword linRegisterSchedulerStartStopCallback (char[] callbackName);
```

## Description

Registers a callback function which is invoked if a LIN scheduler is either started or stopped.

**Note**  
This function may only be called in the event procedure [on preStart](../../Other/EventProcedures/CAPLfunctionsEventproceduresMeasurementSystem.md).

## Parameters

- **callbackName**  
  The name of the callback function which should be registered. The callback must have the following signature:  
  `void func (dword channel, dword started, int64 eventTime)`

## Return Values

Returns **1** if the registration succeeded, otherwise **0**.

## Example

```plaintext
on preStart
{
  linRegisterSchedulerStartStopCallback("OnSchedulerStartStop");
}

void OnSchedulerStartStop (dword channel, dword started, int64 eventTime)
{
  if (started)
  {
    write("Scheduler on LIN channel %ld started at: %lld", channel, eventTime);
  }
  else
  {
    write("Scheduler on LIN channel %ld stopped at: %lld", channel, eventTime);
  }
}
```

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)