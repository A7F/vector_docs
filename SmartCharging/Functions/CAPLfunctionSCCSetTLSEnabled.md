[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCSetTLSEnabled.md)

# SCC_SetTLSEnabled

[CAPL Functions](../../CAPLfunctions.md) » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [Simulation Control](../CAPLFunctionsSmartChargingOverview.md#SimulationControl) » [Shared Functions](../CAPLFunctionsSmartChargingOverview.md#SimulationControl) » SCC_SetTLSEnabled

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE  •  CANoe4SW DE

## Function Syntax

```plaintext
void SCC_SetTLSEnabled ( long Enabled )
```

## Description

Specifies if TLS is used. This function will affect both the **Security** flag in the SECC Discovery message and the subsequent communication setup. By calling this function, the configuration parameter **`<UseTLS>`** is overwritten. When no behavior is specified by any of these methods, the remote station may decide for either TCP or TLS.

**Note:**

- Communication between EV and EVSE can only be established if both sides configure the TLS equally.
- You can use the information from [SCC_SECCDiscoveryReq()](../Callbacks/CAPLfunctionSCCSECCDiscoveryReq.md) or [SCC_SECCDiscoveryRes()](../Callbacks/CAPLfunctionSCCSECCDiscoveryRes.md) to adjust the TLS mode for one station.

## Parameters

- **Enabled**: 1 to enable TLS support, 0 to disable TLS support.

## Return Values

—

## Example

—

[SCC_SECCDiscoveryReq()](../Callbacks/CAPLfunctionSCCSECCDiscoveryReq.md) | [SCC_SECCDiscoveryRes()](../Callbacks/CAPLfunctionSCCSECCDiscoveryRes.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
