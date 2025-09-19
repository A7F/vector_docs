[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCGetDCStatusCode.md)

**CAPL Functions** » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [V2G Simulation Data](../CAPLFunctionsSmartChargingOverview.md#V2GSimDataRead) » [Shared Functions](../CAPLFunctionsSmartChargingOverview.md#V2GSimDataRead) » **SCC_GetDCStatusCode**

# SCC_GetDCStatusCode

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE •  CANoe4SW DE

## Function Syntax

```plaintext
void SCC_GetDCStatusCode ( byte SessionID[], char StatusCode[] ) // form 1
void SCC_GetDCStatusCode ( char StatusCode[] ) // form 2
```

## Description

Outputs the DC status in string form.

## Parameters

- **SessionID**: Queries the 8-byte long SessionID of SCC connection, range: 0 – 0xFF FF FF FF FF FF FF FF (to the given byte buffer).
- **StatusCode**: Queries the status code (to the given char buffer).

## Return Values

—

## Example

—

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
