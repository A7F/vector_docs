[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCGetMaxVoltage.md)

**CAPL Functions** » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [V2G Data Queries](../CAPLFunctionsSmartChargingOverview.md#V2GDataQueries) » [Shared Functions](../CAPLFunctionsSmartChargingOverview.md#V2GDataQueries) » **SCC_GetMaxVoltage**

# SCC_GetMaxVoltage

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE •  CANoe4SW DE

**Note**  
This function can be called only within the assigned callback. The function is used to query the details of a request.

## Function Syntax

`float SCC_GetMaxVoltage ( )`

## Description

Gets the vehicle's maximum voltage.

## Parameters

—

## Return Values

Returns Maximum line voltage of vehicle (AC: **EVSEMaxVoltage**, DC: **EVSEMaximumVoltageLimit**).

## Example

—

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)