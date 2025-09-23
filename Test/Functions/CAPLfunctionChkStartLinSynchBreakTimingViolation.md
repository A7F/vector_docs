[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionChkStartLinSynchBreakTimingViolation.md)

[CAPL Functions](../../CAPLfunctions.md) » [Test Service Library](../CAPLfunctionsTSLOverview.md) » [Checks](../CAPLfunctionsTSLCheckOverview.md) » ChkStart_LINSynchBreakTimingViolation

# ChkStart_LINSynchBreakTimingViolation

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
dword ChkStart_LINSynchBreakTimingViolation (dword MinBreakLen, dword MaxBreakLen);
dword ChkStart_LINSynchBreakTimingViolation (dword MinBreakLen, dword MaxBreakLen, char[] CaplCallback);
```

## Description

Checks the timing of the synchronization break field in LIN headers.

An event will be generated, if the measured length [in bit times] of break low phase is outside of the specified range.

## Parameters

- **MinBreakLen**
  - `0`: Minimum length of break low phase shall not be checked
  - `>0`: Minimum allowed length of break low phase
  - Unit: bit time

- **MaxBreakLen**
  - `0`: Maximum length of break low phase shall not be checked
  - `>0`: Maximum allowed length of break low phase
  - Unit: bit time

- **CaplCallback**
  - Name of CAPL callback function to be called on generated event. In simulation nodes this parameter has to be set. In test modules this parameter is optional.

## Return Values

- **0**: Check could not be created and must not be referenced
- **> 0**: Check was created successfully and may be referenced using the returned (handle-) value.

## Possible Errors

- Range specified for synch break length is invalid
- CAPL callback does not exist

## Check-specific Queries

- [ChkQuery_EventTiming](CAPLfunctionChkQueryEventTiming.md)
- [ChkQuery_EventInterval](CAPLfunctionChkQueryEventInterval.md)
- [ChkQuery_EventMessageId](CAPLfunctionChkQueryEventMessageId.md)

## Example

```plaintext
...
dword checkId;
ChkConfig_SetPrecision(9); // switch to ns precision
// Create and start the check for LIN break low phase violation
checkId = ChkStart_LINSynchBreakTimingViolation(13, 20, "LINSynchBreakCallback"); 
ChkConfig_SetPrecision(3); // switch to ms precision (default)
...
// CAPL callback for violation notification
void LINSynchBreakCallback (dword aCheckId)
{
   ChkQuery_EventStatusToWrite(aCheckId);
}
```
