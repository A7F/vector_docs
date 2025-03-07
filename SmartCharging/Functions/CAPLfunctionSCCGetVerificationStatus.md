[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCGetVerificationStatus.md)

# SCC_GetVerificationStatus

[CAPL Functions](../../CAPLfunctions.md) » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [V2G Data Queries](../CAPLFunctionsSmartChargingOverview.md#V2GDataQueries) » [Shared Functions](../CAPLFunctionsSmartChargingOverview.md#V2GDataQueries) » SCC_GetVerificationStatus

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE  •  CANoe4SW DE

**Note**  
This function can be called only within the assigned callback. It is used to query the details of a SLAC or V2G message.

## Function Syntax

```
dword SCC_GetVerificationStatus ( )
```

## Description

Gets the state of the received message regarding the validity of its signature.

## Parameters

—

## Return Values

- **0**: Verification failed.
- **1**: Verification successful.
- **2**: Not verified (unsigned message or not required).

## Example

—

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)