# ChkQuery_EventSignalValueMin, ChkQuery_EventSignalValueMax

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

- `long ChkQuery_EventSignalValueMin(dword checkId, int64& value);`
- `long ChkQuery_EventSignalValueMax(dword checkId, int64& value);`
- `long ChkQuery_EventSignalValueMin(dword checkId, double& value);`
- `long ChkQuery_EventSignalValueMax(dword checkId, double& value);`

## Method Syntax

- `check.QueryEventSignalValueMin(int64& value);`
- `check.QueryEventSignalValueMax(int64& value);`
- `check.QueryEventSignalValueMin(double& value);`
- `check.QueryEventSignalValueMax(double& value);`

## Description

Enables access to the minimal and maximal measured values within a check.

## Parameters

- **checkId**: Identifier of the queried Check.
- **value**: Retrieval of value was successful.

**Note**: Use the **int64 parameters** for system variables of UInt64 and Int64 type to cover the whole value range. The int64 parameter is interpreted for system variables of UInt64 type as qword (uint64).

## Return Values

- **\<= 0**: Refers the query [error codes](../CAPLfunctionsTSLErrorCodes.md) in this chapter
- **\> 0**: Retrieval of value was successful.

## Available For

- [ChkCreate_MsgSignalValueInvalid](CAPLfunctionChkCreateMsgSignalValueInvalid.md)
- [ChkCreate_SignalValueChange](CAPLfunctionChkCreateSignalValueChange.md)

## Example

```plaintext
double maxValue;
int checkId;

checkId = ChkStart_MsgSignalValueInvalid (singalToObserve, 5.5, 10.5);    
TestAddCondition(checkId)
// sequence of different actions and waiting conditions
TestWaitForTimeout(1000);
ChkQuery_EventSignalValueMax(checkID, maxValue);

write("Max signal value=%f", maxValue);

TestRemoveCondition(checkId);
```
