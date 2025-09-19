[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionTimeToElapse.md)

[CAPL Functions](../../CAPLfunctions.md) » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » timeToElapse

# timeToElapse

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
long timeToElapse(timer t); // from 1
long timeToElapse(mstimer t); // from 2
```

## Method Syntax (Dynamic)

[Method](../../../Shared/CAPL/General/ClassesAndObjects.md) Syntax

```plaintext
long msTimer::timeToElapse();
```

## Description

Returns a value indicating how much more time will elapse before an [on timer](../EventProcedures/CAPLfunctionOnTimer.md) event procedure is called.

For form 1, the time value is returned in seconds; for form 2, the time value is returned in milliseconds.

If the timer is not active, -1 is returned. This is also the case in the [on timer](../EventProcedures/CAPLfunctionOnTimer.md) event procedure itself.

## Parameters

- **timer** or **mstimer** variable

## Return Values

Time to go until the timer elapses and the event procedure is called.

## Example

```plaintext
timer t;
setTimer(t, 5);
write("Time to elapse: %d", timeToElapse(t)); // writes 5
```

[Class: Timer, MS Timer](../../ObjectOrientedProg/CAPLfunctionsOOPTimer.md) • [setTimer](CAPLfunctionSetTimer.md) • [cancelTimer](CAPLfunctionCancelTimer.md) • [isTimerActive](CAPLfunctionIsTimerActive.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) • [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
