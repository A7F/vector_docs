# ChkQuery_EventMessageContents

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
long ChkQuery_EventMessageContents (dword CheckId, byte buffer[], dword bufferlen);
```

## Method Syntax

[Method Syntax](../../../Shared/CAPL/General/ClassesAndObjects.md)

```
check.QueryEventMessageContents (byte buffer[], dword bufferlen);
```

## Description

Stores the data bytes of the message, for which the event has been sent, in the buffer and returns the number of stored data bytes (DLC).

## Parameters

- **CheckId**: Identifier of the queried Check.
- **buffer**: —
- **bufferlen**: —

## Return Values

- **\< 0**: Refers the query [error codes](../CAPLfunctionsTSLErrorCodes.md)
- **\> 0**: Number of stored data bytes (DLC)

## Available For

- [ChkStart_LINReconfRequestFormatViolation](CAPLfunctionChkStartLinReconfRequestFormatViolation.md): Result: All data bytes of the LIN reconfiguration request, which caused the event
- [ChkStart_LINETFViolation](CAPLfunctionChkStartLinEtfViolation.md): Result: All data bytes of the last invalid ETF single response

## Example

—
