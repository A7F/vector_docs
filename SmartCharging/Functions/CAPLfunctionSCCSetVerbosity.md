[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCSetVerbosity.md)

# SCC_SetVerbosity

[CAPL Functions](../../CAPLfunctions.md) » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [General Functions](../CAPLFunctionsSmartChargingOverview.md#GeneralFunctions) » [Shared Functions](../CAPLFunctionsSmartChargingOverview.md#GeneralFunctions) » SCC_SetVerbosity

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE  •  CANoe4SW DE

## Function Syntax

```
void SCC_SetVerbosity ( dword Level )
```

## Description

Sets the **Verbosity** parameter of the DLL. The higher the value is, the more information will be output in the write window.

## Parameters

- **Level**: The desired verbosity level.

  - **0**: Signals only critical errors.
  - **1**: Signals errors due to erroneous configurations, etc.
  - **2**: Warns, if an unexpected protocol status is reached, and signals missing obligatory callbacks.
  - **3**: Informs about missing optional callbacks and minor problems.
  - **>3**: Signals low level events such as setting and expiring of timers.

## Return Values

—

## Example

—

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
