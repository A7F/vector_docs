[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCSetPresentCurrent.md)

## SCC_SetPresentCurrent

**CAPL Functions** » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [V2G Simulation Data](../CAPLFunctionsSmartChargingOverview.md#V2GSimDataWrite) » [EVSE Functions](../CAPLFunctionsSmartChargingOverview.md#V2GSimDataWrite) » SCC_SetPresentCurrent

### Valid for:  
[CANoe DE](../../../Shared/FeatureAvailability.md) • CANoe4SW DE

### Function Syntax

```plaintext
long SCC_SetPresentCurrent ( float PresentCurrent )
```

### Description

Sets the present current output. This value is used in various DC messages, and for calculating the MeterInfo in AC mode. If no value is set, the charge point will automatically calculate a default.

### Parameters

- **PresentCurrent**: Value to be set.

### Return Values

- **0**: Not successful
- **1**: Successful

### Example

—

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
