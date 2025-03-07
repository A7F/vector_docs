[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Diagnostics/Functions/CAPLfunctionDiagDisconnectRequest.md)

[CAPL Functions](../../CAPLfunctions.md) » [Diagnostics](../CAPLfunctionsDiagnosticsOverview.md) » _Diag_DisconnectReq, _Diag_DisconnectRequest

# _Diag_DisconnectReq, _Diag_DisconnectRequest

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

## Function Syntax

- `void _Diag_DisconnectReq(); // form 1`
- `void _Diag_DisconnectRequest(char target[]); // form 2`

## Description

The diagnostic communication channel to the target with the given qualifier shall be closed. For connectionless transport protocols, [diag_ClosedChannelInd](CAPLfunctionDiagClosedChannelInd.md) can be called immediately. Otherwise, the completion of the channel closing must be indicated when the TP layer indicates it.

For connection-oriented protocols, the CAPL program can call a close connection routine of the TP layer.

## Parameters

- **target**: Qualifier of the ECU whose communication channel shall be closed.

## Return Values

—

## Example

```c
// disconnect request callback for DoIP
_Diag_DisconnectReq()
{
  DoIP_CloseConnection();
}
```

[diag_ClosedChannelInd](CAPLfunctionDiagClosedChannelInd.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)