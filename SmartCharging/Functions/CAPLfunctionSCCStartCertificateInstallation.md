[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCStartCertificateInstallation.md)

# SCC_StartCertificateInstallation

[CAPL Functions](../../CAPLfunctions.md) » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [V2G Simulation Control](../CAPLFunctionsSmartChargingOverview.md#V2GSimControl) » [EV Functions](../CAPLFunctionsSmartChargingOverview.md#V2GSimControl) » SCC_StartCertificateInstallation

**Valid for**:  CANoe DE • CANoe4SW DE

## Function Syntax

```
long SCC_StartCertificateInstallation ( )
```

## Description

Schedules a **CertificateInstallationReq** message to be sent after the **ServiceAndPaymentSelectionReq**. This is only possible when in ISO 15118 PnC mode.

## Parameters

—

## Return Values

- **0**: Not successful
- **1**: Successful

## Example

—

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)