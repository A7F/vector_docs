[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCSuspendTx.md)

**CAPL Functions** » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [Simulation Control](../CAPLFunctionsSmartChargingOverview.md#SimulationControl) » [Shared Functions](../CAPLFunctionsSmartChargingOverview.md#SimulationControl) » **SCC_SuspendTx**

# SCC_SuspendTx

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE  •  CANoe4SW DE

## Function Syntax

```plaintext
void SCC_SuspendTx ( long NumberOfMessages )
```

## Description

Skips the sending of the following messages depending on the parameter value.

## Parameters

- **NumberOfMessages**

  | Value | Behavior |
  |-------|----------|
  | -1    | Sending of all further messages is suspended. |
  | 0     | Resume. Starting from current state messages are sent. |
  | >0    | The following **NumberOfMessages** are suspended. |

## Return Values

- **0**: Not successful
- **1**: Successful

## Example

—