# diagCloseChannel

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

- `long diagCloseChannel(); // form 1`
- `long DiagCloseChannel(char ecuQualifier[]); // form 2`

## Description

Closes a diagnostic channel. State of the channel is Closed afterwards.

The channel the function refers to is set with the last call of [diagSetTarget](CAPLfunctionDiagSetTarget.md).

## Parameters

- **ecuQualifier**: Qualifier of the ECU or target as set in the diagnostic configuration dialog for the respective diagnostic description.

## Return Values

On success 0, otherwise [error code](../CAPLfunctionsDiagnosticsErrorCode.md).

## Example

—
