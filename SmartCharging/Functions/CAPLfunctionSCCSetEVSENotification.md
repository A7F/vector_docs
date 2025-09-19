[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCSetEVSENotification.md)

## SCC_SetEVSENotification

[CAPL Functions](../../CAPLfunctions.md) » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [V2G Simulation Data](../CAPLFunctionsSmartChargingOverview.md#V2GSimDataWrite) » [EVSE Functions](../CAPLFunctionsSmartChargingOverview.md#V2GSimDataWrite) » SCC_SetEVSENotification

**Valid for**:  CANoe DE • CANoe4SW DE

### Function Syntax

```plaintext
long SCC_SetEVSENotification ( char EVSENotification[] )
```

### Description

Sets the EVSE notification enum.

### Parameters

- **EVSENotification**: String that must match an enum value according to the schema. Possible values are:
  - None
  - StopCharging
  - ReNegotiation

### Return Values

- **0**: Not successful
- **1**: Successful

### Example

—

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
