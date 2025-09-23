# ChkQuery_EventNodeName

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long ChkQuery_EventNodeName (dword CheckId, char buffer[], dword bufferlen);
```

## Method Syntax

[Method](../../../Shared/CAPL/General/ClassesAndObjects.md) Syntax

```plaintext
check.QueryEventNodeName (char buffer[], dword bufferlen);
```

## Description

Stores the name of the node, for which the event has been sent, in the buffer and returns the length of the name, or 0 if specified for a range of nodes.

## Parameters

- **CheckId**: Identifier of the queried Check.
- **buffer**: —
- **bufferlen**: —

## Return Values

- **\< 0**: Refers the query [error codes](../CAPLfunctionsTSLErrorCodes.md)
- **\> 0**: Length of the node name

## Available For

- [ChkStart_LINDiagDelayTimesViolation](CAPLfunctionChkStartLinDiagDelayTimesViolation.md): Result: Node name for which the diagnostic delay has been violated
- [ChkStart_LINRespToleranceViolation](CAPLfunctionChkStartLinRespToleranceViolation.md): Result: name of the node which caused response tolerance violation
- [ChkStart_LINRespErrorSignal](CAPLfunctionChkStartLinRespErrorSignal.md): Result: the name of the node, for which the Response_Error has been notified

## Example

—
