[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCCreateSECCDiscoveryRes.md)

**CAPL Functions** » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [V2G Test Functions](../CAPLFunctionsSmartChargingOverview.md#V2Gtestfunctions) » [Shared Functions](../CAPLFunctionsSmartChargingOverview.md#V2Gtestfunctions) » SCC_CreateSECCDiscoveryRes

# SCC_CreateSECCDiscoveryRes

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

- `long SCC_CreateSECCDiscoveryRes ( char IpAddress [],dword Port, dword TLSEnabled) //form 1`
- `long SCC_CreateSECCDiscoveryRes ( char IpAddress [], dword Port, dword Security, dword TransportProtocol ) //form 2`

## Description

Creates a SECC Discovery Response message for sending.

- Form 1 creates valid messages only.
- Form 2 allows to specify arbitrary byte values for the two message parameters **Security** and **TransportProtocol**.

## Parameters

- **IpAddress**: String representation of the EVSE’s IPv6 address in the usual notation.
- **Port**: Target port number.
- **TLSEnabled**: 1 for TLS, 0 for no transport layer security.
- **Security**: Security field (1 byte), valid values: 0x00 = TLS, 0x10 = No transport layer security.
- **TransportProtocol**: Transport protocol field (1 byte), valid values: 0x00 = TCP.

## Return Values

- **1**: If successful.
- **0**: Else (message cannot be sent).

## Example

—
