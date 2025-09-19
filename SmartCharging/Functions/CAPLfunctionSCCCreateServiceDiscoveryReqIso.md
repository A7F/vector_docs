[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCCreateServiceDiscoveryReqIso.md)

**CAPL Functions** » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [V2G Test Functions](../CAPLFunctionsSmartChargingOverview.md#V2GTestISO) » [Shared Functions](../CAPLFunctionsSmartChargingOverview.md#V2GTestISO) » **SCC_CreateServiceDiscoveryReq_ISO**

# SCC_CreateServiceDiscoveryReq_ISO

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```
long SCC_CreateServiceDiscoveryReq_ISO 
( byte SessionID[] )
```

## Description

Creates a Service Discovery Request message for sending.

## Parameters

- **SessionID**: 8-byte long SessionID of SCC connection, range: 0 - 0xFF FF FF FF FF FF FF FF.

### Optional Parameters

- **Index**: 0
  - **Name**: ServiceScope
  - **Type**: char[]
  - **Description**: Scope of requested service.

- **Index**: 1
  - **Name**: ServiceType
  - **Type**: char[]
  - **Description**: Type of requested service.

## Return Values

- **1**: If successful.
- **0**: Else (message cannot be sent).

## Example

—

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
