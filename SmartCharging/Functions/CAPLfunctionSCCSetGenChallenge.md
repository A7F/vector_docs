[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCSetGenChallenge.md)

# SCC_SetGenChallenge

[CAPL Functions](../../CAPLfunctions.md) » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [V2G Simulation Data](../CAPLFunctionsSmartChargingOverview.md#V2GSimDataWrite) » [EVSE Functions](../CAPLFunctionsSmartChargingOverview.md#V2GSimDataWrite) » SCC_SetGenChallenge

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE •  CANoe4SW DE

## Function Syntax

```
long SCC_SetGenChallenge ( byte GenChallenge[] )
```

## Description

Sets the challenge for the **PaymentDetailsRes** message, which is randomly generated otherwise.

## Parameters

- **GenChallenge**: Value to be set. Array length must be 16 byte.

## Return Values

- **0**: Not successful
- **1**: Successful

## Example

—

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
