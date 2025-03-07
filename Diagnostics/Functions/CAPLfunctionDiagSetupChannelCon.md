[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Diagnostics/Functions/CAPLfunctionDiagSetupChannelCon.md)

[CAPL Functions](../../CAPLfunctions.md) » [Diagnostics](../CAPLfunctionsDiagnosticsOverview.md) » diag_SetupChannelCon

# diag_SetupChannelCon

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

## Function Syntax

```plaintext
long diag_SetupChannelCon ();
```

## Description

This function communicates to CANoe, that a communication channel is available to the communication partner and data can be sent.

For connectionless transport protocols this function can be called out of the callback [_Diag_SetupChannelReq](CAPLfunctionDiagSetupChannelRequest.md).

## Parameters

—

## Return Values

[Error code](../CAPLfunctionsDiagnosticsErrorCode.md)

## Example

—

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)