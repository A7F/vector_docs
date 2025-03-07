[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Diagnostics/Functions/CAPLfunctionDiagConnectChannel.md)

**CAPL Functions** » **Diagnostics** » **diagConnectChannel**

# diagConnectChannel

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

- `long diagConnectChannel(); // form 1`
- `DiagConnectChannel(char ecuQualifier[]); // form 2`

## Description

Initiates the connection of a diagnostic channel. This function is called asynchronously, i.e., it immediately returns even if establishing the connection takes some more time. You can query the state of the diagnostic channel using [diagIsChannelConnected](CAPLfunctionDiagIsChannelConnected.md). Additionally, you can wait until the connection is established using [TestWaitForDiagChannelConnected](../../Test/Functions/CAPLfunctionTestWaitForDiagChannelConnected.md).

For form 1, the channel the function refers to is set with the last call of [diagSetTarget](CAPLfunctionDiagSetTarget.md).

## Parameters

- **ecuQualifier**: Qualifier of the ECU or target as set in the diagnostic configuration dialog for the respective diagnostic description.

## Return Values

On success 0, otherwise [error code](../CAPLfunctionsDiagnosticsErrorCode.md).

## Example

—

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)