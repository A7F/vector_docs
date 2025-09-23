[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCStopSimulation.md)

## SCC_StopSimulation

[CAPL Functions](../../CAPLfunctions.md) » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [Simulation Control](../CAPLFunctionsSmartChargingOverview.md#SimulationControl) » [Shared Functions](../CAPLFunctionsSmartChargingOverview.md#SimulationControl) » SCC_StopSimulation

**Valid for**:  CANoe DE • CANoe4SW DE

### Note

If simulation is restarted after a stop, the XML configuration file will be read in again. While the simulation is deactivated, another data set can be loaded with [SCC_LoadCommunicationConfig](CAPLfunctionSCCLoadCommunicationConfig.md).

### Function Syntax

```
long SCC_StopSimulation ( )
```

### Description

These functions activate/deactivate the SCC simulation.

**Note**: If the simulation is deactivated, no messages are sent and the API (except [SCC_StartSimulation()](CAPLfunctionSCCStartSimulation.md)) has no effect!

With the vehicle DLL, the call of [SCC_StartSimulation()](CAPLfunctionSCCStartSimulation.md) starts the setup of a connection.

### Parameters

—

### Return Values

- **0**: Not successful
- **1**: Successful

### Example

—
