[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionChkCreateMsgSignalValueRangeViolation.md)

**CAPL Functions** » [Test Service Library](../CAPLfunctionsTSLOverview.md) » [Checks](../CAPLfunctionsTSLCheckOverview.md) » ChkCreate_MsgSignalValueRangeViolation, ChkStart_MsgSignalValueRangeViolation

# ChkCreate_MsgSignalValueRangeViolation, ChkStart_MsgSignalValueRangeViolation

**Valid for**: CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

- `dword ChkCreate_MsgSignalValueRangeViolation (Signal aObservedSignal, double aMinValue, double aMaxValue, char [] aCallback); // form 1`
- `dword ChkStart_MsgSignalValueRangeViolation (Signal aObservedSignal, double aMinValue, double aMaxValue, char [] aCallback); // form 2`
- `dword ChkCreate_MsgSignalValueRangeViolation (char aMessageName[], char aSignalName[], double aMinValue, double aMaxValue, char [] aCallback); // form 3`
- `dword ChkStart_MsgSignalValueRangeViolation (char aMessageName[], char aSignalName[], double aMinValue, double aMaxValue, char [] aCallback); // form 4`
- `dword ChkCreate_MsgSignalValueRangeViolation (EnvVarName, double aMinValue, double aMaxValue, char [] aCallback); // form 5`
- `dword ChkStart_MsgSignalValueRangeViolation (EnvVarName, double aMinValue, double aMaxValue, char [] aCall-back); // form 6`
- `dword ChkCreate_MsgSignalValueRangeViolation (sysVar aSysVar, double aMinValue, double aMaxValue, char [] aCallback); // form 7`
- `dword ChkStart_MsgSignalValueRangeViolation (sysVar aSysVar, double aMinValue, double aMaxValue, char [] aCall-back); // form 8`
- `dword ChkCreate_MsgSignalValueRangeViolation (sysVar aSysVar, int64 aMinValue, int64 aMaxValue, char [] aCallback); // form 9`
- `dword ChkStart_MsgSignalValueRangeViolation (sysVar aSysVar, int64 aMinValue, int64 aMaxValue, char [] aCallback); // form 10`
- `dword ChkCreate_MsgSignalValueRangeViolation (valueHandle* doValue, double aMinValue, double aMaxValue, char [] aCallback); // form 11`
- `dword ChkStart_MsgSignalValueRangeViolation (valueHandle* doValue, double aMinValue, double aMaxValue, char [] aCallback); // form 12`
- `dword ChkCreate_MsgSignalValueRangeViolation (valueHandle* doValue, int64 aMinValue, int64 aMaxValue, char [] aCallback); // form 13`
- `dword ChkStart_MsgSignalValueRangeViolation (valueHandle* doValue, int64 aMinValue, int64 aMaxValue, char [] aCallback); // form 14`
- `dword ChkCreate_MsgSignalValueRangeViolation (valueHandle* doValue, double aMinValue, double aMaxValue, functionPointer Callback); // form 15`
- `dword ChkStart_MsgSignalValueRangeViolation (valueHandle* doValue, double aMinValue, double aMaxValue, functionPointer Callback); // form 16`
- `dword ChkCreate_MsgSignalValueRangeViolation (valueHandle* doValue, int64 aMinValue, int64 aMaxValue, functionPointer Callback); // form 17`
- `dword ChkStart_MsgSignalValueRangeViolation (valueHandle* doValue, int64 aMinValue, int64 aMaxValue, functionPointer Callback); // form 18`

## Constructor

- `TestCheck::CreateMsgSignalValueRangeViolation (Signal aObservedSignal, double aMinValue, double aMaxValue, char [] aCallback); // form 1`
- `TestCheck::StartMsgSignalValueRangeViolation (Signal aObservedSignal, double aMinValue, double aMaxValue, char [] aCallback); // form 2`
- `TestCheck::CreateMsgSignalValueRangeViolation (char aMessageName[], char aSignalName[], double aMinValue, double aMaxValue, char [] aCallback); // form 3`
- `TestCheck::StartMsgSignalValueRangeViolation (char aMessageName[], char aSignalName[], double aMinValue, double aMaxValue, char [] aCallback); // form 4`
- `TestCheck::CreateMsgSignalValueRangeViolation (EnvVarName, double aMinValue, double aMaxValue, char [] aCallback); // form 5`
- `TestCheck::StartMsgSignalValueRangeViolation (EnvVarName, double aMinValue, double aMaxValue, char [] aCall-back); // form 6`
- `TestCheck::CreateMsgSignalValueRangeViolation (sysVar aSysVar, double aMinValue, double aMaxValue, char [] aCallback); // form 7`
- `TestCheck::StartMsgSignalValueRangeViolation (sysVar aSysVar, double aMinValue, double aMaxValue, char [] aCall-back); // form 8`
- `TestCheck::CreateMsgSignalValueRangeViolation (sysVar aSysVar, int64 aMinValue, int64 aMaxValue, char [] aCallback); // form 9`
- `TestCheck::StartMsgSignalValueRangeViolation (sysVar aSysVar, int64 aMinValue, int64 aMaxValue, char [] aCallback); // form 10`
- `TestCheck::CreateMsgSignalValueRangeViolation (valueHandle* doValue, double aMinValue, double aMaxValue, char [] aCallback); // form 11`
- `TestCheck::StartMsgSignalValueRangeViolation (valueHandle* doValue, double aMinValue, double aMaxValue, char [] aCallback); // form 12`
- `TestCheck::CreateMsgSignalValueRangeViolation (valueHandle* doValue, int64 aMinValue, int64 aMaxValue, char [] aCallback); // form 13`
- `TestCheck::StartMsgSignalValueRangeViolation (valueHandle* doValue, int64 aMinValue, int64 aMaxValue, char [] aCallback); // form 14`

## Check Name

[Value Valid](../../../TestCommands/CheckDescriptions/CDValueValid.md)

## Description

Checks the value of a signal, an environment variable or a system variable. The value should be inside the given value range (inclusive limits).

An event will be generated, if the value of physical signal, the environment variable or the system variable is outside the given value range.

**Note**: The first event is executed with the current physical value when the check is started. Subsequent events only take place when the physical value changes.

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

## Return Values

- **0**: Check could not be created and must not be referenced
- **> 0**: Check was created successfully and may be referenced using the returned (handle-) value.

## Possible Errors

- Value range(s) exceeded
- Message does not exist in the DB
- Signal is not mapped to message
- CAPL callback does not exist

## Check-specific Queries

- [ChkQuery_EventMessageId](CAPLfunctionChkQueryEventMessageId.md)
- [ChkQuery_EventMessageName](CAPLfunctionChkQueryEventMessageName.md)
- [ChkQuery_EventSignalValue](CAPLfunctionChkQueryEventSignalValue.md)

## Example

**Example 1**

```plaintext
// checks the value of the signal (should be inside the given range)
checkId = ChkStart_MsgSignalValueRangeViolation (SignalToObserve, 2.5, 3.7);
TestAddCondition(checkId);
// sequence of different actions and waiting conditions
TestWaitForTimeout(1000);
TestRemoveCondition(checkId);
```

**Example 2: CAPL Callback**

```plaintext
// checks the value of the signal (should be inside the given range)
checkId = ChkStart_MsgSignalValueRangeViolation (SignalToObserve, 2.5, 3.7, "CAPL_Callback");
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
// checks the value of the distributed object member (should be inside the given range)
checkId = ChkStart_MsgSignalValueRangeViolation (DOProvider.DoubleMember, 2.5, 3.7, delegate (dword check)
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