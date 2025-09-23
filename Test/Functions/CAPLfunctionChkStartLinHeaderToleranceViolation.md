# ChkStart_LINHeaderToleranceViolation

**Valid for**: CANoe DE • CANoe4SW DE

## Function Syntax

- `dword ChkStart_LINHeaderToleranceViolation (float Tolerance);`
- `dword ChkStart_LINHeaderToleranceViolation (float Tolerance, char[] CaplCallback);`

## Constructor

- `TestCheck::StartLINHeaderToleranceViolation (float Tolerance);`
- `TestCheck::StartLINHeaderToleranceViolation (float Tolerance, char[] CaplCallback);`

## Description

Checks the LIN header transmission time. An event will be generated if the measured header transmission time is over the specified tolerance.

**Note:** For a LIN 2.0 compliance, the Tolerance has to be in the range [0 .. 40]%.

**Note:** Dependent on the used parameter type, the appropriate bus context in a multibus environment has only to be set before the function is called if the corresponding database object will be ambiguous. Further information on site [MultiBus Environment](../../../Shared/CAPL/General/TestMultiBusEnvironment.md).

## Parameters

- **Tolerance**: Allowed tolerance for Header transmission time.  
  Value range: [0 .. 40]  
  Unit: percents [%]

- **CaplCallback**: Name of CAPL callback function to be called on generated event. In simulation nodes this parameter has to be set. In test modules this parameter is optional.

## Return Values

- **0**: Check could not be created and must not be referenced
- **\> 0**: Check was created successfully and may be referenced using the returned (handle-) value.

## Check-specific Queries

- [ChkQuery_EventInterval](CAPLfunctionChkQueryEventInterval.md)
- [ChkQuery_EventMessageId](CAPLfunctionChkQueryEventMessageId.md)
- [ChkQuery_EventTiming](CAPLfunctionChkQueryEventTiming.md)

## Example

```plaintext
...
dword checkId;
// Create and start the check for LIN Header tolerance
checkId = ChkStart_LINHeaderToleranceViolation(40.0, "LINHeaderToleranceCallback");
...
// CAPL callback for violation notification
void LINHeaderToleranceCallback (dword aCheckId)
{
   ChkQuery_EventStatusToWrite(aCheckId);
}
```

[Functions to Configure Checks](../CAPLfunctionsTSLConfigurationFunctions.md) • [Commands to Control Checks](../CAPLfunctionsTSLCheckControlCommands.md)
