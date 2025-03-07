[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCGetEnergyTransferType.md)

**CAPL Functions** » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [V2G Data Queries](../CAPLFunctionsSmartChargingOverview.md#V2GDataQueries) » [Shared Functions](../CAPLFunctionsSmartChargingOverview.md#V2GDataQueries) » **SCC_GetEnergyTransferType**

# SCC_GetEnergyTransferType

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE  •  CANoe4SW DE

**Note**

This function can be called only within the assigned callback. The function is used to query the details of a request.

## Function Syntax

`long SCC_GetEnergyTransferType ( char[] EnergyTransferType )`

## Description

Gets the energy transfer type (DIN 70121) resp. energy transfer mode (ISO 15118) from various messages.

## Parameters

- **EnergyTransferType**: Queries the charging mode used in the message (to the given char buffer). If this is not required, transfer an empty string.

## Return Values

Type of requested power supply:

- **0**: AC_Charging
- **1**: DC_Charging

## Example

—

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)