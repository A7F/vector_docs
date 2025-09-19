[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCSetMessageDelay.md)

## SCC_SetMessageDelay

**CAPL Functions** » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [Simulation Control](../CAPLFunctionsSmartChargingOverview.md#SimulationControl) » [Shared Functions](../CAPLFunctionsSmartChargingOverview.md#SimulationControl) » SCC_SetMessageDelay

### Tool Availability

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE  •  CANoe4SW DE

### Function Syntax

```plaintext
void SCC_SetMessageDelay ( dword Delay ) // form 1
void SCC_SetMessageDelay ( dword Delay, float JitterPercent ) // form 2
```

### Description

Specifies the delay time before an SCC message is sent. This allows you to slow down the protocol sequence. The delay applies to all active connections of the module.

### Parameters

- **Delay**: Desired delay value in milliseconds.
- **JitterPercent**: Desired jitter (max. random variation) in % of Delay.

### Return Values

—

### Example

—

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
