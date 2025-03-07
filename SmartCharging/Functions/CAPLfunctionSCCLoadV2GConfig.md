[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCLoadV2GConfig.md)

**CAPL Functions** » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [Simulation Control](../CAPLFunctionsSmartChargingOverview.md#SimulationControl) » [Shared Functions](../CAPLFunctionsSmartChargingOverview.md#SimulationControl) » **SCC_LoadV2GConfig**

# SCC_LoadV2GConfig

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE •  CANoe4SW DE

### Note

- The charge point DLL uses the `<EVSEConfiguration>` XML elements, and the vehicle DLL the `<PEVConfiguration>` elements. The two configuration types can be numbered independently.
- Using `SCC_LoadV2GConfig()`, the charge point may react on the requested schema, by supplying e.g. different types of tariff tables and service lists.

## Function Syntax

```
long SCC_LoadV2GConfig ( long ConfigID )
```

## Description

Loads the section within the XML configuration file designated with `configID`. If `LoadCommunicationConfig` has not yet been called when the simulation starts, section 0 is loaded automatically.

The function `SCC_LoadCommunicationConfig` loads the configuration globally, i.e. for all connections to be created. This call is only possible when simulation is deactivated.

The function `SCC_LoadV2GConfig` loads the configuration for an already active connection, applying only those parameters relevant to an individual connection.

## Parameters

- **ConfigID**: ID of desired configuration section.

## Return Values

- **0**: Not successful
- **1**: Successful

## Example

—

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)