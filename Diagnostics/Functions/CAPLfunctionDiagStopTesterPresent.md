[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Diagnostics/Functions/CAPLfunctionDiagStopTesterPresent.md)

**CAPL Functions** » [Diagnostics](../CAPLfunctionsDiagnosticsOverview.md) » diagStopTesterPresent

# diagStopTesterPresent

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

- `long diagStopTesterPresent (); // form 1`
- `long diagStopTesterPresent (char ecuQualifier[]); // form 2`

## Description

Stops sending autonomous/cyclical Tester Present requests from CANoe to the specified or current ECU.

## Parameters

- **ecuQualifier**: Qualifier of the ECU as specified in the diagnostic configuration dialog, for which the Tester Present service shall be stopped. If no parameter is provided, sending of Tester Present requests is stopped for the current diagnostic target (set by [diagSetTarget(char ecuQualifier[]](CAPLfunctionDiagSetTarget.htm)).

  **Note**: This function will only stop the Tester Present service if in the calling CAPL node no CAPL Callback interface for diagnostics is used.

## Return Values

[Error code](../CAPLfunctionsDiagnosticsErrorCode.md)

## Example

—

[diagGetTesterPresentState](CAPLfunctionDiagGetTesterPresentState.md) • [diagStartTesterPresent](CAPLfunctionDiagStartTesterPresent.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)