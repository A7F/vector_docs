# _Diag_SetupChannelRequest, _Diag_SetupChannelReq

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

**Note**  
If the transport protocol is not connection oriented, [diag_SetupChannelCon](CAPLfunctionDiagSetupChannelCon.md) can be called immediately. In ECU simulations this callback is not necessary, because ECUs never initiate connections to the tester.

## Function Syntax

```plaintext
void _Diag_SetupChannelReq (); // form 1
void _Diag_SetupChannelRequest(char target[]); // form 2
```

## Description

With this function, the CAPL program of a tester implementation will be requested to open a channel to the ECU. After opening the channel, the CAPL program can call the function [diag_SetupChannelCon](CAPLfunctionDiagSetupChannelCon.md).

## Parameters

- **target**: Qualifier of the ECU to open a channel to.

## Return Values

—

## Example

```plaintext
_Diag_SetupChannelRequest(char target[])
{
  Diag_SetupChannelCon(); // On CAN there is no need to wait for the communication channel to be established
}
```

[diag_SetupChannelCon](CAPLfunctionDiagSetupChannelCon.md)
