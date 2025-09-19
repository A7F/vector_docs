# diagGetTesterPresentState

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

- `long diagGetTesterPresentState()` // form 1
- `long diagGetTesterPresentState(char ecuQualifier[])` // form 2

## Description

Returns the state of autonomous/cyclical Tester Present requests from CANoe to the specified or current ECU.

**Note**: This function only returns the correct state if in the calling CAPL node no CAPL Callback interface for diagnostics is used.

**Status:**

- 0: sending Tester Present disabled for target ECU
- 1: sending Tester Present enabled for target ECU

## Parameters

- **ecuQualifier**: Qualifier of the ECU as specified in the diagnostic configuration dialog, for which the Tester Present state shall be queried. If no parameter is provided, the state of the current diagnostic target (set by [diagSetTarget(char ecuQualifier[]](CAPLfunctionDiagSetTarget.htm)) is returned.

## Return Values

[Error code](../CAPLfunctionsDiagnosticsErrorCode.md) or status

## Example

—

[diagStartTesterPresent](CAPLfunctionDiagStartTesterPresent.md) • [diagStopTesterPresent](CAPLfunctionDiagStopTesterPresent.md)
