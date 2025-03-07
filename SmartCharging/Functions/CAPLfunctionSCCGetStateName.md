[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCGetStateName.md)

# SCC_GetStateName

[CAPL Functions](../../CAPLfunctions.md) » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [General Functions](../CAPLFunctionsSmartChargingOverview.md#GeneralFunctions) » [Shared Functions](../CAPLFunctionsSmartChargingOverview.md#GeneralFunctions) » SCC_GetStateName

**Valid for:** CANoe DE • CANoe4SW DE

## Function Syntax

```
void SCC_GetStateName ( dword State, char Buffer[], int BufferLength )
```

## Description

Gets a string representation of a state enum value obtained with [SCC_StateTransitionInd](../Callbacks/CAPLfunctionSCCStateTransitionInd.md).

## Parameters

- **State**: State enum to be translated.
- **Buffer**: Queries the string representation (to the given char buffer).
- **BufferLength**: Size of the output buffer.

## Return Values

—

## Example

—

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)