# diagDisconnectChannel

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

- `long diagDisconnectChannel(); // form 1`
- `long DiagDisconnectChannel(char ecuQualifier[]); // form 2`

## Description

Disconnects a channel. State of the channel is Opened afterwards.

The channel the function refers to is set with the last call of [diagSetTarget](CAPLfunctionDiagSetTarget.md).

## Parameters

- **ecuQualifier**: Qualifier of the ECU or target as set in the diagnostic configuration dialog for the respective diagnostic description.

## Return Values

On success 0, otherwise [error code](../CAPLfunctionsDiagnosticsErrorCode.md).

## Example

—
