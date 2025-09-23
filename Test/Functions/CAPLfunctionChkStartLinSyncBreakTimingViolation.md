# ChkStart_LINSyncBreakTimingViolation

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```c
dword ChkStart_LINSyncBreakTimingViolation (float MinBreakLen, float MaxBreakLen);
dword ChkStart_LINSyncBreakTimingViolation (float MinBreakLen, float MaxBreakLen, char[] CaplCallback);
```

## Constructor

[Constructor](../../../Shared/CAPL/General/ClassesAndObjects.md)

```c
TestCheck::StartLINSyncBreakTimingViolation (float MinBreakLen, float MaxBreakLen);
TestCheck::StartLINSyncBreakTimingViolation (float MinBreakLen, float MaxBreakLen, char[] CaplCallback);
```

## Description

Checks the timing of the synchronization break field in LIN headers. An event will be generated if the measured length [in bit times] of break low phase is outside of the specified range.

**Note**: Dependent on the used parameter type, the appropriate bus context in a multibus environment has only to be set before the function is called if the corresponding database object will be ambiguous. Further information on site [MultiBus Environment](../../../Shared/CAPL/General/TestMultiBusEnvironment.md).

## Parameters

- **MinBreakLen**
  - `0`: Minimum length of break low phase shall not be checked
  - `\>0`: Minimum allowed length of break low phase
  - Unit: bit time

- **MaxBreakLen**
  - `0`: Maximum length of break low phase shall not be checked
  - `\>0`: Maximum allowed length of break low phase
  - Unit: bit time

- **CaplCallback**
  - Name of CAPL callback function to be called on generated event. In simulation nodes, this parameter has to be set. In test modules, this parameter is optional.

## Return Values

- `0`: Check could not be created and must not be referenced
- `\> 0`: Check was created successfully and may be referenced using the returned (handle-) value.

## Possible Errors

- Range specified for synch break length is invalid
- CAPL callback does not exist

## Check-specific Queries

- [ChkQuery_EventTiming](CAPLfunctionChkQueryEventTiming.md)
- [ChkQuery_EventInterval](CAPLfunctionChkQueryEventInterval.md)
- [ChkQuery_EventMessageId](CAPLfunctionChkQueryEventMessageId.md)

## Example

```c
...
dword checkId;
ChkConfig_SetPrecision(9); // switch to ns precision
// Create and start the check for LIN break low phase violation
checkId = ChkStart_LINSyncBreakTimingViolation(13, 20, "LINSyncBreakCallback"); 
ChkConfig_SetPrecision(3); // switch to ms precision (default)
...
// CAPL callback for violation notification
void LINSyncBreakCallback (dword aCheckId)
{
   ChkQuery_EventStatusToWrite(aCheckId);
}
```

[Functions to Configure Checks](../CAPLfunctionsTSLConfigurationFunctions.md) • [Commands to Control Checks](../CAPLfunctionsTSLCheckControlCommands.md)
