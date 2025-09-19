[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCGetEnergyTransferMode.md)

[CAPL Functions](../../CAPLfunctions.md) » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [V2G Data Queries](../CAPLFunctionsSmartChargingOverview.md#V2GDataQueries) » [EV Functions](../CAPLFunctionsSmartChargingOverview.md#V2GDataQueriesEV) » SCC_GetEnergyTransferMode

# SCC_GetEnergyTransferMode

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE •  CANoe4SW DE

**Note**  
This function can be called only within the assigned callback. The function is used to query the details of a request.

## Function Syntax

```c
void SCC_GetEnergyTransferMode ( long Index, char EnergyTransferMode[] )
```

## Description

Gets EnergyTransferMode with the target index (ISO 15118).

## Parameters

- **Index**  
  Zero-based index of the sub element. Use [SCC_GetEnergyTransferModeCount](CAPLfunctionSCCGetEnergyTransferModeCount.md) to retrieve the number of elements.

- **EnergyTransferMode**  
  Queries the textual representation of the EnergyTranferMode (e.g. **DC_extended**) (to the given char buffer).

## Return Values

—

## Example

—

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
