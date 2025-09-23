# ChkQuery_Valid_AsyncResult

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long ChkQuery_Valid_AsyncResult(dword aCheckId);
```

## Method Syntax

[Method Syntax](../../../Shared/CAPL/General/ClassesAndObjects.md)

```plaintext
check.QueryValidAsyncResult();
```

## Description

Examines whether a check with particular Id is valid. The data has to be queried first using [testWaitForCheckQuery](CAPLfunctionTestWaitForCheckQuery.md).

## Parameters

- **aCheckId**: Identifier of the queried Check.

## Return Values

- **\< 0**: Refer the query [error codes](../CAPLfunctionsTSLErrorCodes.md)
- **= 0**: Id is invalid
- **\> 0**: Valid Id

## Example

```plaintext
long result;
dword checkId;
checkId = ChkStart_MsgRelCycleTimeViolation(VehicleMotion, 0.9, 1.1);
// ... execute test sequence
result = testWaitForCheckQuery(checkId, 10000);
if (result == 1)
  result = ChkQuery_Valid_AsyncResult(checkId);
```
