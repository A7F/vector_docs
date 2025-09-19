[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCStartSimulation.md)

**CAPL Functions** » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [Simulation Control](../CAPLFunctionsSmartChargingOverview.md#SimulationControl) » [Shared Functions](../CAPLFunctionsSmartChargingOverview.md#SimulationControl) » SCC_StartSimulation

# SCC_StartSimulation

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

**Note**  
If simulation is restarted after a stop, the XML configuration file will be read in again. While the simulation is deactivated, another data set can be loaded with [SCC_LoadCommunicationConfig](CAPLfunctionSCCLoadCommunicationConfig.md).

## Function Syntax

- `long SCC_StartSimulation()` // form 1
- `long SCC_StartSimulation(dword SLACMode)` // form 2

## Description

These functions start the simulation DLL in active mode.

**Note**  
Until the simulation is started, no messages are sent and the API (except `SCC_StartSimulation()`) has no effect!

With the vehicle DLL, the call of `SCC_StartSimulation()` starts the setup of a connection.

## Parameters

- **SLACMode**  
  Controls the behavior regarding SLAC, which overrides the parameter `<UseSLAC>` from the XML configuration:
  - 0 = SLAC is skipped (may be done manually)
  - 1 = SLAC is used
  - 2 = EV: use SLAC depending on link status (not recommended due to HomePlug Green PHY chip instabilities)

## Return Values

- **0**  
  Not successful

- **1**  
  Successful

## Example

—

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
