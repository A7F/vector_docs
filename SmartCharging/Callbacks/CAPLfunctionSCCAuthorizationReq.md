[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Callbacks/CAPLfunctionSCCAuthorizationReq.md)

# SCC_AuthorizationReq

[CAPL Functions](../../CAPLfunctions.md) » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [EVSE Callback Functions](../CAPLFunctionsSmartChargingOverview.md#CallbackEVSE) » SCC_AuthorizationReq

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE  •  CANoe4SW DE

## Function Syntax

```plaintext
void SCC_AuthorizationReq ( byte SessionID[] )
```

## Description

The callback is called as soon as an Authorization Request is received.

The challenge optionally transmitted in this request can be queried with [SCC_GetGenChallenge](../Functions/CAPLfunctionSCCGetGenChallenge.md).

Alternatively, the callback [SCC_ContractAuthenticationReq](CAPLfunctionSCCContractAuthenticationReq.md) can be used. Both functions are called when the message is received. `SCC_ContractAuthenticationReq` is called first.

## Parameters

- **SessionID**: 8-byte long SessionID of SCC connection, range: 0 – 0xFF FF FF FF FF FF FF FF.

## Return Values

—

## Example

—
