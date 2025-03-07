[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCGetMaxPower.md)

**CAPL Functions** » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [V2G Data Queries](../CAPLFunctionsSmartChargingOverview.md#V2GDataQueries) » [Shared Functions](../CAPLFunctionsSmartChargingOverview.md#V2GDataQueries) » SCC_GetMaxPower

# SCC_GetMaxPower

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE •  CANoe4SW DE

**Note**

- This function can be called only within the assigned callback. The function is used to query the details of a request.
- This function applies only to the SAScheduleList of ISO 15118.

## Function Syntax

`float SCC_GetMaxPower ( )`

## Description

Gets the vehicle's or the charge point's maximum power.

## Parameters

—

## Return Values

Returns Maximum power of vehicle (AC: **EVMaxPower**, DC: **EVMaximumPowerLimit**) or charge point **EVSEMaximumPowerLimit**.

## Example

—

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)