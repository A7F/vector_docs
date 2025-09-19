# diagStartTesterPresent

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

- `long diagStartTesterPresent(); // form 1`
- `long diagStartTesterPresent(char ecuQualifier[]); // form 2`

## Description

Starts sending autonomous/cyclical Tester Present requests from CANoe to the specified or current ECU.

## Parameters

- **ecuQualifier**: Qualifier of the ECU as specified in the diagnostic configuration dialog, for which the Tester Present service shall be started. If no parameter is provided, sending of Tester Present requests is started for the current diagnostic target (set by [diagSetTarget(char ecuQualifier[]](CAPLfunctionDiagSetTarget.htm)).

  **Note**: This function will only start the Tester Present service if in the calling CAPL node no CAPL Callback interface for diagnostics is used.

## Return Values

[Error code](../CAPLfunctionsDiagnosticsErrorCode.md)

## Example

—

[diagGetTesterPresentState](CAPLfunctionDiagGetTesterPresentState.md) • [diagStopTesterPresent](CAPLfunctionDiagStopTesterPresent.md)
