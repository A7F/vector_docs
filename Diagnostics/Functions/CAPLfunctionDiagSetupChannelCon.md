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
