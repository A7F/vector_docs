[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionSetTimerCyclic.md)

[CAPL Functions](../../CAPLfunctions.md) » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » setTimerCyclic

# setTimerCyclic

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

- `void setTimerCyclic(msTimer t, long firstDuration, long period); // form 1`
- `void setTimerCyclic(msTimer t, long period); // form 2`
- `void setTimerCyclic(timer t, int64 periodInNs); // form 3`

## Method Syntax (Dynamic)

- `void msTimer::setCyclic(long firstDuration, long period);`
- `void msTimer::setCyclic(long period);`
- `void timer::setCyclic(int64 periodInNs);`

## Description

Sets a cyclical timer.

With form 2, **firstDuration** is implicitly the same as period, i.e. the timer runs precisely according to period the first time.

## Parameters

- **t**: The timer to be set.
- **firstDuration**: Time in milliseconds until the timer runs out for the first time.
- **period**: Time in milliseconds in which the timer is restarted in case of expiration.
- **periodInNs**: Time in nanoseconds in which the timer is restarted in case of expiration.

## Return Values

—

## Example

Starting of a timer that expires the first time 10 ms after the start of measurement and thereafter every 20 ms (10 ms, 30 ms, 50 ms, 70 ms etc.)

```plaintext
variables {
   msTimer t;
}
on start {
   setTimerCyclic(t, 10, 20)
}
```

[cancelTimer](CAPLfunctionCancelTimer.md) • [setTimer](CAPLfunctionSetTimer.md)
