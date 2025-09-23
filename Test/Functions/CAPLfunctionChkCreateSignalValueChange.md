# ChkCreate_SignalValueChange, ChkStart_SignalValueChange

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

- `dword ChkCreate_SignalValueChange (Signal aObservedSignal, char [] CaplCallback); // form 1`
- `dword ChkStart_SignalValueChange (Signal aObservedSignal, char [] CaplCallback); // form 2`
- `dword ChkCreate_SignalValueChange (EnvVar EnvVarName, char [] CaplCallback); // form 3`
- `dword ChkStart_SignalValueChange (EnvVar EnvVarName, char [] CaplCallback); // form 4`
- `dword ChkCreate_SignalValueChange (sysVar aSysVar, char [] CaplCallback); // form 5`
- `dword ChkStart_SignalValueChange (sysVar aSysVar, char [] CaplCallback); // form 6`
- `dword ChkCreate_SignalValueChange (valueHandle* doValue, char [] CaplCallback); // form 7`
- `dword ChkStart_SignalValueChange (valueHandle* doValue, char [] CaplCallback); // form 8`
- `dword ChkCreate_SignalValueChange (valueHandle* doValue, functionPointer Callback); // form 9`
- `dword ChkStart_SignalValueChange (valueHandle* doValue, functionPointer Callback); // form 10`

## Constructor

- `TestCheck::CreateSignalValueChange (Signal aObservedSignal, char [] CaplCallback); // form 1`
- `TestCheck::StartSignalValueChange (Signal aObservedSignal, char [] CaplCallback); // form 2`
- `TestCheck::CreateSignalValueChange (EnvVar EnvVarName, char [] CaplCallback); // form 3`
- `TestCheck::StartSignalValueChange (EnvVar EnvVarName, char [] CaplCallback); // form 4`
- `TestCheck::CreateSignalValueChange (sysVar aSysVar, char [] CaplCallback); // form 5`
- `TestCheck::StartSignalValueChange (sysVar aSysVar, char [] CaplCallback); // form 6`
- `TestCheck::CreateSignalValueChange (valueHandle* doValue, char [] CaplCallback); // form 7`
- `TestCheck::StartSignalValueChange (valueHandle* doValue, char [] CaplCallback); // form 8`

## Check Name

[No Value Change](../../../TestCommands/CheckDescriptions/CDNoValueChange.md)

## Description

Checks the physical value of a signal or an environment variable. An event will be generated if the value changes.

**Note**: Dependent on the used parameter type, the appropriate bus context in a multibus environment has only to be set before the function is called if the corresponding database object will be ambiguous. Further information on [MultiBus Environment](../../../Shared/CAPL/General/TestMultiBusEnvironment.md).

## Parameters

- **aObservedSignal**: Signal to be checked.
- **EnvVarName**: Environment variable to be checked.
- **CaplCallback**: In simulation nodes, this parameter has to be set. In test modules, this parameter is optional.
- **aSysVar**: System variable to be checked.
- **doValue**: Distributed object member to be checked.

## Return Values

- **0**: Check could not be created and must not be referenced.
- **\> 0**: Check was created successfully and may be referenced using the returned (handle-) value.

## Possible Errors

- Signal is not mapped to message.
- CAPL callback does not exist.

## Check-specific Queries

- [ChkQuery_EventMessageId](CAPLfunctionChkQueryEventMessageId.md)
- [ChkQuery_EventMessageName](CAPLfunctionChkQueryEventMessageName.md)
- [ChkQuery_EventSignalValue](CAPLfunctionChkQueryEventSignalValue.md)
- [ChkQuery_EventSignalValueMin](CAPLfunctionChkQueryEventSignalValueMinMax.md)
- [ChkQuery_EventSignalValueMax](CAPLfunctionChkQueryEventSignalValueMinMax.md)

## Example

**Example 1**

```c
// checks that there is no change of the value of the signal
checkId = ChkStart_SignalValueChange(SignalToObserve);
TestAddCondition(checkId);
// sequence of different actions and waiting conditions
TestWaitForTimeout(1000);
TestRemoveCondition(checkId);
```

**Example 2: CAPL Callback**

```c
// checks that there is no change of the value of the signal
checkId = ChkStart_SignalValueChange(SignalToObserve, "CAPL_Callback");
TestAddCondition(checkId);
// sequence of different actions and waiting conditions
TestWaitForTimeout(1000);
TestRemoveCondition(checkId);
...
void CAPL_Callback(dword check)
{
  write("Check id is %d", check);
}
```

**Example 3: Function Pointer**

```c
// checks that there is no change of the value of the distributed object member
checkId = ChkStart_SignalValueChange(DOProvider.DoubleMember, delegate (dword check)
  {
    write("Check id is %d", check);
  });
TestAddCondition(checkId);
// sequence of different actions and waiting conditions
TestWaitForTimeout(1000);
TestRemoveCondition(checkId);
```

[Functions to Configure Checks](../CAPLfunctionsTSLConfigurationFunctions.md) • [Commands to Control Checks](../CAPLfunctionsTSLCheckControlCommands.md)
