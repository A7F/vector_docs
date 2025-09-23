# ChkQuery_EventFrameId

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
long ChkQuery_EventFrameId (dword CheckId)
```

## Method Syntax

[Method Syntax](../../../Shared/CAPL/General/ClassesAndObjects.md)

```
check.QueryEventFrameId()
```

## Description

Retrieves frame id of a schedule table for which the event has been sent.

## Parameters

- **CheckId**: Identifier of the queried Check.

## Return Values

- **\< 0**: Refers the query [error codes](../CAPLfunctionsTSLErrorCodes.md)
- **≥ 0**: Refers to the frame id

## Example

—
