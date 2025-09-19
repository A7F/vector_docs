[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCGetOEMPRovisioningCertificate.md)

# SCC_GetOEMPRovisioningCertificate

[CAPL Functions](../../CAPLfunctions.md) » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [V2G Data Queries](../CAPLFunctionsSmartChargingOverview.md#V2GDataQueries) » [EVSE Functions](../CAPLFunctionsSmartChargingOverview.md#V2GDataQueriesEVSE) » SCC_GetOEMPRovisioningCertificate

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE  •  CANoe4SW DE

**Note**  
This function can be called only within the assigned callback. The function is used to query the details of a request.

## Function Syntax

```c
void SCC_GetOEMPRovisioningCertificate(char Certificate[])
```

## Description

Gets the OEM provisioning certificate from the target certificate as base64 string.

## Parameters

- **Certificate**: Queries the OEM provisioning certificate as base64 string (to the given char buffer).

## Return Values

—

## Example

—

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
