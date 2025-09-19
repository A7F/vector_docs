[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionChkCreateMsgSignalValueInvalid.md)

**CAPL Functions** » [Test Service Library](../CAPLfunctionsTSLOverview.md) » [Checks](../CAPLfunctionsTSLCheckOverview.md) » ChkCreate_MsgSignalValueInvalid, ChkStart_MsgSignalValueInvalid

# ChkCreate_MsgSignalValueInvalid, ChkStart_MsgSignalValueInvalid

**Valid for**: CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

- `dword ChkCreate_MsgSignalValueInvalid (Signal aObservedSignal, double aMinValue, double aMaxValue, char [] aCallback)` // form 1
- `dword ChkStart_MsgSignalValueInvalid (Signal aObservedSignal, double aMinValue, double aMaxValue, char [] aCallback)` // form 2
- `dword ChkCreate_MsgSignalValueInvalid (char aMessageName[], char aSignalName[], double aMinValue, double aMaxValue, char [] aCallback)` // form 3
- `dword ChkStart_MsgSignalValueInvalid (char aMessageName[], char aSignalName[], double aMinValue, double aMaxValue, char [] aCallback)` // form 4
- `dword ChkCreate_MsgSignalValueInvalid (EnvVarName, double aMinValue, double aMaxValue, char [] aCallback)` // form 5
- `dword ChkStart_MsgSignalValueInvalid (EnvVarName, double aMinValue, double aMaxValue, char [] aCallback)` // form 6
- `dword ChkCreate_MsgSignalValueInvalid (sysVar aSysVar, double aMinValue, double aMaxValue, char [] aCallback)` // form 7
- `dword ChkStart_MsgSignalValueInvalid (sysVar aSysVar, double aMinValue, double aMaxValue, char [] aCallback)` // form 8
- `dword ChkCreate_MsgSignalValueInvalid (sysVar aSysVar, int64 aMinValue, int64 aMaxValue, char [] aCallback)` // form 9
- `dword ChkStart_MsgSignalValueInvalid (sysVar aSysVar, int64 aMin-Value, int64 aMaxValue, char [] aCallback)` // form 10
- `dword ChkCreate_MsgSignalValueInvalid (valueHandle* doValue, double aMinValue, double aMaxValue, char [] aCallback); // form 11`
- `dword ChkStart_MsgSignalValueInvalid (valueHandle* doValue, double aMinValue, double aMaxValue, char [] aCallback); // form 12`
- `dword ChkCreate_MsgSignalValueInvalid (valueHandle* doValue, int64 aMinValue, int64 aMaxValue, char [] aCallback); // form 13`
- `dword ChkStart_MsgSignalValueInvalid (valueHandle* doValue, int64 aMinValue, int64 aMaxValue, char [] aCallback); // form 14`
- `dword ChkCreate_MsgSignalValueInvalid (valueHandle* doValue, double aMinValue, double aMaxValue, functionPointer Callback); // form 15`
- `dword ChkStart_MsgSignalValueInvalid (valueHandle* doValue, double aMinValue, double aMaxValue, functionPointer Callback); // form 16`
- `dword ChkCreate_MsgSignalValueInvalid (valueHandle* doValue, int64 aMinValue, int64 aMaxValue, functionPointer Callback); // form 17`
- `dword ChkStart_MsgSignalValueInvalid (valueHandle* doValue, int64 aMinValue, int64 aMaxValue, functionPointer Callback); // form 18`

## Constructor

- `TestCheck::CreateMsgSignalValueInvalid (Signal aObservedSignal, double aMinValue, double aMaxValue, char [] aCallback); // form 1`
- `TestCheck::StartMsgSignalValueInvalid (Signal aObservedSignal, double aMinValue, double aMaxValue, char [] aCallback); // form 2`
- `TestCheck::CreateMsgSignalValueInvalid (char aMessageName[], char aSignalNamel[], double aMinValue, double aMaxValue, char [] aCallback); // form 3`
- `TestCheck::StartMsgSignalValueInvalid (char aMessageName[], char aSignalName[], double aMinValue, double aMaxValue, char [] aCallback); // form 4`
- `TestCheck::CreateMsgSignalValueInvalid (EnvVarName, double aMinValue, double aMaxValue, char [] aCallback); // form 5`
- `TestCheck::StartMsgSignalValueInvalid (EnvVarName, double aMinValue, double aMaxValue, char [] aCallback); // form 6`
- `TestCheck::CreateMsgSignalValueInvalid (sysVar aSysVar, double aMinValue, double aMaxValue, char [] aCallback); // form 7`
- `TestCheck::StartMsgSignalValueInvalid (sysVar aSysVar, double aMinValue, double aMaxValue, char [] aCallback); // form 8`
- `TestCheck::CreateMsgSignalValueInvalid (sysVar aSysVar, int64 aMinValue, int64 aMaxValue, char [] aCallback); // form 9`
- `TestCheck::StartMsgSignalValueInvalid (sysVar aSysVar, int64 aMin-Value, int64 aMaxValue, char [] aCallback); // form 10`
- `TestCheck::CreateMsgSignalValueInvalid (valueHandle* doValue, double aMinValue, double aMaxValue, Callback aCallback); // form 11`
- `TestCheck::StartMsgSignalValueInvalid (valueHandle* doValue, double aMinValue, double aMaxValue, Callback aCallback); // form 12`
- `TestCheck::CreateMsgSignalValueInvalid (valueHandle* doValue, int64 aMinValue, int64 aMaxValue, Callback aCallback); // form 13`
- `TestCheck::StartMsgSignalValueInvalid (valueHandle* doValue, int64 aMinValue, int64 aMaxValue, Callback aCallback); // form 14`

## Check Name

[Value Valid](../../../TestCommands/CheckDescriptions/CDValueValid.md)

## Description

Check the value of a signal, of an environment variable or a system variable. The value should be outside the given value range (inclusive limits).

An event will be generated, if the value of the physical signal, the environment variable or the system variable is inside the given value range.

**Note**: Dependent on the used parameter type the appropriate bus context in a multibus environment has only to be set before the function is called if the corresponding database object will be ambiguous. Further information on site [MultiBus Environment](../../../Shared/CAPL/General/TestMultiBusEnvironment.md).

## Parameters

- **aObservedSignal**: Name of the signal to be checked. Must exist in DB.
- **aMessageName**: Name of the message of which the signal should be observed. Must exist in DB.
- **aSignalName**: Name of the signal to be checked. Must exist in the DB and must be mapped to aMessageName.
- **EnvVarName**: Environment variable to be checked.
- **aSysVar**: System variable to be checked.
- **doValue**: Distributed object member to be checked.
- **aMinValue**: aMinValue <= aMaxValue
- **aMaxValue**: aMinValue <= aMaxValue
- **aCallback**: In simulation nodes this parameter has to be set. In test modules this parameter is optional.

**Note**: Use the **int64 parameters** for system variables of UInt64 and Int64 type to cover the whole value range. The int64 parameter is interpreted for system variables of UInt64 type as qword (uint64).

## Return Values

- **0**: Check could not be created and must not be referenced
- **> 0**: Check was created successfully and may be referenced using the returned (handle-) value

## Possible Errors

- Value range(s) exceeded
- Message does not exist in the DB
- Signal is not mapped to message
- CAPL callback does not exist

## Check-specific Queries

- [ChkQuery_EventMessageId](CAPLfunctionChkQueryEventMessageId.md)
- [ChkQuery_EventMessageName](CAPLfunctionChkQueryEventMessageName.md)
- [ChkQuery_EventSignalValue](CAPLfunctionChkQueryEventSignalValue.md)
- [ChkQuery_EventSignalValueMin](CAPLfunctionChkQueryEventSignalValueMinMax.md)
- [ChkQuery_EventSignalValueMax](CAPLfunctionChkQueryEventSignalValueMinMax.md)

## Example

**Example 1**

```plaintext
// checks the value of the signal (should be outside the given range)
checkId = ChkStart_MsgSignalValueInvalid (SignalToObserve, 2.5, 3.7);
TestAddCondition(checkId);
// sequence of different actions and waiting conditions
TestWaitForTimeout(1000);
TestRemoveCondition(checkId);
```

**Example 2: CAPL Callback**

```plaintext
// checks the value of the signal (should be outside the given range)
checkId = ChkStart_MsgSignalValueInvalid (SignalToObserve, 2.5, 3.7, "CAPL_Callback");
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

```plaintext
// checks the value of the distributed object member (should be outside the given range)
checkId = ChkStart_MsgSignalValueInvalid (DOProvider.DoubleMember, 2.5, 3.7, delegate (dword check)
  {
    write("Check id is %d", check);
  });
TestAddCondition(checkId);
// sequence of different actions and waiting conditions
TestWaitForTimeout(1000);
TestRemoveCondition(checkId);
```

[Functions to Configure Checks](../CAPLfunctionsTSLConfigurationFunctions.md) • [Commands to Control Checks](../CAPLfunctionsTSLCheckControlCommands.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)