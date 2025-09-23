[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Callbacks/CAPLfunctionSCCServiceDiscoveryReq.md)

**CAPL Functions** » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [EVSE Callback Functions](../CAPLFunctionsSmartChargingOverview.md#CallbackEVSE) » **SCC_ServiceDiscoveryReq**

# SCC_ServiceDiscoveryReq

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
void SCC_ServiceDiscoveryReq ( byte SessionId[], char ServiceScope[], char ServiceCategory[] )
```

## Description

The callback is called as soon as a Service Discovery Request is received.

## Parameters

- **SessionID**: 8-byte long SessionID of SCC connection, range: 0 – 0xFF FF FF FF FF FF FF FF.
- **ServiceScope**: Typically designates a company/organization in the form of a URI.
- **ServiceCategory**: Type of requested services.

## Return Values

—

## Example

—
