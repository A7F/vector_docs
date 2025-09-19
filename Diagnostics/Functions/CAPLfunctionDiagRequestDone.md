# diag_RequestDone

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

- `long diag_RequestDone(); // form 1`
- `long diag_RequestDone(char target[]); // form 2`

## Description

The processing of the current diagnostic request completed. This function can be called if the diagnostic communication layer detected a timeout, i.e. the ECU did not respond in time. Calling this function allows the CAPL program to abort waiting for a response on the request.

## Parameters

- **target**: Stop processing of the current request sent to the ECU with this qualifier.

## Return Values

[Error code](../CAPLfunctionsDiagnosticsErrorCode.md)

## Example

```plaintext
on timer tP2
{
  // No response was received within P2
  diag_RequestDone(gCurrentECU);
}
```
