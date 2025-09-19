[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionIsTimerActive.md)

**CAPL Functions** » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » isTimerActive

# isTimerActive

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

- `int isTimerActive(timer t); // form 1`
- `int isTimerActive(mstimer t); // form 2`

## Description

Return value indicates whether a specific timer is active. This is the case between the call to the [setTimer](CAPLfunctionSetTimer.md) function and the call to the [on timer](../EventProcedures/CAPLfunctionOnTimer.md) event procedure.

## Parameters

- **timer** or **mstimer** variable

## Return Values

- 1, if the timer is active; otherwise 0.
- 0 is also returned within the [on timer event](../EventProcedures/CAPLfunctionOnTimer.md) procedure.

## Example

```plaintext
timer t;
write("Active? %d", isTimerActive(t)); // writes 0
setTimer(t, 5);
write("Active? %d", isTimerActive(t)); // writes 1
```

[setTimer](CAPLfunctionSetTimer.md) • [cancelTimer](CAPLfunctionCancelTimer.md) • [timeToElapse](CAPLfunctionTimeToElapse.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
