[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCGetMinCurrent.md)

## SCC_GetMinCurrent

[CAPL Functions](../../CAPLfunctions.md) » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [V2G Data Queries](../CAPLFunctionsSmartChargingOverview.md#V2GDataQueries) » [Shared Functions](../CAPLFunctionsSmartChargingOverview.md#V2GDataQueries) » SCC_GetMinCurrent

### Tool Availability

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE  •  CANoe4SW DE

### Note

This function can be called only within the assigned callback. The function is used to query the details of a request or of a SLAC or V2G message.

### Function Syntax

```plaintext
float SCC_GetMinCurrent ( )
```

### Description

Gets the vehicle's minimum current.

### Parameters

—

### Return Values

Returns Minimum line current of vehicle (AC: **EVMinCurrent**, DC: **EVMinimumCurrentLimit**).

### Example

—

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)