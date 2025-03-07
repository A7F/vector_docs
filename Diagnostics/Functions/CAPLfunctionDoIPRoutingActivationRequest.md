[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Diagnostics/Functions/CAPLfunctionDoIPRoutingActivationRequest.md)

CAPL Functions » [Diagnostics](../CAPLfunctionsDiagnosticsOverview.md) » _DoIP_RoutingActivationRequest

# _DoIP_RoutingActivationRequest

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

**Note**  
The following DoIP CAPL function is only available with the modeling library **DoIP.dll** and eventually an appropriate implementation of the CAPL Callback Interface. Information about the DoIP DLL and the CAPL Callback Interface you find here:

- [DoIP CAPL Introduction](../CAPLDiagnosticDoIP.md)
- [AN-IND-1-012_CAPL_Callback_Interface.pdf](javascript:startDemoLoader('AN-IND-1-012_CAPL_Callback_Interface.pdf'))
- [AN-IND-1-026_DoIP_in_CANoe.pdf](javascript:startDemoLoader('AN-IND-1-026_DoIP_in_CANoe.pdf'))

## Function Syntax

```plaintext
long _DoIP_RoutingActivationRequest(dword sourceAddress,
dword activationType, dword reserved, dword OEM,
BYTE sendResponse[], BYTE responseCodeOut[]);
```

## Description

A request for routing activation was received in a vehicle simulation. It is possible to ignore, accept or deny the request, and to specify if a response message is sent.

## Parameters

- **sourceAddress**: Logical address of the tester that sent the request.
- **activationType**: The tester has requested this type of connection, e.g. WWH-OBD or default.
- **reserved**: The value of the **reserved** field in the request message.
- **OEM**: The value of the **OEM** field in the request, or 0, if field is not present.
- **sendResponse**: Output parameter to indicate whether the simulation shall send a routing activation response message:
  - 0: Do not send a response message
  - 1: Send a response message
  - other: reserved
- **responseCodeOut**: If a response is sent, this value will be used as response code.

## Return Values

- **0**: Process request and send a response as if callback was not present (default).
- **1**: The activation has failed, i.e. routing is not activated in the simulation.
- **2**: The activation was successful, i.e. routing is activated.

## Example

```plaintext
long _DoIP_RoutingActivationRequest(dword sourceAddress, dword activationType,dword reserved, dword OEM, BYTE sendResponse[], BYTE responseCodeOut[])
{
  write("_DoIP_RoutingActivationRequest(%04x, 0x%02x, reserved=%08x, OEM=%08x)", sourceAddress, activationType, reserved, OEM);
  // sendResponse[0]    is always 1    (default: send response)
  // responseCodeOut[0] is always 0x10

  // Accept default or WWH-OBD
  if(activationType <= 0x01)
    return 0;  // continue with default behavior

  // Ignore a specific activation type, i.e. do not even send a response
  if(activationType == 0x99)
  {
    sendResponse[0] = 0;
    return 1;  // deny routing activation
  }

  // Accept a specific activation type only if reserved value is correct
  if(IsValidForActivationType( activationType, reserved))
    return 2;  // allow routing activation

  // All other activation types shall be denied
  responseCodeOut[0] = 0x06; // UnsupportedActivationType
  return 1; // deny routing activation
}
```

[DoIP_SetRoutingActivationOEMSpecific](CAPLfunctionDoIPSetRoutingActivationOEMSpecific.md) • [DoIP_ConfigureRoutingActivationResponse](CAPLfunctionDoIPConfigureRoutingActivationResponse.md)