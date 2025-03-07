[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCGetMaxCurrent.md)

## SCC_GetMaxCurrent

**Path:** [CAPL Functions](../../CAPLfunctions.md) » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [2G Data Queries](../CAPLFunctionsSmartChargingOverview.md#V2GDataQueries) » [Shared Functions](../CAPLFunctionsSmartChargingOverview.md#V2GDataQueries) » SCC_GetMaxCurrent

**Valid for:** [CANoe DE](../../../Shared/FeatureAvailability.md) • CANoe4SW DE

### Note

This function can be called only within the assigned callback. The function is used to query the details of a request.

### Function Syntax

```plaintext
float SCC_GetMaxCurrent ( )
```

### Description

Returns the SDP or V2G message header (to the output buffer).

### Parameters

—

### Return Values

Returns Maximum line current of vehicle (AC: **EVMaxCurrent**, DC: **EVMaximumCurrentLimit**).

### Example

—

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)