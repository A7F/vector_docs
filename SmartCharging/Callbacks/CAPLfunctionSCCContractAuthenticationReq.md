[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Callbacks/CAPLfunctionSCCContractAuthenticationReq.md)

[CAPL Functions](../../CAPLfunctions.md) » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [EVSE Callback Functions](../CAPLFunctionsSmartChargingOverview.md#CallbackEVSE) » SCC_ContractAuthenticationReq

# SCC_ContractAuthenticationReq

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE •  CANoe4SW DE

## Function Syntax

```
void SCC_ContractAuthenticationReq ( byte SessionID[] )
```

## Description

The callback is called as soon as a Contract Authentication Request is received.

The challenge optionally transmitted in this request can be queried with [SCC_GetGenChallenge](../Functions/CAPLfunctionSCCGetGenChallenge.md).

Alternatively, the callback [SCC_AuthorizationReq](CAPLfunctionSCCAuthorizationReq.md) can be used. Both functions are called when the message is received. `SCC_ContractAuthenticationReq` is called first.

## Parameters

- **SessionID**: 8-byte long SessionID of SCC connection, range: 0 – 0xFF FF FF FF FF FF FF FF.

## Return Values

—

## Example

—

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)