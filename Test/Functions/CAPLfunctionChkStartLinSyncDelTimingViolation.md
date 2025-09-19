[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionChkStartLinSyncDelTimingViolation.md)

**CAPL Functions** » **Test Service Library** » **Checks** » ChkStart_LINSyncDelTimingViolation

# ChkStart_LINSyncDelTimingViolation

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `dword ChkStart_LINSyncDelTimingViolation (float MinDelLen, float MaxDelLen);`
- `dword ChkStart_LINSyncDelTimingViolation (float MinDelLen, float MaxDelLen, char[] CaplCallback);`

## Constructor

[TestCheck::StartLINSyncDelTimingViolation](../../../Shared/CAPL/General/ClassesAndObjects.md)

- `TestCheck::StartLINSyncDelTimingViolation (float MinDelLen, float MaxDelLen);`
- `TestCheck::StartLINSyncDelTimingViolation (float MinDelLen, float MaxDelLen, char[] CaplCallback);`

## Description

Checks the timing of the synchronization break field in LIN headers. An event will be generated if the measured length [in bit times] of break delimiter is outside of the specified range.

**Note**: Dependent on the used parameter type, the appropriate bus context in a multibus environment has only to be set before the function is called if the corresponding database object will be ambiguous. Further information on site [MultiBus Environment](../../../Shared/CAPL/General/TestMultiBusEnvironment.md).

## Parameters

- **MinDelLen**
  - `0`: Minimum length of break delimiter shall not be checked
  - `>0`: Minimum allowed length of break delimiter
  - Unit: bit time

- **MaxDelLen**
  - `0`: Maximum length of break delimiter shall not be checked
  - `>0`: Maximum allowed length of break delimiter
  - Unit: bit time

- **CaplCallback**
  - Name of CAPL callback function to be called on generated event. In simulation nodes this parameter has to be set. In test modules this parameter is optional.

## Return Values

- **0**: Check could not be created and must not be referenced
- **> 0**: Check was created successfully and may be referenced using the returned (handle-) value.

## Possible Errors

- Range specified for delimiter length is invalid
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
// Create and start the check for LIN Synch Delimiter violation
checkId = ChkStart_LINSyncDelTimingViolation(1, 5, "LINSyncDelimiterCallback"); 
ChkConfig_SetPrecision(3); // switch to ms precision (default)
...
// CAPL callback for violation notification
void LINSyncDelimiterCallback (dword aCheckId)
{
   ChkQuery_EventStatusToWrite(aCheckId);
}
```

[Functions to Configure Checks](../CAPLfunctionsTSLConfigurationFunctions.md) • [Commands to Control Checks](../CAPLfunctionsTSLCheckControlCommands.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
