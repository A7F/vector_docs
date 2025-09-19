[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionChkQueryEventSignalValueMinMaxAsyncResult.md)

[CAPL Functions](../../CAPLfunctions.md) » [Test Service Library](../CAPLfunctionsTSLOverview.md) » [Status Report Functions](../CAPLfunctionsTSLStatusReportFunctions.md) » ChkQuery_EventSignalValueMin_AsyncResult, ChkQuery_EventSignalValueMax_AsyncResult

# ChkQuery_EventSignalValueMin_AsyncResult, ChkQuery_EventSignalValueMax_AsyncResult

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

- `long ChkQuery_EventSignalValueMin_AsyncResult(dword checkId, int64& value);`
- `long ChkQuery_EventSignalValueMax_AsyncResult(dword checkId, int64& value);`
- `long ChkQuery_EventSignalValueMin_AsyncResult(dword checkId, double& value);`
- `long ChkQuery_EventSignalValueMax_AsyncResult(dword checkId, double& value);`

## Method Syntax

- `check.QueryEventSignalValueMinAsyncResult(int64& value);`
- `check.QueryEventSignalValueMaxAsyncResult(int64& value);`
- `check.QueryEventSignalValueMinAsyncResult(double& value);`
- `check.QueryEventSignalValueMaxAsyncResult(double& value);`

## Description

Enables access to the minimal and maximal measured values within a check. The data has to be queried first using [testWaitForCheckQuery](CAPLfunctionTestWaitForCheckQuery.md).

## Parameters

- **checkId**: Identifier of the queried Check.
- **Value**: Contains according minimal/maximal value after function call.

**Note**: Use the **int64 parameters** for system variables of UInt64 and Int64 type to cover the whole value range. The int64 parameter is interpreted for system variables of UInt64 type as qword (uint64).

## Return Values

- **≤ 0**: Refers the query [error codes](../CAPLfunctionsTSLErrorCodes.md)
- **> 0**: Retrieval of value was successful.

## Available For

- [ChkCreate_MsgSignalValueInvalid](CAPLfunctionChkCreateMsgSignalValueInvalid.md)
- [ChkCreate_SignalValueChange](CAPLfunctionChkCreateSignalValueChange.md)

## Example

```plaintext
long result;
dword checkId;
double maxValue;
double minValue;
checkId = ChkStart_MsgSignalValueInvalid (singalToObserve, 5.5, 10.5); TestAddCondition(checkId)
// sequence of different actions and waiting conditions
TestWaitForTimeout(1000);
result = testWaitForCheckQuery(checkId, 10000);
if (result == 1)
{
  result = ChkQuery_EventSignalValueMax_AsyncResult(checkId, maxValue);
  result = ChkQuery_EventSignalValueMin_AsyncResult(checkId, minValue);
}
```

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
