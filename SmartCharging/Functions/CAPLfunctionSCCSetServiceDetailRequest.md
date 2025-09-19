[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCSetServiceDetailRequest.md)

# SCC_SetServiceDetailRequest

[CAPL Functions](../../CAPLfunctions.md) » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [V2G Simulation Control](../CAPLFunctionsSmartChargingOverview.md#V2GSimControl) » [EV Functions](../CAPLFunctionsSmartChargingOverview.md#V2GSimControl) » SCC_SetServiceDetailRequest

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE  •  CANoe4SW DE

## Function Syntax

```
long SCC_SetServiceDetailRequest(dword ServiceId)
```

## Description

Requests the vehicle to send a Service Detail Request during the [ServiceDiscoveryRes](../Callbacks/CAPLfunctionSCCServiceDiscoveryRes.md) or [ServiceDetailRes](../Callbacks/CAPLfunctionSCCServiceDetailRes.md) callback. It is possible for multiple Service Detail Requests, or none at all, to be sent. If this function is not called, the vehicle skips this message.

**Note**: This function must be called during a callback before a Service Detail Request may be sent, i.e. the callback for the messages Service Discovery Response or Service Detail Response.

## Parameters

- **ServiceID**: ID of service that is to be requested, in hexadecimal representation.

## Return Values

- **0**: Not successful
- **1**: Successful

## Example

—
