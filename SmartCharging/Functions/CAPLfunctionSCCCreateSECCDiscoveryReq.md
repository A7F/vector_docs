[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCCreateSECCDiscoveryReq.md)

**CAPL Functions** » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [V2G Test Functions](../CAPLFunctionsSmartChargingOverview.md#V2Gtestfunctions) » [Shared Functions](../CAPLFunctionsSmartChargingOverview.md#V2Gtestfunctions) » **SCC_CreateSECCDiscoveryReq**

# SCC_CreateSECCDiscoveryReq

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long SCC_CreateSECCDiscoveryReq ( dword TLSEnabled ) //form 1
long SCC_CreateSECCDiscoveryReq ( dword Security, dword TransportProtocol ) //form 2
```

## Description

Creates a SECC Discovery Request message for sending.

## Parameters

- **TLSEnabled**: 1 for TLS, 0 for **no transport layer security**.
- **Security**: Security field (1 byte), valid values: 0x00 = TLS, 0x10 = No transport layer security.
- **TransportProtocol**: Transport protocol field (1 byte), valid values: 0x00 = TCP.

## Return Values

—

## Example

—
