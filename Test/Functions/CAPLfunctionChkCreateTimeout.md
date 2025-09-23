# ChkCreate_Timeout, ChkStart_Timeout

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

- `dword ChkCreate_Timeout (Duration aTimeout, char [] CaplCallback);`
- `dword ChkStart_Timeout (Duration aTimeout, char [] CaplCallback);`

## [Constructor](../../../Shared/CAPL/General/ClassesAndObjects.md)

- `TestCheck::CreateTimeout (Duration aTimeout, char [] CaplCallback);`
- `TestCheck::StartTimeout (Duration aTimeout, char [] CaplCallback);`

## Check Name

[Timeout (Check Description)](../../../TestCommands/CheckDescriptions/CDTimeout.md)

## Description

The check fires an event if the time has expired.

## Parameters

- **aTimeout**: \> 0; default unit [ms], if not changed with [ChkConfig_SetPrecision](CAPLfunctionChkConfigSetPrecision.md).
- **CaplCallback**: In simulation nodes this parameter has to be set. In test modules this parameter is optional.

## Return Values

- **0**: Check could not be created and must not be referenced
- **\> 0**: Check was created successfully and may be referenced using the returned (handle-) value

## Possible Errors

- CAPL callback does not exist

## Example

```plaintext
// checks the maximum duration of a sequence of actions
checkId = ChkStart_Timeout (2000);
TestAddCondition(checkId);
// sequence of different actions and waiting conditions
TestWaitForTimeout(1000);
TestRemoveCondition(checkId);
```

[Functions to Configure Checks](../CAPLfunctionsTSLConfigurationFunctions.md) • [Commands to Control Checks](../CAPLfunctionsTSLCheckControlCommands.md)
