# diagGetCurrentEcu

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```
long diagGetCurrentEcu 
(char[] qualifier, dword bufferLen)
```

## Description

Gets the qualifier of the ECU for which the last event was processed, especially if a response was received from this ECU. This function can be used to determine the ECU that responded to a functional request.

In a diagnostics event handler in the measurement setup, this function will return the target of request primitives and the source of response primitives (the other communication partner is always a tester).

## Parameters

- **qualifier**: Output buffer
- **bufferLen**: Length of the output buffer

## Return Values

[Error code](../CAPLfunctionsDiagnosticsErrorCode.md) or length of the name provided.

## Example

```c
on diagResponse *
{
  char ecu[100];
  diagGetCurrentEcu(ecu, elcount(ecu));
  write("Received response from %s", ecu);
}

on key 'a'
{
  // Diagnostic description with ECU qualifier 'FunctionalGroup' configured for Functional Group Requests (FGR)
  diagRequest FunctionalGroup.DefaultSession_Start req1;
  diagSendRequest(req1); // Request is sent to functional group, therefore multiple ECUs may respond
}
```
