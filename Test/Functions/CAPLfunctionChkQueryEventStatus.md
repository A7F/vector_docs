# ChkQuery_EventStatus

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
long ChkQuery_EventStatus (dword aCheckId, char aBuffer[], dword aBufferLength);
```

## Method Syntax

[Method Syntax](../../../Shared/CAPL/General/ClassesAndObjects.md)

```plaintext
check.QueryEventStatus (char aBuffer[], dword aBufferLength);
```

## Description

Converts the status into a string that can be printed. Returns the number of characters written (\<= length).

## Parameters

- **aCheckId**: Identifier of the queried Check.
- **aBuffer**: Buffer where string is stored.
- **aBufferLength**: Length of provided buffer.

## Return Values

- **\< 0**: Refers the query [error codes](../CAPLfunctionsTSLErrorCodes.md)
- **≥ 0**: Number of characters

## Example

```plaintext
long result;
dword checkId;
char eventStatus[256];
checkId = ChkStart_MsgRelCycleTimeViolation(VehicleMotion, 0.9, 1.1);
// ... execute test sequence
result = ChkQuery_EventStatus(checkId, eventStatus, 256);
Write("result = %d", result);
Write("Event Status = %s", eventStatus);
```
