[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionChkQueryEventStatusAsyncResult.md)

**CAPL Functions** » [Test Service Library](../CAPLfunctionsTSLOverview.md) » [Status Report Functions](../CAPLfunctionsTSLStatusReportFunctions.md) » ChkQuery_EventStatus_AsyncResult

# ChkQuery_EventStatus_AsyncResult

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
long ChkQuery_EventStatus_AsyncResult(dword aCheckId, char aBuffer[], dword aBufferLength);
```

## Method Syntax

[Method Syntax](../../../Shared/CAPL/General/ClassesAndObjects.md)

```
check.Query_EventStatus_AsyncResult(char aBuffer[]);
```

## Description

Converts the status into a string that can be printed. Returns the number of characters written (\<= length).

The data has to be queried first using [testWaitForCheckQuery](CAPLfunctionTestWaitForCheckQuery.md).

## Parameters

- **aCheckId**: Identifier of the queried Check.
- **aBuffer**: Buffer where string is stored.
- **aBufferLength**: Length of provided buffer.

## Return Values

- **\< 0**: Refers the query [error codes](../CAPLfunctionsTSLErrorCodes.md)
- **≥ 0**: Number of characters

## Example

```c
long result;
dword checkId;
char eventStatus[256];
checkId = ChkStart_MsgRelCycleTimeViolation(VehicleMotion, 0.9, 1.1);
// ... execute test sequence
result = testWaitForCheckQuery(checkId, 10000);
if (result == 1)
{
  result = ChkQuery_EventStatus_AsyncResult(checkId, eventStatus, 256);
  Write("result = %d", result);
  Write("Event Status = %s", eventStatus);
}
```
