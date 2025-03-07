[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCCreateAuthorizationReqISO.md)

**CAPL Functions** » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [V2G Test Functions](../CAPLFunctionsSmartChargingOverview.md#V2GTestISO) » [Shared Functions](../CAPLFunctionsSmartChargingOverview.md#V2GTestISO) » **SCC_CreateAuthorizationReq_ISO**

# SCC_CreateAuthorizationReq_ISO

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```
long SCC_CreateAuthorizationReq_ISO ( byte SessionID[] )
```

## Description

Creates an Authorization Request message for sending.

## Parameters

- **SessionID**: 8-byte long SessionID of SCC connection, range: 0 - 0xFF FF FF FF FF FF FF FF.

### Optional Parameters

- **Index**: 0
  - **Name**: Id
  - **Type**: char[]
  - **Description**: Id of the message.

- **Index**: 1
  - **Name**: GenChallenge
  - **Type**: byte[]
  - **Description**: Challenge data (16 byte).

## Return Values

- **1**: If successful.
- **0**: Else (message cannot be sent).

## Example

—

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)