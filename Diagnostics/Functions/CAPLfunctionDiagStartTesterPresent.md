[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Diagnostics/Functions/CAPLfunctionDiagStartTesterPresent.md)

[CAPL Functions](../../CAPLfunctions.md) » [Diagnostics](../CAPLfunctionsDiagnosticsOverview.md) » diagStartTesterPresent

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

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)