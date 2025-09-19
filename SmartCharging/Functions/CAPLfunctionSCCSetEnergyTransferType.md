[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCSetEnergyTransferType.md)

**CAPL Functions** » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [V2G Simulation Control](../CAPLFunctionsSmartChargingOverview.md#V2GSimControl) » [Shared Functions](../CAPLFunctionsSmartChargingOverview.md#V2GSimControl) » **SCC_SetEnergyTransferType**

# SCC_SetEnergyTransferType

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE  •  CANoe4SW DE

## Function Syntax

- `long SCC_SetEnergyTransferType ( char EnergyTransferType[] ) //form 1 (EV only)`
- `long SCC_SetEnergyTransferType ( char EnergyTransferType[], dword Force ) // form 2 (EV only)`
- `long SCC_SetEnergyTransferType ( char EnergyTransferType[] ) // form 3 (EVSE only)`

## Description

**EV:**

Sets the desired charging mode **for a running SCC session**. For the list of all valid charging modes, see the SCC specification.

**EVSE:**

Sets the offered energy transfer type (DIN 70121) resp. -mode (ISO 15118) **for a running SCC session**. In case of ISO 15118, a list with one element is created. For the list of all valid values, see the SCC specification.

## Parameters

- **EnergyTransferType (EV/EVSE):** Desired charging mode as string. Please make sure the string entered is a valid according to the schema.
- **Force (EV):** If set to 1, the vehicle is forced to set the charging mode even if the charge point hasn’t offered it previously. If set to 0, another mode may be selected if this one is unavailable.

## Return Values

- **0:** Not successful
- **1:** Successful

## Example

—

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
