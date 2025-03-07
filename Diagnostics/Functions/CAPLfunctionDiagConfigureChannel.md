[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Diagnostics/Functions/CAPLfunctionDiagConfigureChannel.md)

[CAPL Functions](../../CAPLfunctions.md) » [Diagnostics](../CAPLfunctionsDiagnosticsOverview.md) » _Diag_ConfigureChannel

# _Diag_ConfigureChannel

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

## Function Syntax

```plaintext
void _Diag_ConfigureChannel(char target[]);
```

## Description

This callback function will be called when a diagnostic request has to be sent to a new target. The CAPL node can configure the transport protocol, e.g. set CAN IDs for sending and receiving.

## Parameters

- **target**: Qualifier of the ECU to communicate with.

## Return Values

—

## Example

```plaintext
_Diag_ConfigureChannel(char target[])
{
  long connectionHandle;
  connectionHandle = CreateConnection(target);
  TPLayer_SetTxId(connectionHandle, GetTxId(target));
  TPLayer_SetRxId(connectionHandle, GetRxId(target));
}
```

[_Diag_SetChannelParameters](CAPLfunctionDiagSetChannelParameters.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)