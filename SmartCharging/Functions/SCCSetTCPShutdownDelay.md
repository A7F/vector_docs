[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/SCCSetTCPShutdownDelay.md)

# SCC_SetTCPShutdownDelay

[CAPL Functions](../../CAPLfunctions.md) » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [Simulation Control](../CAPLFunctionsSmartChargingOverview.md#SimulationControl) » [Shared Functions](../CAPLFunctionsSmartChargingOverview.md#SimulationControl) » SCC_SetTCPShutdownDelay

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE  •  CANoe4SW DE

## Function Syntax

```plaintext
void SCC_SetTCPShutdownDelay ( dword DelayInMs )
```

## Description

Specifies the delay time between reaching the state **protocol finished** (e.g. because of SessionStop or a timeout / error) and the closure of the TCP connection with ACK FIN.

## Parameters

- **DelayInMs**

  | Value | Behavior                             |
  |-------|--------------------------------------|
  | 0     | Close immediately.                   |
  | >0    | Close after the specified time has passed. |

## Return Values

—

## Example

—

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)