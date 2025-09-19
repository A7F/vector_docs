# diagIsChannelConnected

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
long diagIsChannelConnected(); // form 1
long DiagIsChannelConnected(char ecuQualifier[]); // form 2
```

## Description

Checks if a channel is already in state Connected. The channel the function refers to is set with the last call of [diagSetTarget](CAPLfunctionDiagSetTarget.md).

## Parameters

- **ecuQualifier**: Qualifier of the ECU or target as set in the diagnostic configuration dialog for the respective diagnostic description.

## Return Values

1 if channel is connected, 0 if channel is not connected, otherwise [error code](../CAPLfunctionsDiagnosticsErrorCode.md).

## Example

—
