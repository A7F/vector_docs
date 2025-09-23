[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCStartPassive.md)

# SCC_StartPassive

[CAPL Functions](../../CAPLfunctions.md) » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [Simulation Control](../CAPLFunctionsSmartChargingOverview.md#SimulationControl) » [Shared Functions](../CAPLFunctionsSmartChargingOverview.md#SimulationControl) » SCC_StartPassive

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE  •  CANoe4SW DE

## Function Syntax

```
long SCC_StartPassive ( )
```

```
long SCC_StartPassive ( dword SLACMode )
```

## Description

This function activates the modeling library, but does not start an SCC simulation (i.e. a state machine). In this state, callbacks can be received, and test functions can be called.

## Parameters

- **SLACMode**: Controls the behavior regarding SLAC, which overrides the parameter `<UseSLAC>` from the XML configuration:
  - 0 = SLAC is skipped (may be done manually)
  - 1 = SLAC is used
  - 2 = EV: use SLAC depending on link status (not recommended due to HomePlug Green PHY chip instabilities)

## Return Values

- **0**: Not successful
- **1**: Successful

## Example

—
