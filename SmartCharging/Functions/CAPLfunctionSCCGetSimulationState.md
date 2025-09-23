# SCC_GetSimulationState

[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCGetSimulationState.md)

**CAPL Functions** » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [Simulation Control](../CAPLFunctionsSmartChargingOverview.md#SimulationControl) » [Shared Functions](../CAPLFunctionsSmartChargingOverview.md#SimulationControl) » **SCC_GetSimulationState**

**Valid for:** CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long SCC_GetSimulationState ( )
```

## Description

This function checks if the simulation is running, waiting (in **pause** state) or stopped.

## Parameters

—

## Return Values

- **0**: Simulation is deactivated.
- **1**: Simulation is running in passive mode.
- **2**: Simulation is running in active mode.
- **3**: Simulation is running in active mode and waiting.  
  ([SCC_SimulationWait()](CAPLfunctionSCCSimulationWait.md) has been called)

## Example

—
