[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Diagnostics/Functions/CAPLfunctionDiagDisconnectChannel.md)

**CAPL Functions** » **Diagnostics** » **diagDisconnectChannel**

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

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)