# ChkStart_LINMasterInitTimeViolation

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `dword ChkStart_LINMasterInitTimeViolation (duration MinTime, duration MaxTime);`
- `dword ChkStart_LINMasterInitTimeViolation (duration MinTime, duration MaxTime, char[] CaplCallback);`

## Constructor

[TestCheck::StartLINMasterInitTimeViolation (duration MinTime, duration MaxTime);](../../../Shared/CAPL/General/ClassesAndObjects.md)
- `TestCheck::StartLINMasterInitTimeViolation (duration MinTime, duration MaxTime, char[] CaplCallback);`

## Description

Checks an initialization time of LIN Master. The initialization state is entered on switching on and on waking up. An event will be generated if the initialization time is out of the specified range.

**Note**: This function verifies the initialization time on waking up only, i.e., a time between getting Wakeup signal and the first header transmitted by the Master. For a LIN 2.0 compliance, the initialization time has to be in the range [100 .. 150] ms.

**Note**: Dependent on the used parameter type, the appropriate bus context in a multibus environment has only to be set before the function is called if the corresponding database object will be ambiguous. Further information on site [MultiBus Environment](../../../Shared/CAPL/General/TestMultiBusEnvironment.md).

## Parameters

- **MinTime**
  - `0`: Minimum time shall not be checked
  - `\>0`: Minimum allowed initialization time
  - Unit: Can be set with [ChkConfig_SetPrecision](CAPLfunctionChkConfigSetPrecision.md).

- **MaxTime**
  - `0`: Maximum time shall not be checked
  - `\>0`: Maximum allowed initialization time
  - Unit: Can be set with [ChkConfig_SetPrecision](CAPLfunctionChkConfigSetPrecision.md).

- **CaplCallback**
  - Name of CAPL callback function to be called on generated event. In simulation nodes, this parameter has to be set. In test modules, this parameter is optional.

## Return Values

- **0**: Check could not be created and must not be referenced
- **\> 0**: Check was created successfully and may be referenced using the returned (handle-) value.

## Possible Errors

- Range specified for initialization time is invalid
- CAPL callback does not exist

## Check-specific Queries

- [ChkQuery_EventInterval](CAPLfunctionChkQueryEventInterval.md)

## Example

```cpp
...
dword checkId;
// Create and start the check for LIN Master initialization time violation
checkId = ChkStart_LINMasterInitTimeViolation(100, 150, "LINMasterInitTimeCallback");
...
// CAPL callback for violation notification
void LINMasterInitTimeViolation (dword aCheckId)
{
   ChkQuery_EventStatusToWrite(aCheckId);
}
```

[Functions to Configure Checks](../CAPLfunctionsTSLConfigurationFunctions.md) • [Commands to Control Checks](../CAPLfunctionsTSLCheckControlCommands.md)
