[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCSetMaxPower.md)

## SCC_SetMaxPower

[CAPL Functions](../../CAPLfunctions.md) » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [V2G Simulation Data](../CAPLFunctionsSmartChargingOverview.md#V2GSimDataWrite) » [Shared Functions](../CAPLFunctionsSmartChargingOverview.md#V2GSimDataWrite) » SCC_SetMaxPower

### Tool Availability

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE  •  CANoe4SW DE

### Note

This function needs a running SCC session in order to work. Make sure to call it only after the Session Setup Request message is sent.

### Function Syntax

```plaintext
long SCC_SetMaxPower ( float MaxPower )
```

### Description

Sets the limit for power. These limits are used in various messages for both AC and DC mode (the actual element name depends on the charging mode and the protocol version). Defaults can be set using the respective configuration file.

### Parameters

- **MaxPower**: Limit value to be set.

### Return Values

- **0**: Not successful
- **1**: Successful

### Example

—

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
